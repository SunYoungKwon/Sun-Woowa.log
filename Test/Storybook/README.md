# Storybook

## 사용목적

- 컴포넌트의 state 별 렌더링 결과를 테스트
- 서버나 앱 전체를 실행하지 않고 컴포넌트 제작
- 개발하는 동안 컴포넌트의 UI가 망가지지 않는지 확인 가능

## 시작하기

### 구현 순서(공식 튜토리얼에 따름)

1. 구현할 컴포넌트에서 테스트에 필요한 상태 정리(요구사항 도출)
2. 컴포넌트 구현
3. 스토리 파일 설정
4. 구현된 UI 확인

### `export default`

```js
export default {
  component: TestComponent,
  title: "TestComponent",
  argTypes: { onClick: { action: "clicked" } },
  decorators: [(story) => <div style={{ padding: "3rem" }}>{story()}</div>],
};
```

- component : 해당 컴포넌트
- title : Storybook 앱의 사이드바에서 컴포넌트를 참조하는 방법
- excludeStories : Storybook에서 스토리를 내보낼 때 렌더링에서 제외하는 것
- [argTypes](https://storybook.js.org/docs/react/api/argtypes) : 각각의 스토리에서 인수(args)의 행동 방식을 명시
- [parameters](https://storybook.js.org/docs/react/writing-stories/parameters)
- [decorators](https://storybook.js.org/docs/react/writing-stories/decorators) : 스토리에 임의의 wrapper를 제공

### `Template.bind()`

```js
const Template = (args) => <TestComponent {...args} />;

export const Default = Template.bind({});
Default.args = {
  id: 1,
  title: "Test Component!",
};
```

- 함수를 복사하기 위해 사용
- `bind()`를 통해 함수를 복사하여 각 스토리가 고유한 속성을 갖지만 동시에 동일한 구현을 사용하도록 만듦

## 함께 사용할 수 있는 도구

- [스냅샷 테스트 에드온](https://github.com/storybooks/storybook/tree/master/addons/storyshots)
- Jest - 단위테스트

## 참고

- [React를 위한 Storybook 튜토리얼](https://storybook.js.org/tutorials/intro-to-storybook/react/ko/get-started/)

---

[[TOP]](./#Storybook) | [[HOME]](https://github.com/SunYoungKwon/What-I-Studied-on-Woowacourse#-what-i-studied-on-woowacourse)
