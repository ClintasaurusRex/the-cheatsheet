
# ISS Spotter

This code is designed to fetch and display the times at which the International Space Station (ISS) will fly over the user's location. It does so by chaining together multiple asynchronous API calls.

## Functions Overview

1. **fetchMyIP(callback)**
2. **fetchCoordsByIP(ip, callback)**
3. **fetchISSFlyOverTimes(coords, callback)**
4. **nextISSTimesForMyLocation(callback)**

## Detailed Explanation

### 1. `fetchMyIP(callback)`

This function fetches the user's IP address using the ipify API.

- **Input:** A callback function to handle the response.
- **Output:** Passes either an error or the IP address to the callback.

```javascript
const fetchMyIP = function(callback) {
  const url = 'https://api.ipify.org?format=json';

  needle.get(url, (error, response, body) => {
    if (error) {
      callback(error);
      return;
    }
    if (response.statusCode !== 200) {
      const msg = `Status Code ${response.statusCode} when fetching IP. Response: ${body}`;
      callback(Error(msg), null);
      return;
    }
    const ip = body.ip;
    callback(null, ip);
  });
};
```

### 2. `fetchCoordsByIP(ip, callback)`

This function fetches the geographical coordinates (latitude and longitude) for a given IP address using the ipwhois API.

- **Input:** An IP address and a callback function.
- **Output:** Passes either an error or the coordinates object to the callback.

```javascript
const fetchCoordsByIP = function(ip, callback) {
  const url = `http://ipwho.is/${ip}`;

  needle.get(url, (error, response, body) => {
    if (error) {
      callback(error);
      return;
    }
    if (!body.success) {
      const message = `Success status was ${body.success}. Server message says: ${body.message} when fetching for IP ${body.ip}`;
      callback(Error(message), null);
      return;
    }

    const coordinates = {
      latitude: body.latitude,
      longitude: body.longitude,
    };
    callback(null, coordinates);
  });
};
```

### 3. `fetchISSFlyOverTimes(coords, callback)`

This function fetches the times at which the ISS will fly over a given set of geographical coordinates using the ISS flyover API.

- **Input:** A coordinates object and a callback function.
- **Output:** Passes either an error or the ISS flyover times to the callback.

```javascript
const fetchISSFlyOverTimes = function(coords, callback) {
  const url = `https://iss-flyover.herokuapp.com/json/?lat=${coords.latitude}&lon=${coords.longitude}`;

  needle.get(url, (error, response, body) => {
    if (error) {
      callback(error);
      return;
    }
    if (response.statusCode !== 200) {
      callback(Error(`Status Code ${response.statusCode} when fetching ISS pass times: ${body}`), null);
      return;
    }

    const flyBys = body.response;
    callback(null, flyBys);
  });
};
```

### 4. `nextISSTimesForMyLocation(callback)`

This function orchestrates the entire process, making the three API calls in sequence and passing the final result (ISS flyover times) to the provided callback.

- **Input:** A callback function.
- **Output:** Passes either an error or the ISS flyover times to the callback.

```javascript
const nextISSTimesForMyLocation = function(callback) {
  fetchMyIP((error, ip) => {
    if (error) {
      // Return error via callback if fetching IP fails
      return callback(error, null);
    }

    fetchCoordsByIP(ip, (error, coordinates) => {
      if (error) {
        console.log("Failed to fetch coordinates: ", error);
        return callback(error, null);
      }

      fetchISSFlyOverTimes(coordinates, (error, flyBys) => {
        if (error) {
          return callback(error, null);
        }
        return callback(null, flyBys);
      });
    });
  });
};

module.exports = { nextISSTimesForMyLocation };
```

## Usage

To use the `nextISSTimesForMyLocation` function, simply call it with a callback that handles the results.

```javascript
const { nextISSTimesForMyLocation } = require('./iss');

nextISSTimesForMyLocation((error, flyBys) => {
  if (error) {
    console.log("It didn't work!" , error);
    return;
  }
  console.log('It worked! Returned flyover times:' , flyBys);
});
```
