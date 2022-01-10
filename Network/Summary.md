# Network

<br>

## 목차

#### [1. 정의](#정의)

#### [2. 거리에 따른 네트워크 분류](#거리에-따른-네트워크-분류)

- LAN
- WAN

#### [3. 인터넷](#인터넷)

- 정의
- 동작 과정
- 라우터
- 모뎀
- ISP

#### [4. 방화벽](#방화벽)

#### [5. CDN](#CDN)

#### [6. 프로토콜](#프로토콜)

- 정의
- OSI 7계층
- TCP/IP 4계층

#### [7. IP주소](#IP주소)

- 정의
- 구성요소
- 종류
- IPv4
- IPv6

<br>

---

<br>

## 정의

- 정보 전송 목적의 인프라

<br>

## 거리에 따른 네트워크 분류

- LAN
  - Local Area Network
  - 동일 건물 내의 네트워크
- WAN
  - Wide Area Network
  - LAN을 연결시킨 네트워크

<br>

## 인터넷

### 정의

- TCP/IP 기반 네트워크

### 동작 과정

- 컴퓨터A
- 라우터A
- 모뎀A
- 전화시설A
- ISP A
- ISP B
- 전화시설B
- 모뎀B
- 라우터B
- 컴퓨터B

### 라우터

- 송신 컴퓨터로부터 데이터를 받아서 모뎀으로 보내고 수신 컴퓨터에 전달 여부 확인 기기

### 모뎀

- MODEM (MOdulator & DEModulator)
- 네트워크 데이터를 전화시설에서 처리할 수 있는 데이터로 변환 / 역변환 기기

### ISP

- Internet Service Provider
- 인터넷 서비스 제공 업체

<br>

## 방화벽

- 내부 네트워크 보호 목적으로 허가된 트래픽만 허용하는 방어 대책

<br>

## CDN

- Content Delivery Network
- 물리적인 거리로 인한 지연 해결을 목적으로 캐시 서버에 콘텐츠를 저장하고 제공하는 기술

<br>

## 프로토콜

### 정의

- 데이터 통신 규약

### OSI 7계층

#### 정의

- ISO에서 고안한 표준 프로토콜 집합 계층

#### 종류

- Application Layer
- Presentation Layer
- Session Layer
- Transport Layer
- Network Layer
- Data Link Layer
- Physical Layer

### TCP/IP 4계층

#### TCP/IP

- 인터넷 관련 프로토콜 집합 계층

#### 종류

- Application Layer
- Transport Layer
- Internet Layer
- Network Access Layer

### 종류

#### HTTP

- Hyper Text Transfer Protocol
- 인터넷에서 데이터 교환 목적의 서버/클라이언트 모델 프로토콜

#### HTTPS

- Hyper Text Transfer Protocol Secure
- HTTP + Security
- 모든 데이터 암호화
- SSL 인증서 필요

#### FTP

- File Transfer Protocol

#### SMTP

- Simple Mail Transfer Protocol

#### SNMP

- Simple Network Management Protocol
- UDP에서 사용하는 네트워크 장비 관리 프로토콜

#### Telnet

- 원격 시스템 연결에 사용하는 프로토콜

#### DNS

- Domain Name System
- IP주소 대신에 문자열로 주소를 표현하는 프로토콜
- 동작 과정
  - URL 입력
  - Local DNS에게 입력한 URL에 대한 IP주소 요청
  - Local DNS에 해당 URL의 IP주소가 없다면, Local DNS는 Root DNS 서버에 요청
  - Root DNS에 없다면, Local DNS는 다른 DNS서버에 요청
  - Local DNS가 해당 IP주소를 수신하면, 해당 도메인 네임의 IP주소를 캐싱하고 접속

#### TCP

- 연결형 통신 서비스 제공 프로토콜

#### UDP

- 비연결형 통신 서비스 제공 프로토콜

#### IP

- 인터넷 자원의 고유 주소 제공 프로토콜

#### ARP

- Address Resolution Protocol
- IP주소 -> MAC주소 변환 프로토콜

#### RARP

- Reverse Address Resolution Protocol
- MAC주소 -> IP주소 변환 프로토콜

#### ARQ

- Automatic Repeat reQuest
- 오류 발생 프레임의 재전송 프로토콜

#### Ethernet

- LAN에서 네트워크 장비의 MAC주소를 이용한 프레임 전송 프로토콜

<br>

## IP주소

### 정의

- 인터넷 자원의 고유 주소

### 구성요소

- 네트워크 주소 + 호스트 주소 + (서브넷 주소)
  - 서브넷
    - 호스트 주소를 부분적으로 나눈 부분망

### 종류

- IPv4
- IPv6

### IPv4

#### 비트수

- 32bit (8x4)

#### 진수

- 10진수

#### 클래스

- A ~ E 클래스

### IPv6

#### 비트수

- 128bit (16x8)

#### 진수

- 16진수

#### 특징

- IPv4 주소 고갈 해결
- 보안
- 멀티미디어
- 자동 네트워크 환경 설정
- 동적 패킷 크기

<br>
