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

