# React Testing Library

## 각각의 `test()` 또는 `it()`이 연속된 동작을 테스트

### 문제

예약 기능을 테스트 하며, 메인 페이지 렌더링 -> 예약할 공간 선택 후 예약 페이지 진입 -> 예약 추가를 순서대로 테스트 하고 싶었다. 하지만, 각 단계를 서로다른 `it()`으로 감싸자 각 동작이 연결되지 않았다.

### 해결

[Testing Library](https://testing-library.com/)는 각각의 테스트 동작 이후(Jest의 `afterEach`와 같은 타이밍)에 자동으로 Cleanup을 수행한다.
이 동작을 skip하도록 설정하면 위의 문제를 해결할 수 있다.

#### 1) `shell script`에서 설정하기

```
cross-env RTL_SKIP_AUTO_CLEANUP=true jest
```

#### 2) `jest config`에서 설정하기

```
{
  // ... other jest config
  setupFiles: ['@testing-library/react/dont-cleanup-after-each']
}
```

## 참고

- [Skipping Auto Cleanup - Testing Library](https://testing-library.com/docs/react-testing-library/setup/#skipping-auto-cleanup)

---

[[TOP]](#react-testing-library) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
