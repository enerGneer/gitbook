# Conditional

```javascript
if (true) {
  //body
} else {
  //else body
}
```

* ()안의 조건이 true면 body를 실행한다.
* false라면 else body를 실행한다.

## operater

* `&&` = and
* `||` = or
* `===` = equal
  * `=` 과는 다르다. a = b는 하나의 value를 할당한다는 뜻이다.
* `!==` = not

#### example

```
const age = parseInt(prompt("how old are you?"));

if (isNaN(age) || age < 0) {
  console.log("Please enter a real positive number.");
} else if (age < 20) {
  console.log("You are too young!");
} else if (age >= 20 && age <= 50) {
  console.log("You can drink!");
} else if (age >= 50 && age <= 80) {
  console.log("You should exercise!");
} else if (age === 100) {
  console.log("You are wise!");
} else if (age > 80) {
  console.log("You can do whatever you want!");
}
```
