# prop-types

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

## prop-types와 Typescript

- 대부분의 경우는 둘 다 사용했을 때, 큰 이점을 가지지 못한다.
- 타입스크립트는 컴파일 타임에 타입을 검사하기 때문에, 사용자의 동적인 입력에 따른 오류를 검사하지 못한다.
- prop-types는 동적으로 타입을 검사하기 때문에, 사용자가 지정된 타입에 맞지 않는 입력을 하는 경우도 검사할 수 있다.
- [[참고] PropTypes in a TypeScript React Application - stack overflow](https://stackoverflow.com/questions/41746028/proptypes-in-a-typescript-react-application)

## 참고

- [PropTypes와 함께 하는 타입 확인 - React 공식문서](https://ko.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)
- [prop-types - npm](https://www.npmjs.com/package/prop-types)

---

[[TOP]](#prop-types) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
