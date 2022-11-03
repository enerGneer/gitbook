---
description: 어떤 코드를 캡슐화하는 기능.
---

# Function

```javascript
function sayHello() {
  console("Hey enerG! Cheer Up!");
  // 이 안에 있는 요소를 반복해서 실행할 수 있다.
}

sayHello();
```

## function에 data 보내기

```javascript
function sayCheerUp(cheerName) {
  console.log("Hey " + cheerName + "! Cheer Up!");
}

sayCheerUp("enerG"); // Hey enerG! Cheer Up!

console.log(cheerName); // Undefined
```

### Place holder

```javascript
function plus(a, b) {
  console.log(a + b);
}

plus(8, 10); // 18 (a=8, b=10)

function divide(firstNumber, secondNumber) {
  console.log(firstNumber / secondNumber);
}

divide(100, 20); // 5
```

* a와 b, firstNumber와 secondNumber는 단순한 place holder다.

## Object 안에서 function 사용하기

```javascript
const player = {
  name: "nico",
  sayHello: function (otherName) { // 이 부분이
    console.log("Hello~ " + otherName + "! Nice to meet you!");
  },
};

player.sayHello("enerG"); // Hello~ enerG! Nice to meet you!
```

## Return

```javascript
const age = 90; // 1
function calculateKrAge(ageOfForeigner) { // 3
  return ageOfForeigner + 2; // 4
}

const KrAge = calculateKrAge(age); // 2 // 5 // 6
console.log(KrAge); // 7
```

<details>

<summary>details</summary>

1. `age` 의 90이라는 값을 아래의 calculateKrAge(_age_)에서 가져간다.
2. calculateKrAge(90)이 된다.
3. 90이라는 값을 `ageOfForeigner`에 보내준다.
4. 함수 내부 `ageOfForeigner`에서 90을 받아 90 + 2를 실행한다. = 92
5. 이것을 반환 return 해서 밖에 있는 calculateKrAge의 값이 92가 된다.
6. const KrAge = 92가 된다.
7. 콘솔로그로 도출한 결과 역시 92가 된다.

* 이렇게 KrAge라는 variable이 function의 return value를 가지게 된다.

</details>

### Return하는 순간 function은 작동을 멈춘다

```javascript
const calculator = {
  add: function (a, b) {
    console.log("hello!"); // 작동한다
    return a + b; // return한다
    console.log("bye bye"); // 작동하지 않는다
  },
};
```

#### return의 효용 : 상호의존성

```javascript
const calculator = {
  add: function (a, b) {
    return a + b;
  },
  minus: function (a, b) {
    return a - b;
  },
  times: function (a, b) {
    return a * b;
  },
  divide: function (a, b) {
    return a / b;
  },
  power: function (a, b) {
    return a ** b;
  },
};

const plusResult = calculator.add(10, 2); //12
const minusResult = calculator.minus(plusResult, 5); //7
const timesResult = calculator.times(10, minusResult); //70
const divideResult = calculator.divide(timesResult, minusResult); //10
const powerResult = calculator.power(divideResult, minusResult); //10000000
```



## ETC

* `prompt` : 팝업 창을 띄운다. 따라서 요즘에는 잘 쓰이지 않는 방식이다.
* `parseInt` : string을 number로 바꿔준다.
* `typeof variable` : variable의 datatype을 확인한다.
