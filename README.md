<div align="center">
  <img src="https://raw.githubusercontent.com/hey-dudegg/OnCore-Project/5bd5e22f175f356d9802a76fb1d18b7bc0a91c4d/frontend/src/assets/NewBanner.svg">
  <h2>동료들과 함께 알고리즘을 학습하고 소통할 수 있는 플랫폼</h2>
  <h4>🗝️ KeyWords <h4/>
  <p> #Algorithm #CodeMirror #CRDT #TLdraw #WebRTC #Socket #ClovaAI</p>
  <br>
  <p>사용 기술 스택</p>
    <img src="https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=NestJS&logoColor=white"/>
    <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
    <img src="https://img.shields.io/badge/TailwindCSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white"/>
    <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=MongoDB&logoColor=white"/>
    <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=white"/>
    <img src="https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white"/>
    <br>
    <img src="https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=Socket.io&logoColor=white"/>
    <img src="https://img.shields.io/badge/Artillery-FF4500?style=flat-square&logo=Artillery&logoColor=white"/>
    <img src="https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=Swagger&logoColor=white"/>
    <img src="https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=Postman&logoColor=white"/>
  <div align="center">
    
  </div>
  <br>
  <a href="https://youtu.be/dqOzQJm5DQMk">🎤 발표영상 보기 </a>
</div>

---

# 기획의도
알고리즘 코어타임을 온라인으로 계속 이어나가기 위해 제작

# 서비스 소개
알고리즘 문제를 실시간으로 협업하여 풀 수 있는 웹 서비스

# 참고
**(담당)** 표시가 있는 파트가 김동준 담당 파트입니다.

# 아키텍처
<details>
<summary> 
  🔗 서버 아키텍처</summary>

  ![7](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/6d6448ce-af8a-4b27-b481-8b5c692287ab)
</details>

# 기능 소개
### 📝 화이트 보드 (담당)
- TLdraw와 소켓.IO 라이브러리 활용하여 다자간이 실시간 브레인스토밍 보드 구현

| ![3](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/11c4939c-3b3e-4705-b3a3-118c0ca28eec)|
| ----------------------------------------------------------------------------- |
| 화이트 보드에서 실시간으로 아이디어 공유하기                                  |

      
<details>
<summary> 
⚙️ 코드 에디터</summary>
- Yjs와 CodeMirror를 사용하여 실시간 동시 편집이 가능합니다.
   
|![2](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/21937151-3e82-4b11-990d-6d5da2de2569)|
| ----------------------------------------------------------------------------- |
| 코드 에디터에서 실시간으로 코드 편집하기                                      |
</details>

<details>
<summary> 
🧑‍🧑‍🧒‍🧒 화상 채팅</summary>
- WebRTC와 PeerJS를 사용하여 P2P 스트리밍을 구현하였습니다.
- Socket.IO를 통해 신호 교환을 처리하고, 사용자가 특정 방에 접속할 때 소켓은 방 참가자를 관리하고 신호 메시지 처리를 통해 P2P 연결을 설정합니다.
- 직접 연결된 메쉬 네트워크를 통해 오디오와 비디오를 스트리밍합니다.

| ![4](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/35ea9b16-1dfe-4511-8526-8cb121b29984)|
| ----------------------------------------------------------------------------- |
| 화상 채팅을 통해 동료와 소통하기                                              |
</details>

<details>
<summary>
💬 채팅 + AI 찬스</summary>
- Redis Pub/Sub과 소켓을 사용하여 사용자 간 실시간 채팅이 가능합니다.
- Clova AI LLM을 통합하여 사용자와 AI 간 상호작용을 통해 효율적으로 협업할 수 있습니다.

| ![5](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/32327c19-3e77-4131-9011-a4e6b494043c)|
| ----------------------------------------------------------------------- |
| 사용자와 AI와의 실시간 채팅                                              |
</details>

<details>
<summary>
📝 문제 보기 (백준 알고리즘)</summary>
- Puppetter와 Chromium 브라우저를 사용하여 필요한 정보를 수집합니다.
- Cheerio를 통해 태그를 파싱하고 제거하며, Redis 캐시를 활용하여 요청 시간을 단축시킬 수 있었습니다.

