# props-types

## element vs elementType

### element

```javascript
// 상위 컴포넌트
export const Container = () => {
  return (
    <div>
      <Content element={<Element />} />
    </div>
  )
};

---

// 하위 컴포넌트
export const Content = ({ element }) => {
  return (
    <div>
      {element}
    </div>
  )
}
```

### elementType

```javascript
// 상위 컴포넌트
export const Container = () => {
  return (
    <div>
      <Content Element={Element} />
    </div>
  )
};

---

// 하위 컴포넌트
export const Content = ({ Element }) => {
  return (
    <div>
      <Element />
    </div>
  )
}
```

## Typescript를 사용하면 prop-types는 필요없을까?

```
No!!!
타입스크립트는 컴파일 타임에 타입을 검사하기 때문에, 사용자의 동적인 입력에 따른 오류를 검사하지 못한다.
prop-types는 동적으로 타입을 검사하기 때문에, 사용자가 지정된 타입에 맞지 않는 입력을 하는 경우도 검사할 수 있다.

=> 둘의 역할이 다르기 때문에 둘 다 사용하는 것이 좋다.
```

## 참고

- [PropTypes와 함께 하는 타입 확인 - React 공식문서](https://ko.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)
- [prop-types - npm](https://www.npmjs.com/package/prop-types)

---

[[TOP]](./#prop-types) | [[HOME]](https://github.com/SunYoungKwon/What-I-Studied-on-Woowacourse#-what-i-studied-on-woowacourse)
