# this

- [하브루타 스터디 2기 3주차 - this](https://github.com/woowacourse-fe-study/havruta-frontend/discussions/17)

## this 바인딩 우선순위

(뒤로 갈 수록 우선순위가 높음)

- 기본 바인딩
  - 기본적으로 전역 객체에 컨텍스트가 바인딩된다.
  - 하지만 strict모드에서는 `undefined` 이다.
- 암시적 바인딩
  - 함수 호출 시 객체의 프로퍼티에 접근하여 실행(`obj.method()`)
  - 호출부의 객페 프로퍼티로 접근하면, 이 객체를 this와 바인딩
- 명시적 바인딩
  - call, apply, bind 사용
  - bind(null)을 사용하면 커링 가능
- `new` 바인딩
  - new를 사용하면 새로운 객체를 반환하는데, 이때 반환되는 값이 `this`

## 화살표함수의 this

- 화살표함수의 this는 상위 스코프가 가리키는 this와 같음
- JS는 렉시컬 스코프를 따르므로 함수를 선언한 시점에 상위 스코프가 결정됨

## `use strict`

- 기본 바인딩의 주체가 전역객체(window or global)가 아닌 `undefined`
- class문법 내부는 기본적으로 엄격모드가 적용됨

```javascript
const Test = class {
  func() {
    console.log(this);
  }
};

const A = new Test().func;
A(); // undefined
```

---

[[TOP]](#this) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
