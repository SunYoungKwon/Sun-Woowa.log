# Level2 장바구니 리뷰

## 코드

- 다른 페이지에서 주문 목록으로 돌아가는 경우 캐싱 사용 고려하기, API 요소가 달라진 부분이 없다면 갱신하지 않는 로직 도입 고려.
- 항목 삭제 함수는 단건 삭제와 전체 삭제를 각각의 함수로 나누는 것이 더 명시적이며 수정에도 용이함.
- `if` vs `&&` [[리뷰링크]](https://github.com/woowacourse/react-shopping-cart/pull/8#discussion_r633068755)
  - `func && func()` vs `if(func) func()`
  - 최종적으로 boolean값으로 평가되는 `&&`연산자의 사용 용도를 생각했을 때, boolean값이 필요한 경우에 사용하는 것이 적절함.
  - 따라서 위와 같은 경우는 if문을 사용하는 것이 좋다.

### Markup

- props로 값이 넘어오지 않으면, 해당 값을 화면에 표시하기 위한 태그도 나타나지 않아야함.
- 두 가지 이상의 조건이 있다면 jsx에서 조건을 분기하는 것 보다 별개의 함수나 변수로 분리하는 것이 좋음. 마크업은 최대한 간단하게!
- image를 base64로 설정하면 기존에 상정하던 크기보다 커지고, js로 동작하기 때문에 로드 시 병렬처리가 되지 않는 이슈가 있으니, s3에 이미지를 업로드해서 받는 방식이 더 좋음. [[리뷰링크]](https://github.com/woowacourse/react-shopping-cart/pull/1#discussion_r632892139)
- 스낵바, 모달은 HTML 순서 상 하단에 배치.

- 반응형 화면 px값과 같이 여러곳에서 사용되는 css 값도 constants로 관리.
- 색상을 상수화해서 사용 시 통일성있게 white, black도 함께 상수화하기.
- props가 입력되지 않았을경우의 기본값을 설정해야 한다면 undefined나 null을 적용.
- `padding: 0;` `padding: 1px 1px;` 와 같이 줄여서 작성 가능하다면 줄여서 작성.
- z-index 값은 상수로 관리.
- props로 css 요소 하나하나 넘겨주는 경우 emotion을 사용 고려하기.
- `rgba(0, 0, 0, 0.3)`은 `rgba(#000, 0.3)`으로 작성할 수 있음.

### Setting

- testing-library와 @types는 dev-dependencies로!

## UX

- 장바구니 페이지 진입 시 장바구니 내 상품이 전체선택 상태를 기본으로 두기
  - 사용자가 구매할 상품을 선택한 후 바로 결제하는 흐름을 생각했을 때 사용성에 더 좋음
  - 사용자가 한 번 더 생각하고 상품을 선택하는 것 보다 바로 결제하도록 하는 것이 수익에 더 유리
- 주문목록은 최신 주문을 상단에 배치
- 목록이 길어지는 경우 페이징, 무한 스크롤 고려하기
- 로딩 시 모든 요소를 없애는 경우 화면이 깜빡이며 사용자에게 피로감을 줄 수 있음. 기존 화면을 유지하며 오버레이형식이나 toast 등을 사용하는 것이 좋음

---

[[TOP]](#level2-장바구니-리뷰) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
