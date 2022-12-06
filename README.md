#  The Mysteries of the This keyword and how it actually works

A lot of beginners struggle understanding how to use the this keyword and wonder why it gives wierd results sometimes. 

This article contains an explanation of how the this keyword actually works and i am confident you would use the this keyword in your code comfortably after reading through. 

# Now, Lets Begin !.

The "this" keyword is a special variable that is created for every Function by default. This means everytime a function is created, a 'this' keyword exists for it. 

Well... except for arrow functions that literally borrows a this keyword. details below

Now lets read this slowly and carefully, _"The this keyword points to (holds) the value of the owner of the function in which the this keyword is used"_.

# Illustration of how the this keyword works:

```
const tutorDetails = {
    firstName: "Abdurahman",
    lastName: "Aramide",
    job: "Teacher",
    birthYear: 1990,
    friends: ["Zayd", "Mariam", "Abdullah"],
    hasDriversLicense: true,
    about: function () {
        this.age = 2022 - this.birthYear;
        return console.log(`${this.firstName} is a ${this.age} year old ${this.job} and he has ${this.hasDriversLicense ? 'a' : 'no'} drivers' license`)
    }
}
tutorDetails.about();
```

The above code gives this result in the console:
```
Abdurahman is a 32 year old Teacher and he has a drivers' license
```

The example above works because tutorDetails is the owner of the function that calls the method, so the this keyword points to it and thats how we could get all those parameters.

An untamed definition: **The this keyword points to whatever is used to call the method/function in which it exists.**

I guess that makes the this keyword quite useful right? 😊

# Some Facts about the this keyword:

1. In strict mode if not assigned, the this keyword of a regular function points to undefined
2. In the global variable, the this keyword points to the Window object
3. Arrow functions do not get their own this keyword so they use the this keyword of their parent scope and it is said to use its lexical this keyword in this case. 

So it's safe to say "Do not use an arrow function if you would need to use the function's this keyword" like in the case of a method as shown in the ilustration above.

and also as a best pratice, **never use arrow functions in methods (methods are functions used inside an object).**

_I hope you enjoyed the read and most importantly found value. ❤_ 
