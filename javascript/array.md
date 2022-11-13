# Array

## array 안에 있는 항목 받아오기

```javascript
const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];

// Get Item from Array
console.log(daysOfWeek[5]); //sat
```

- 결과가 sat인 이유
  - 컴퓨터는 숫자를 0부터 센다.

## array에 element 추가 해주기 : push

맨 끝에 item을 추가 해준다.

```javascript
const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];

// Get Item from Array
console.log(daysOfWeek);

// Add one more day to the array
daysOfWeek.push("sun");

// push는 항목 하나 추가해주는 역할
console.log(daysOfWeek);
```

## array의 item 교체하기

```javascript
const toBuy = ["potato", "tomato", "pizza"];

console.log(toBuy[2]); // pizza
toBuy[2] = "water";
console.log(toBuy[2]); // water
```
