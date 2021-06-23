# CORS(Cross-Origin Resource Sharing)

- SOP(Same Origin Policy): 같은 출처에서만 리소스를 공유할 수 있다!
- 출처: Protocol + Host + Port
  - IE의 경우 Port를 검사하지 않음
  - 브라우저는 문자열 값이 서로 같은지로 동일출처인지 판단함
- Preflight Request: OPTIONS 메서드를 사용하는 예비 요청. 본 요청을 보내도 안전한지 확인.
  - 서버가 CORS를 인식하고 핸들링 할 수 있는지 확인하기 위해 필요
- Simple Request: Preflight요청 없이 바로 본 요청을 보내고, 브라우저는 응답 헤더의 값으로 CORS 정책 위반 여부를 확인
  - 요청의 메소드는 GET, HEAD, POST 중 하나
  - 헤더는 Accept, Accept-Language, Content-Language, Content-Type, DPR, Downlink, Save-Data, Viewport-Width, Width만 사용 가능
  - Content-Type를 사용하는 경우, application/x-www-form-urlencoded, multipart/form-data, text/plain만 허용
- Credentialed Request: 인증 관련 헤더를 포함할 때 사용

## 참고링크

- [[10분 테코톡] 나봄의 CORS](https://www.youtube.com/watch?v=-2TgkKYmJt4)
- [CORS는 왜 이렇게 우리를 힘들게 하는 걸까? - 문동욱님](https://evan-moon.github.io/2020/05/21/about-cors/)

---

[[TOP]](#corscross-origin-resource-sharing) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
