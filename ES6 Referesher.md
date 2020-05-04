# React Course with Mosh

---

## Spread (ES6 Refresher Video10)
```javascript
const first = [1,2,3]
const second = [4,5,6]
// combined = [1,2,3,”a”,4,5,6]
const combined = […first, “a”, …second] 
// combined2 = [1,2,3,4,5,6] 
const combined2 = first.concat(second)
```
```javascript
const first = { name: "Onur Can" }
const second = { surname: "Avci" }
// combined = { name = “Onur Can”, surname: “Avci”,  location: “Giresun” }
const combined = { ...first, ...second, location: "Giresun" }
```
## Classes (Video 11)
If we want to create more than one person, 
we should write codes like this
```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  walk() {
  console.log("walk");
  }
}
const person1 = new Person("Onur Can");
const person1 = new Person("Batuhan");
```
instead of writing like this
```javascript
const person1 = {
  name: "Onur Can",
  walk() {
    console.log("walk");
  }
};
const person2 = {
  name: "Batuhan",
  walk() {
    console.log("walk");
  }
};
```
## Inheritance (Video 12)
Let's imagine that we create a teacher class and this class have same properties in person class. We have to inherit from properties of person to teacher like this.
```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  walk() {
  console.log("walk");
  }
}
class Teacher extends Person{
  // Teachers have name bacuse of they are person too
  // But all persons do not have degree
  constructor(name, degree) {
    super(name);
    this.degree = degree;
  }
  // Imagine that just teachers have teach property
  teach() {
  console.log("teach");
  }
}

const teacher = new Teacher("Onur Can", "MSc");
teacher.teach();
```
## Modules (Video 13)
A class can be in different files, and we need to call in a file 
```javascript
import { Teacher } from "./teacher";
import { Person } from "./person";

const teacher = new Teacher("Onur Can", "MSc");
const person = new Person("Burak");
teacher.teach();
person.walk();
```
## Named and Default Exports (Video 14)
If we only have an object in a file, we exports as a default exports like this;
```javascript
import { Person } from "./person";

// Exports a function 
export function promote(){}

// We have just an object 
export default class Teacher extends Person{
  constructor(name, degree) {
    super(name);
    this.degree = degree;
  }
  teach() {
  console.log("teach");
  }
}
```
and we imports default exports like this
```javascript
import Teacher, { promote } from "./teacher";

const teacher = new Teacher("Onur Can", "MSc");
teacher.teach();
```

