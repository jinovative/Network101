[[Computer Networks and the Internet]]

#### **요약 (Summary)**

인터넷은 다양한 보안 위협(Security Threats)에 노출되어 있으며, 공격자(Attackers)는 **malware(악성코드), DoS(Denial-of-Service) 공격, packet sniffing(패킷 감청), IP spoofing(위조)** 등의 기법을 사용해 시스템을 공격한다. 네트워크 보안(Network Security)은 이러한 위협을 방어하는 기술과 전략을 포함한다.

---

## **1.6.1 Malware (악성코드 공격)**

### **설명 (Explanation)**

**Malware(악성코드)**는 사용자의 컴퓨터를 감염시키는 소프트웨어로, 감염된 장치는 공격자가 원격으로 조종할 수 있다.

### **Malware의 종류**

1. **Virus (바이러스)**
    
    - 실행 파일에 포함되어 사용자가 실행하면 활성화됨
    - **E-mail attachments(이메일 첨부 파일)**로 유포되는 경우가 많음
2. **Worm (웜)**
    
    - 사용자 개입 없이 스스로 전파되는 악성코드
    - 인터넷을 통해 자동으로 확산됨
3. **Trojan Horse (트로이 목마)**
    
    - 정상적인 프로그램처럼 위장하여 설치되지만, 내부에 악성 기능 포함
4. **Spyware & Keylogger (스파이웨어 & 키로거)**
    
    - 사용자의 키보드 입력을 기록하여 개인정보 탈취 (ex: 비밀번호, 신용카드 정보)
5. **Botnet (봇넷)**
    
    - 감염된 다수의 장치를 원격 제어하여 DDoS 공격, 스팸 메일 전송 등에 활용됨

##### **💡 Real-Life Example (실생활 예시)**

> **바이러스**는 감염된 **USB**를 꽂으면 컴퓨터가 감염되는 것과 같음.  
> **웜**은 공기 중에 전염되는 감기 바이러스처럼 한 컴퓨터에서 다른 컴퓨터로 자동 전파됨.

---

## **1.6.2 Denial-of-Service (DoS) 공격**

### **설명 (Explanation)**

**Denial-of-Service(DoS) 공격**은 특정 서버나 네트워크를 과부하 상태로 만들어 정상적인 사용을 방해하는 공격이다.

### **DoS 공격의 유형**

1. **Vulnerability Attack (취약점 공격)**
    
    - 소프트웨어의 보안 취약점을 악용하여 서버를 다운시킴
    - 예: 특정 입력값을 보내 서버의 동작을 멈추게 하는 공격
2. **Bandwidth Flooding (대역폭 고갈 공격)**
    
    - 엄청난 양의 패킷을 전송하여 네트워크 대역폭을 가득 채움
    - 서버의 인터넷 연결을 마비시킴
3. **Connection Flooding (연결 과부하 공격)**
    
    - **TCP 3-way handshake**를 악용하여 가짜 연결 요청을 무한 생성
    - 서버가 정상적인 연결을 처리하지 못하도록 방해

### **DDoS (Distributed Denial-of-Service) 공격**

- **Botnet(봇넷)**을 활용하여 다수의 감염된 기기에서 동시에 공격을 수행
- 기존 DoS보다 탐지와 방어가 어려움

##### **💡 Real-Life Example (실생활 예시)**

> **DoS 공격**은 **수천 명이 동시에 전화를 걸어 고객센터를 마비시키는 것**과 비슷함.  
> **DDoS 공격**은 **조직적으로 대량의 가짜 전화(패킷)를 보내는 것**과 같다.

---

## **1.6.3 Packet Sniffing (패킷 감청, 도청)**

### **설명 (Explanation)**

**Packet Sniffing(패킷 감청)**은 네트워크에서 주고받는 패킷을 가로채어 감시하는 공격 방식이다.

- 네트워크를 통해 전송되는 **비암호화된 데이터**는 감청될 위험이 있음
- 공격자는 Wi-Fi 네트워크에서 패킷을 가로채 **로그인 정보, 신용카드 정보** 등을 탈취할 수 있음

### **Sniffing이 가능한 환경**

1. **Wireless Networks (무선 네트워크)**
    
    - 공공 Wi-Fi에서 쉽게 발생
    - 공격자는 Wi-Fi 패킷을 가로채서 분석 가능
2. **Broadcast Networks (공유 네트워크)**
    
    - 같은 LAN을 공유하는 사용자 간 데이터 감청 가능
3. **Compromised Routers (해킹된 라우터)**
    
    - 라우터가 해킹되면 모든 트래픽이 감청될 수 있음

### **방어 방법**

- **HTTPS 사용** (SSL/TLS 암호화)
- **VPN(Virtual Private Network)** 사용
- **Wi-Fi에서 WPA2/WPA3 보안 설정 활성화**

##### **💡 Real-Life Example (실생활 예시)**

> 패킷 감청은 **공공 Wi-Fi에서 누군가 옆에서 당신의 화면을 몰래 보는 것**과 같다.  
> VPN은 **프라이버시 보호막** 역할을 하며, 공격자가 당신의 트래픽을 훔쳐볼 수 없도록 한다.

---

## **1.6.4 IP Spoofing (IP 스푸핑, 위장 공격)**

### **설명 (Explanation)**

**IP Spoofing(스푸핑)**은 **공격자가 자신을 신뢰할 수 있는 IP로 위장하여 네트워크를 속이는 공격**이다.

- 패킷의 **source IP(출발지 IP 주소)**를 변조하여 신뢰받는 시스템인 것처럼 위장
- 네트워크 트래픽을 조작하거나, DoS 공격을 수행할 때 사용됨

### **공격 방식**

1. **Man-in-the-Middle Attack (MITM, 중간자 공격)**
    
    - 공격자가 클라이언트와 서버 사이에서 통신을 가로챔
    - 사용자는 공격자가 제공하는 가짜 웹사이트에 접속할 수도 있음
2. **Session Hijacking (세션 가로채기)**
    
    - 인증된 세션의 쿠키나 토큰을 탈취하여 불법적으로 접근

### **방어 방법**

- **IP 기반 인증 대신 암호화된 인증 사용**
- **VPN 및 보안 프로토콜(SSL/TLS) 적용**
- **네트워크 모니터링을 통한 비정상적인 트래픽 탐지**

##### **💡 Real-Life Example (실생활 예시)**

> IP Spoofing은 **전화 발신번호 조작**과 같다.
> 
> - 스팸 전화가 신뢰할 수 있는 번호로 표시되면 받게 되는 것처럼, 공격자는 신뢰받는 IP인 것처럼 위장하여 피해를 입힌다.

---

### **📌 핵심 정리 (Key Takeaways)**

1. **Malware(악성코드)**: 컴퓨터를 감염시키는 프로그램 (Virus, Worm, Trojan, Botnet 등)
2. **DoS/DDoS Attack(서비스 거부 공격)**: 과부하를 유발하여 서버나 네트워크를 마비시킴
3. **Packet Sniffing(패킷 감청)**: 네트워크 트래픽을 가로채 로그인 정보 등을 탈취
4. **IP Spoofing(스푸핑)**: 신뢰할 수 있는 IP처럼 위장하여 네트워크를 속이는 공격

🚀 **한 문장 요약:**  
인터넷은 **malware, DoS, packet sniffing, IP spoofing** 등의 보안 위협에 노출되어 있으며, 이를 방어하기 위해 **암호화, VPN, 네트워크 모니터링** 등의 보안 기술이 필요하다.