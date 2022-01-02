# SocketIO

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 라이브러리](#라이브러리)

#### [3. 계층](#계층)

#### [4. Low Level EngineIO](#Low-Level-EngineIO)

- 정의
- 특징
- 기능

#### [5. High Level SocketIO](#High-Level-SocketIO)

- 기능

#### [6. Server](#Server)

- 명칭
- 초기 설정 방법
- 이벤트
- API

#### [7. Client](#Client)

- 초기 설정 방법
- 이벤트

#### [8. Socket](#Socket)

- 이벤트
- API

#### [9. Namespace](#Namespace)

- API

<br>

---

<br>

## 정의

- 웹소켓을 이용해서 이벤트 기반으로 클라이언트와 서버의 실시간 양방향 통신 기능을 제공하는 라이브러리

<br>

## 라이브러리

- socket.io
- socket.io-client

<br>

## 계층

### Low Level

- Engine.IO

### High Level

- Socket.IO

<br>

## Low Level EngineIO

### 정의

- 서버와 클라이언트간의 Low Level의 연결을 설정하는 Socket.IO 내부의 엔진

### 특징

- UX 향상
- 서버 성능 향상

### 기능

#### 전송

- HTTP long-polling (Polling)
  - 서버 데이터 수신 목적의 Long-Running GET 요청
  - 서버로의 데이터 송신 목적의 Short-Running POST 요청
- Websocket
  - 서버와 클라이언트간의 양방향 통신과 저지연 통신 채널을 제공하는 웹소켓 통신

#### 핸드쉐이크

<br>

## High Level SocketIO

### 기능

- Automatic Reconnection
- Packet Buffering
- Acknowledgments
- Namespace
  - 소켓들의 묶음
- Room
  - 네임스페이스의 하위 개념

<br>

## Server

### 명칭

- io

### 초기 설정 방법

#### Standalone

```
import { Server } from "socket.io";

const PORT_NUM = 3000;

const server = app.listen(PORT_NUM, ...);
const io = new Server(server, { ...options });
io.on("connection", (socket) => {
  ...
});
```

#### HTTPS Server

```
import { readFileSync } from "fs";
import https from "https";
import { Server } from "socket.io";

const PORT_NUM = 3000;

const options = {
  ca: fs.readFileSync("/...");
  key: fs.readFileSync("/...");
  cert: fs.readFileSync("/...");
}
const server = https.createServer(options, app);
const io = new Server(server, { ...options });
io.on("connection", (socket) => {
  ...
});
server.listen(PORT_NUM, ...);
```

### 이벤트

- initial_headers
- headers
- connection error
  - 0
    - Transport Unknown
  - 1
    - Session ID Unknown
  - 2
    - Bad Handshake Method
  - 3
    - Bad Request
  - 4
    - Forbidden
  - 5
    - Unsupported Protocol Version
- connection
  - 새로운 연결이 발생하는 경우 이벤트
  - = connect
  - 콜백함수
    - (socket) => {...}
- new_namespace
  - 새로운 네임스페이스가 생성되는 경우 이벤트
  - 콜백함수
    - (namespace) => {...}

### API

- new Server(server, { options })
  - IO 생성 함수
- on(eventName, listener)
  - IO에 이벤트와 리스너 추가 함수
- of(namespaceName)
  - IO의 해당 네임스페이스 객체 반환 함수
- in(roomName)
  - IO의 해당 룸 객체 반환 함수
- sockets
  - 메인 네임스페이스 반환 객체
  - = of("/")
- close(callback)
  - IO와 모든 클라이언트 연결 중단 함수
- socketsJoin(roomName)
  - IO의 모든 소켓을 해당 룸에 추가하는 함수
- socketsLeave(roomName)
  - IO의 모든 소켓을 해당 룸에서 제거하는 함수
- disconnectSockets()
  - IO의 모든 소켓들의 연결 중단 함수
- fetchSockets()
  - IO의 모든 소켓 객체 반환 함수
  - 비동기

<br>

## Client

### 초기 설정 방법

#### 동일 도메인

- const socket = io()

#### 다른 도메인

- const socket = io(serverURL)

### 이벤트

- connect
  - 서버와 처음 연결되거나 다시 연결되는 경우 이벤트
- connect_error
  - 저 레벨 단계의 연결이 안 된 경우나 서버의 미들웨어로 인해 연결이 거부된 경우 이벤트
- disconnect
  - 연결이 중단된 경우 이벤트
  - (reason) => {...}
  - reason
    - io server disconnect
    - io client disconnect
    - ping timeout
    - transport close
    - transport error

<br>

## Socket

### 이벤트

- disconnect
  - 소켓 연결이 중단되는 경우 이벤트
  - (reason)) => {...}
  - reason
    - server namespace disconnect
    - client namespace discconect
    - server shutting down
    - ping timeout
    - transport close
    - transport error
- disconnecting
  - 소켓 연결이 중단되기 전 이벤트
  - (reason) => {...}

### API

- id
- rooms
  - 룸의 셋 반환
- client
- request
  - 요청 헤더 접근 용이
- handshake
- use(callback)
  - 미들웨어 등록 함수
- emit(eventName, { data })
  - 해당 이벤트로 데이터 전송 함수
- on(eventName, listener)
  - 소켓에 이벤트와 리스너 추가 함수
- join([roomNames])
  - 소켓을 룸에 추가하는 함수
- leave(roomName)
  - 소켓을 룸에서 제거하는 함수
- to(roomName)
  - 네임스페이스에서 해당 룸만의 브로드캐스트 객체 반환 함수
  - = in(roomName)
- except(roomName) - 네임스페이스에서 해당 룸을 제외한 브로드캐스트 객체 반환 함수
- timeout(msec)
  - msec를 초과한 소켓 객체 반환
- disconnect(flag)
  - true일 경우 소켓 연결 중단
  - false일 경우 소켓의 네임스페이스 연결 중단

<br>

## Namespace

### API

- name
- sockets
- to(roomName)
  - 네임스페이스에서 해당 룸만의 브로드캐스트 객체 반환 함수
  - = in(roomName)
- except(roomName) - 네임스페이스에서 해당 룸을 제외한 브로드캐스트 객체 반환 함수
- emit(eventName, { data })
  - 해당 이벤트로 데이터 전송 함수
- allSockets()
  - 네임스페이스에 연결되어 있는 모든 소켓ID 배열 반환 함수
- use(callback)
  - 미들웨어 등록 함수

<br>
