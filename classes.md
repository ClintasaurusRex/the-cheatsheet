# Object-Oriented Programming Cheat Sheet

## Classes

- A class is a blueprint for creating objects.
- It defines attributes (data) and methods (behavior) that its objects will have.
- Classes encapsulate data and functionality into a single unit.

### Syntax (Java example):
```java
public class Car {
    private String make;
    private String model;

    public void startEngine() {
        // Method implementation`
    }
}



Superclass (Parent class)
A superclass is a class that is inherited from.
It contains common attributes and methods that can be shared by multiple subclasses.
Promotes code reuse and establishes a hierarchical relationship between classes.
Syntax (Java example):

public class Vehicle {
    // Protected attribute accessible to subclasses
    protected String type;

    // Private attribute, only accessible within this class
    private int year;

    // Constructor
    public Vehicle(String type, int year) {
        this.type = type;
        this.year = year;
    }
}



Subclass (Child class)
A subclass is a class that inherits from a superclass.
It can add new attributes and methods or override existing ones from the superclass.
Allows for specialization and extension of the superclass functionality.
Syntax (Java example):
// Subclass (Child class)
public class Car extends Vehicle {
    // New attribute specific to Car
    private int numberOfDoors;

    // Constructor
    public Car(String type, int year, int numberOfDoors) {
        // Call superclass constructor
        super(type, year);
        this.numberOfDoors = numberOfDoors;
    }
}



Getters and Setters
Getters and setters are methods used to access and modify private attributes of a class.

Getters
Used to retrieve the value of a private attribute.
Usually start with "get" followed by the attribute name.
Syntax:
public String getMake() {
    return make;
}



Setters
Used to set or modify the value of a private attribute.
Usually start with "set" followed by the attribute name.
Often include parameter validation.
Syntax:
public void setMake(String make) {
    if (make != null && !make.isEmpty()) {
        this.make = make;
    }
}



Benefits of Getters and Setters
Encapsulation: Control access to class attributes.
Validation: Ensure data integrity by validating input in setters.
Flexibility: Can modify internal implementation without affecting external code.
Read-only or write-only access: Can provide only getter (read-only) or only setter (write-only) as needed.

This cheat sheet provides a quick reference for the core concepts of classes, inheritance (superclass and subclass), and getters and setters in object-oriented programming. The examples are in Java, but the concepts apply to most object-oriented languages.

### Getters:
// A getter is like peeking into your piggy bank to see how much money is inside.
// You're not putting money in or taking it out, just looking at what's there.
// In programming, a getter lets you safely check the value of a private variable without directly accessing it.
// Setters:

// A setter is like putting money into your piggy bank through a special slot.
// You can't just open the piggy bank and throw money in; you have to use this slot.
// In programming, a setter lets you safely change the value of a private variable.
// Why use them?gy bank to see how much money is inside.
// You're not putting money in or taking it out, just looking at what's there.
// In programming, a getter lets you safely check the value of a private variable without directly accessing it.
// Setters:

// A setter is like putting money into your piggy bank through a special slot.
// You can't just open the piggy bank and throw money in; you have to use this slot.
// In programming, a setter lets you safely change the value of a private variable.
// Why use them?

Control:

// It's like having a piggy bank with a lock. You control who can see or change what's inside.
// In code, this helps prevent accidental changes to important data.
// Validation:

// Imagine your piggy bank only accepts certain coins. The slot (setter) checks each coin before letting it in.
// In programming, setters can check if a new value is valid before changing the variable.
// Flexibility:

// If you decide to change how your piggy bank works inside, as long as the slot and peephole stay the same, nobody needs to know.
// In code, you can change how data is stored or calculated without affecting other parts of the program.
// So, getters and setters are like a safe, controlled way to interact with the "piggy bank" of your object's private data, allowing you to look

### ACCOUNTS----------------------------------



class Transaction {
  constructor(amount, account) {
    this._amount = amount;
    this._account = account;
  }

  // Getters provide read-only access to private properties
  get amount() {
    return this._amount;
  }

  get account() {
    return this._account;
  }

  // Base commit method - will be overridden in subclasses
  commit() {
    this._time = new Date(); // Record the transaction time
    this.account.balance += this.value; // Update account balance
    this.account.addTransaction(this); // Add this transaction to account history
  }
}

class Withdrawal extends Transaction {
  // For withdrawals, value is negative
  get value() {
    return -this.amount;
  }

  // Override commit method to check for sufficient funds
  commit() {
    if (this.account.balance >= this.amount) {
      // If there's enough balance, proceed with the withdrawal
      this.account.balance += this.value; // Subtract the amount
      this.account.addTransaction(this); // Record the transaction
      return true; // Indicate success
    }
    return false; // Indicate failure if insufficient funds
  }
}

class Deposit extends Transaction {
  // For deposits, value is positive
  get value() {
    return this.amount;
  }
  // Note: Deposit uses the base commit method from Transaction
}

class Account {
  constructor(username) {
    this._username = username;
    this._balance = 0;
    this._transactions = [];
  }

  get username() {
    return this._username;
  }

  get balance() {
    return this._balance;
  }

  // Setter for balance includes validation
  set balance(newBalance) {
    if (newBalance >= 0) {
      this._balance = newBalance;
    } else {
      throw new RangeError('Balance cannot be negative');
    }
  }

  // Method to add a transaction to the account's history
  addTransaction(transaction) {
    this._transactions.push(transaction);
  }
}

// DRIVER CODE BELOW
const myAccount = new Account("snow-patrol");

// Attempt to withdraw 50.25 from an empty account
const t1 = new Withdrawal(50.25, myAccount);
console.log('Transaction 1 committed:', t1.commit()); // This will return false
console.log('Transaction 1:', t1);
public class Vehicle {
    protected String type;

    public void move() {
        // Method implementation
    }
}
const t2 = new Withdrawal(9.99, myAccount);
console.log('Transaction 2 committed:', t2.commit()); // This will also return false
console.log('Transaction 2:', t2);public class Vehicle {
    protected String type;

    public void move() {
        // Method implementation
    }
}
// Make a deposit
const t3 = new Deposit(125.00, myAccount);
console.log('Transaction 3 committed:', t3.commit()); // This will return true
console.log('Transaction 3:', t3);

console.log('Balance:', myAccount.balance); // Balance will now be 125.00

Steps on HOW THIS CODE WORKS

We define a base Transaction class with common properties and methods.

Withdrawal and Deposit classes extend Transaction, each implementing their own value getter.

Withdrawal overrides the commit method to check for sufficient funds before proceeding.

The Account class manages the balance and transaction history, using a setter for balance to prevent negative values.

In the driver code:

We create an account with zero balance.
We attempt two withdrawals, which fail due to insufficient funds.
We make a deposit, which succeeds.
We check the final balance, which should reflect only the deposit.