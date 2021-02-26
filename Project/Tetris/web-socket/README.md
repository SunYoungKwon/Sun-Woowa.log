# 웹 소켓(Web Socket)

## 웹 소켓의 특징

1. 양방향 통신(Full-Duplex)
2. 실시간 네트워킹(Real Time-Networking)

## Handshaking 메세지 교환

1. 클라이언트 -----hadshake 요청 메세지----> 서버
2. 클라이언트 <----hadshake 응답 메세지----- 서버
3. 클라이언트 -----data payload frames----> 서버
4. 클라이언트 <----data payload frames----- 서버
5. 클라이언트 -----close frame----> 서버
6. 클라이언트 <----close frame----- 서버

- 최초 접속에만 http 프로토콜 위에서 hadshaking를 하기 때문에 http header를 사용
- 웹 소켓을 위한 별도의 포트는 없으며, 기존 포트(http-80, https-443)을 사용
- ws는 http 기반, wss는 https 기반
- 교환 가능한 메세지는 텍스트(text)와 바이너리(binary)

## 웹 소켓 통신을 위한 기술

- WebSocket API
  - 웹 브라우저간 실시간 양방향 통신환경 제공
- SockJS
- WebSocketClient(안드로이드)

## 웹 소켓 통신과 유사한 기술

- Polling
  - 클라이언트에서 일정 주기마다 요청을 보내고 서버는 요청이 온 당시의 상태를 응답
  - 실시간 반영이 중요한 서비스에 적합하지 않음
  - 서버에 변화가 없더라도 요청에 응답하므로 불필요한 트레픽이 발생
- Long Polling
  - 클라이언트에서 요청을 보내면 서버는 기다렸다가 이벤트가 발생했을 때 응답. 클라이언트는 응답을 받고 다시 요청을 보냄
  - 실시간 반응이 가능
  - 불필요한 트래픽이 발생하지 않음
  - 서버에 이벤트가 잦다면 순간적인 과부화가 발생할 수 있음
- Streaming
  - 이벤트 발생 시 응답을 내려주지만 응답을 완료시키지 않고 연결을 계속 유지
  - 매번 다시 요청을 보내지 않아도 됨
  - 연결 시간이 길어지면 연결의 유효성 관리의 부담이 발생

## 링크

- [[MDN] WebSocket](https://developer.mozilla.org/ko/docs/Web/API/WebSocket)
- [웹 소켓 통신(Web Doorket) - Joker](https://caileb.tistory.com/185)
- [websocket, socket.io를 이용한 양방향 통신 - zych1751](http://www.secmem.org/blog/2019/08/17/websocket-socketio/)
- [socket.io](https://socket.io/)
