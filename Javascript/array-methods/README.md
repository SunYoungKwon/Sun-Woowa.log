# Javascript Array Methods

[HOME](https://github.com/SunYoungKwon/What-I-Studied-on-Woowacourse)

## 전체 목록

- [push](#push)
- [pop](#pop)
- shift
- unshift
- [fill](#fill)
- [forEach](#forEach)
- map
- filter
- reduce
- reduceRight
- [every](#every)
- [some](#some)
- includes
- find
- findIndex
- indexOf
- lastIndexOf
- concat
- slice
- copyWithin
- splice
- join
- toString
- toLocaleString
- sort
- reverse
- entries
- flat
- flatMap
- keys
- values

### push

- 배열의 끝에 하나 이상의 요소를 추가하고, 배열의 새로운 길이를 반환
- 여러 개의 요소를 한 번에 추가할 수 있음

```javascript
const arr = ["a", "b", "c"];
const arrLength = arr.push("d"); // 4
arr.push("e", "f"); // 6
console.log(arr); // ['a', 'b', 'c', 'd', 'e', 'f']
```

### pop

- 배열의 마지막 요소를 제거하고, 제거한 요소를 반환
- 빈 배열에서 사용하는 경우 `undefined` 반환

```javascript
const arr = ["a", "b", "c"];
console.log(arr); // ['a', 'b']
const removedItem = arr.pop(); // 'c'
```

### fill

- `fill(value, startIndex, endIndex)`
- 배열의 시작 인덱스부터 끝 인덱스의 이전까지 정적인 값 하나로 채움
- `startIndex` 인자의 기본 값은 0
- `endIndex` 인자의 기본 값은 `this.length`
- `this` 객체를 변형해 반환
- `value`에 객체를 받을 경우 참조복사해서 배열을 채움

```javascript
Array(3).fill(1); // [1, 1, 1]
const arr = [1, 2, 3, 4, 5];
arr.fill(0, 1, 3); // [ 1, 0, 0, 4, 5 ]
```

#### fill에 value로 객체를 넘긴다면?

```javascript
class Test {
  constructor(startNum) {
    this.arr = [startNum, startNum + 1, startNum + 2];
  }
}
```

```javascript
const testList = new Array(3).fill(new Test(1));
console.log(testList); // [{arr: [1, 2, 3]}, {arr: [1, 2, 3]}, {arr: [1, 2, 3]}]

// 위 콘솔을 찍어 본 후...

testList[0].arr[0] = 5;
console.log(testList); // [{arr: [5, 2, 3]}, {arr: [5, 2, 3]}, {arr: [5, 2, 3]}]
```

```javascript
const testList = new Array(3).fill().map(() => new Test(1));
console.log(testList); // [{arr: [1, 2, 3]}, {arr: [1, 2, 3]}, {arr: [1, 2, 3]}]

// 위 콘솔을 찍어 본 후...

testList[0].arr[0] = 5;
console.log(testList); // [{arr: [5, 2, 3]}, {arr: [1, 2, 3]}, {arr: [1, 2, 3]}]
```

### forEach

- `array.forEach((item, index, array) => ())`
- 주어진 함수를 배열 요소 각각에 실행
- `undefined` 반환
- 예외를 던지지 않고는 멈출 수 없음

```javascript
const arr = [1, 2, 3];
arr.forEach((element, index, arr) => (arr[index] = element + 1));
console.log(arr); // [2, 3, 4]
```

### every

- `array.every((item, index, array) => ())`
- Boolean 반환
  - 모든 요소에 대해 콜백함수가 truthy값을 반환하는 경우 `true` 반환
  - 어떤 요소에 대해 콜백함수가 falsy값을 반환하는 경우, 나머지 요소에 대해 콜백함수를 실행하지 않고 즉시 `false` 반환
  - 빈 배열에 대해 실행 시 `true` 반환

```javascript
[1, 2, 3].every((item) => item > 0); // true
[-1, 0, 1].every((item) => item > 0); // false
[0, 1].every((item) => item); // false
[].every((item) => item > 0); // true

[1, 2, 0, 3, 4].every((item) => {
  console.log(item);
  return item > 0;
});
// false
// 1
// 2
// 0
```

### some

- `array.some((item, index, array) => ())`
- Boolean 반환
  - 어떤 요소에 대해 콜백함수가 truthy값을 반환하는 경우, 나머지 요소에 대한 콜백함수를 실행하지 않고 즉시 `true` 반환
  - 모든 요소에 대해 콜백함수가 falsy값을 반환하는 경우 `false` 반환

```javascript
[-1, 0, 1].some((item) => item > 0); // true
[0, 1].some((item) => item); // true
[0].some((item) => item); // false
[].some((item) => item > 0); // false

[-1, 0, 1, 2].some((item) => {
  console.log(item);
  return item > 0;
});
// true
// -1
// 0
// 1
```

## 참고링크

- [[MDN] Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

[HOME](https://github.com/SunYoungKwon/What-I-Studied-on-Woowacourse)