|![6](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/083c3abc-27af-4cf6-a3c3-1fc047da859b)|
| ------------------------------------------------------------------------------ |
| 백준 문제를 실시간으로 불러오기                                                |
</details>

# ❗기술적 챌린지

### 문제 인식
서비스 특성상 한 서버에 실시간 협업 기능 추가로, 서버의 부하가 심해져 이를 줄이기 위한 방법을 고민하게 됐습니다.

### 해결 방법

1. **소켓 통합** (담당)
   - 웹소켓 -> 소켓.io 업그레이드: 추가한 웹소켓 기반 라이브러리 통신 방식을 소켓.io로 업그레이드
   - 소켓 리소스 통합: 각 기능에서 개별적으로 사용하던 소켓을 통합해서, 리소스 낭비를 줄이기 위해 **하나의 소켓(io)**에서 모두 처리하도록 변경

<details>
  <summary>
2. **소켓 서버의 Vertical Scaling 문제 해결**</summary>
   - 기존 소켓 서버의 구성으로 발생하는 Vertical Scaling 문제를 해결하기 위해 Redis Pub/Sub을 활용하여 Horizontal Scaling이 가능하도록 서버 환경을 구축했습니다.
   - 문제 크롤러 호출 시 같은 방 유저들이 같은 문제를 호출할 가능성을 고려하여 Redis 캐싱으로 Request 속도를 향상시켰습니다.
</details>

### 문제 인식
기존의 웹 페이지 CSS와 새로 적용한 패키지의 CSS의 우선순위가 다르게 적용되면서 사용자에게 색상 표현이 안 나오는 문제가 발생했습니다.

### 해결 방법 (담당)
 - 웹 개발 도구의 요소를 활용해 문제 지점을 찾아내고, 계층 구조를 파악해 동일한 문제가 발생하지 않도록 조치했습니다.
 - 나아가 기존의 CSS를 tailwind를 활용한 방식으로 개선하여 개발자가 더 직관적으로 파악할 수 있게끔 리팩토링했습니다.

# 🔎 개발환경

개발 환경 설정은 다음과 같습니다.

# [.env]
```
<web_fe/backend>
MYSQL_DATABASE=userdb
MYSQL_HOST=localhost
MYSQL_PASSWORD=yours
MYSQL_PORT=3308
MYSQL_USERNAME=hello
SERVERLESS_GRADE_JAVASCRIPT=
SERVERLESS_GRADE_PYTHON=
JWT_SECRETKEY=secret
```
```
<web_fe/frontend>
VITE_CLIENT_URL="http://127.0.0.1:5173/"
VITE_SERVER_URL="http://127.0.0.1:3000/api"
VITE_SOCKET_SERVER_URL="ws://127.0.0.1:3333"
VITE_SOCKET_URL="ws://127.0.0.1:4444/"
VITE_CHAT_SOCKET_SERVER_URL="ws://127.0.0.1:8888/"
VITE_SOCKET_CANVAS_URL="ws://127.0.0.1:5555/"
```
```
<web_fe/chat>
?# common (? 빼세요)
NODE_ENV=dev
PORT=8888
?# cors
ALLOWED_ORIGIN=*
EXPOSE_HEADER=
?# redis
REDIS_PORT=6379
REDIS_HOST=localhost
REDIS_PASSWORD=
CACHE_TTL=300
?# mongo
MONGO_DEV=mongodb://localhost:27017/admin
MONGO_PROD=mongodb://localhost:27017/admin
?# clova
LLM_URL=yours
```
# [setting]
```
<터미널로 5개의 소켓을 열으신 후>
cd backend; yarn install; yarn start:dev
cd frontend; yarn install; yarn dev
cd frontend; yarn install; npx y-webrtc
cd socket; yarn install; yarn dev
cd chat; yarn install; yarn start
```

<details>
<summary> 👻 팀 소개 (Krafton Jungle 4th)</summary>

  ![8](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/5d22de9d-d87b-4d6a-a28c-7ddd064f4940)
</details>
<details>
<summary> 📃 프로젝트 포스터</summary>

  ![9](https://github.com/hey-dudegg/OnCore-Project/assets/154962837/867b9c77-fa4f-41d0-a444-c25ff00c93e9)
</details>
