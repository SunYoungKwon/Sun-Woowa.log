# Module

모듈이란, 분리된 코드의 조각이며 시스템을 이루는 논리적인 일부분이다.

## 모듈화

- 스코프
- 정의
- 사용
- **모듈**은 독립적인 **스코프**를 가져야하며, 모듈을 **정의** 즉 만들수 있어야 하고, 정의된 모듈을 가져다 **사용**할 수 있어야한다

## 모듈시스템 종류

### CommonJS

- JavaScript를 브라우저 뿐 아니라 Java나 Python같이 범용적인 언어로, 특히 서버사이드 언어로 사용하기 위해 등장
- 이를 위해서는 서로 호환되는 표준 라이브러리나 다른 모듈을 가져오는 표준 방법 등이 필요
- `module.exports`를 통해 모듈을 정의하고, `require` 문법을 통해 정의된 모듈을 가져다 사용
- 모든 파일이 로컬에 존재하여 바로 불러올 수 있음을 전제로 하며, 동기적으로 동작
- node.js에서 사용

### AMD(Asynchronous Module Definition)

```javascript
define(id?, dependencies?, factory);

require([modulePath], function(module)(){
  // module을 활용하는 실제 코드
});
```

- 비동기 상황에서 모듈을 사용하기 위해 등장
- 처음에는 CommonJS와 논의했으나 JavaScript를 브라우저 밖에서 사용하고 싶었던 CommonJS 그룹과 브라우저 내의 실행에 중점을 둬 비동기 모듈 사용을 원했던 AMD 그룹은 서로 합의점을 찾지 못함
- `define`을 통해 모듈을 정의하고 `id`에는 모듈을 식별할때 사용할 인수를, `dependencies`는 모듈의 의존성을 나타내는 배열을, `factory`에는 모듈의 실제 구현을 작성
- `define`함수가 파일 스코프의 역할을 대신한다고 볼 수 있음
- dojo toolkit과 require.js에서 사용

### UMD(Universal Module Definition)

- 서로 합의를 이루지 못하고 갈라선 CommonJS와 AMD 모두를 지원하고 싶은 경우 사용

### EMS(EcmaScript modules)

```javascript
export default App;

---

import App from './App.js'
```

- 2015년 JavaScript에 정식 채택된 모듈 시스템
- `export`를 통해 모듈을 내보내고 `import`를 통해 모듈을 가져와 사용

## 모듈 번들러

모듈을 통해 스코프를 나눠 편리하게 프로그래밍 할 수 있게 되었다. 모듈이 나눠지고 웹이 많은 기능을 포함하게 되면서 파일의 개수도 많아졌다. 문제는 모든 파일을 네트워크 통신을 통해 가져와야한다는 것이다. 이로인해 모듈 번들러가 필요해졌다.

### 웹팩(webpack)

- 웹팩에서는 모든 파일(js, css, 이미지, 폰트 등)을 모듈로 취급
- 웹팩 설정
  - mode : 개발모드, 프로덕션모드 등으로 나눌 수 있음
  - entry : 모듈의 시작점, 일반적으로 index.js
  - output : 번들링된 파일을 저장할 위치, 일반적으로 dist 또는 build라는 이름의 폴더를 사용함

#### 로더(loader)

- js가 아닌 웹 자원을 모듈로 변환하는 도구
- 자주 사용하는 로더
  - css-loader : 자바스크립트에서 CSS파일을 모듈로서 가져올 수 있게 함
  - style-loader : 자바스크립트로 들어간 CSS를 HTML에 넣어 브라우저 렌더링 시 적용
  - file-loader : 이미지를 모듈로 사용할 수 있게 함

#### 플러그인(plugin)

- 난독화, 특정 문자열 치환과 같은 번들된 결과물의 형태를 바꿈(후처리)
- 예시
  - DefinePlugin : 개발용 api와 배포용 api 주소를 서로 다르게 설정하는 것과 같이 환경 의존적인 정보를 관리함

#### 바벨(babel)

- 트랜스파일러
- 인간들의 언어를 섞어 서로 소통하지 못하게 함으로써 바벨탑을 쌓기를 막았다는 이야기에서 유래한 이름
- 서로 다른 브라우저 스펙으로 인해 하나의 프로젝트 코드로 모든 브라우저를 커버하지 못하게되는 크로스 브라우징 문제를 해결
- 코드 변환 3단계
  1. 코드를 각 토큰으로 분해
  2. ES5 스펙으로 변환
  3. 변환된 코드 출력

## 참고

- [[테코톡] 모듈 번들러와 빌드도구](https://www.youtube.com/watch?v=9b89f21Sizs)

---

[[TOP]](#Module) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
