    fetchMyIP(callback): Retrieves the user's public IP address.
    fetchCoordsByIP(ip, callback): Gets the geographical coordinates (latitude and longitude) for a given IP address.
    fetchISSFlyOverTimes(coords, callback): Fetches the ISS flyover times for given coordinates.
    nextISSTimesForMyLocation(callback): Orchestrates the above functions to get the ISS flyover times for the user's location.

How It Works
1. Fetch the IP Address

The fetchMyIP function makes an HTTP GET request to https://api.ipify.org?format=json to get the user's public IP address.

javascript

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

    Request: Makes a GET request to the API to retrieve the IP address.
    Error Handling: If there's an error or the response status code is not 200, it passes an error to the callback.
    Success: Extracts the IP address from the response body and passes it to the callback.

2. Fetch Coordinates by IP

The fetchCoordsByIP function takes an IP address and makes an HTTP GET request to http://ipwho.is/<ip> to get the geographical coordinates.

javascript

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

    Request: Makes a GET request to the API to retrieve the coordinates.
    Error Handling: If there's an error, it passes an error to the callback. Also checks if the response was not successful.
    Success: Extracts the coordinates from the response body and passes them to the callback.

3. Fetch ISS Flyover Times

The fetchISSFlyOverTimes function takes coordinates and makes an HTTP GET request to https://iss-flyover.herokuapp.com/json/?lat=<latitude>&lon=<longitude> to get the ISS flyover times.

javascript

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

    Request: Makes a GET request to the API to retrieve the ISS flyover times.
    Error Handling: If there's an error or the response status code is not 200, it passes an error to the callback.
    Success: Extracts the flyover times from the response body and passes them to the callback.

4. Orchestrate All Functions

The nextISSTimesForMyLocation function ties everything together. It calls the above functions sequentially, passing the results from one function to the next.

javascript

const nextISSTimesForMyLocation = function(callback) {
  fetchMyIP((error, ip) => {
    if (error) {
      return callback(error, null);
    }
    fetchCoordsByIP(ip, (error, coordinates) => {
      if (error) {
        return callback(error, null);
      }
      fetchISSFlyOverTimes(coordinates, (error, flyOverTimes) => {
        if (error) {
          return callback(error, null);
        }
        callback(null, flyOverTimes);
      });
    });
  });
};

How It Works

    Get IP: Calls fetchMyIP to get the user's IP address.
        If there's an error, it immediately passes the error to the callback and stops further execution.
    Get Coordinates: Calls fetchCoordsByIP with the obtained IP address to get the coordinates.
        If there's an error, it immediately passes the error to the callback and stops further execution.
    Get ISS Flyover Times: Calls fetchISSFlyOverTimes with the obtained coordinates to get the ISS flyover times.
        If there's an error, it immediately passes the error to the callback and stops further execution.
    Return Result: If all steps succeed, it passes the ISS flyover times to the callback.

Testing the Function

In index.js, you call the nextISSTimesForMyLocation function and log the results:

javascript

const { nextISSTimesForMyLocation } = require('./iss');

nextISSTimesForMyLocation((error, flyOverTimes) => {
  if (error) {
    console.log("It didn't work!" , error);
    return;
  }
  console.log('It worked! Returned flyover times:' , flyOverTimes);
});

    Call the Function: This calls the nextISSTimesForMyLocation function.
    Handle Results: It handles any errors by logging them, or logs the successful result of flyover times.

By chaining the functions together with callbacks, you ensure each step is completed before moving to the next, allowing for proper handling of asynchronous operations and errors.