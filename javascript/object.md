# Object

### Object의 표현 방식 두 가지

```javascript
const player = {
  name: "nico",
  points: 10,
  fat: true,
};

console.log(player.name); // 1번째 방식
console.log(player["name"]); // 2번째 방식
```

존재하는 항목 추가, 업데이트 가능
