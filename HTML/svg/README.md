# svg

## 비트맵 vs 벡터

- 비트맵
  - '레스터 이미지'라고도 함
  - 픽셀로 이루어진 이미지
  - 확대 시 해상도에 따라 이미지가 깨짐
  - 주로 사진에 사용
  - 확장자 : jpg, png, gif, bmp 등
  - 대표적인 편집 프로그램 : 포토샵
- 벡터
  - 점과 선, 면으로 이루어져, 그 방향성과 연결을 통해 이미지를 표현
  - 아무리 확대해도 이미지가 깨지지 않음
  - 비트맵 이미지로 변환 가능
  - 주로 간단한 로고 및 아이콘에 사용
  - 확장자 : svg
  - 대표적인 편집 프로그램 : 일러스트레이터

## viewport & viewBox

```html
<svg
  viewBox="0 0 100 100"
  width="100"
  height="100"
  xmlns="http://www.w3.org/2000/svg"
>
  <circle cx="50" cy="50" r="40" />
</svg>
```

### viewport

- 화면에 보여질 영역
- width, height로 결정됨
- 도형이 viewport 영역을 넘어서면 화면에 나타나지 않고 잘림

### viewBox

- 도형을 그릴 영역
- 도형요소의 좌표값은 viewBox를 기준으로 함
- `min-x min-y width height` 순서로 작성
  - `min-x min-y` : 좌픅상단을 기준점으로 한 viewBox의 시작 좌표
  - `width height` : viewBox의 사이즈

## 도형 요소

- [`<line>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/line) : (x1, y1)좌표와 (x2, y2)좌표를 이어 선을 그림
  - `stroke` attribute : 선 색을 지정, 지정하지 않을 경우 화면에 나타나지 않음
- [`<polyline>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/polyline) : 나열된 (x, y)를 순서대로 연결하여 다각선을 그림
- [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) : width와 height를 지정하여 사각형을 그림
- [`<polygon>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/polygon) : 나열된 (x, y)를 순서대로 연결하여 다각형을 그림
  - `<polyline>`과 유사함. `<polyline>`은 열린 도형을 그릴 수 있으나 `<polygon>`은 닫힌 도형만 그릴 수 있다는 차이가 있음.
- [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) : 가로, 세로 크기를 지정하여 타원을 그림
- [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/path) : M(move to), Z(close path)와 같은 키워드와 좌표값을 이용하여 자유로운 형태의 도형을 그림
  - [그 외 다양한 키워드 - w3.org](https://www.w3.org/TR/SVG/paths.html)

## 리액트에서 사용하기

[SVGR](https://react-svgr.com/)(CRA는 기본으로 설정되어 있음)을 통해 ReactComponent처럼 import해서 사용할 수 있다.

```jsx
import { ReactComponent as Icon } from './assets/icon.svg';

const Test = () => {
  return (
    <div>
      <Icon />
    </div>
  );
};

export default Test;
```

[주의] SVGR을 사용하여 svg이미지를 import하는 경우 `viewBox` 속성을 제거하는 것이 기본 설정이다. viewBox 속성을 표함하고 싶다면 `removeViewBox: false`를 설정해주면 된다.

```javascript
// webpack.config.js

{
  test: /\.svg$/,
  use: [
    {
      loader: '@svgr/webpack',
      options: {
        svgoConfig: {
          plugins: {
            removeViewBox: false,
          },
        },
      },
    },
    'url-loader',
  ],
}
```

---

[[TOP]](#svg) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
