# 🎰 화곡랜드 UDP 미니게임 프로젝트

## 📌 개요

UDP 소켓 통신 기반으로 제작된 서버-클라이언트 미니게임 플랫폼입니다.  
C 언어를 기반으로 주사위 게임, 경마 게임, 슬롯머신 게임을 구현하였고, 
프레임버퍼를 활용하여 CLI 환경에서 간단한 그래픽 표현까지 지원합니다.

---

## 👤 담당 역할

- 전체 클라이언트 구조 이해 및 수정
- **`slot_machine_client.c`** 직접 구현 (애니메이션, 입력 처리, 서버 통신)
- 포트 설정, 통신 흐름 정리, 클라이언트 실행 전반 구성

---

## ⚙️ 사용 기술

- 언어: C
- 통신 방식: UDP Socket (`<sys/socket.h>`, `<netinet/in.h>`)
- 실행 환경: Linux (프레임버퍼 및 GPIO 입력 사용)
- 플랫폼: Raspberry Pi / 리눅스 CLI 환경

---

## 💡 주요 기능

- 🎲 주사위 게임: 유저 vs 서버 주사위 대결
- 🐎 경마 게임: 말 색상 선택 후 경주 결과 확인
- 🎰 슬롯머신 게임: 슬롯 회전 애니메이션 및 보상 판정
- 프레임버퍼를 이용한 간단한 그래픽 효과
- UDP를 통한 서버-클라이언트 통신

---

## 🎥 시연 영상

- [👉 미니게임 시연 영상(통합본)](https://youtu.be/NnL0EDnkhDs)

---

## 🛠️ 컴파일 및 실행 방법

### 📦 클라이언트 컴파일

```bash
# 메인 클라이언트 실행 파일
gcc client.c -o client

# 주사위 게임 클라이언트
gcc Dice_client.c -o Dice_client -lm

# 경마 게임 클라이언트
gcc horse_racing_client.c -o horse_racing_client -lm

# 슬롯머신 게임 클라이언트
gcc slot_machine_client.c -o slot_machine_client -lm
```
### 📦 서버 컴파일

```bash
# 메인 서버 실행 관리자
gcc execute.c -o server

# 주사위 게임 서버
gcc Dice_server.c -o Dice_server

# 경마 게임 서버
gcc horse_racing_server.c -o horse_racing_server

# 슬롯머신 게임 서버
gcc slot_machine_server.c -o slot_machine_server

```
## 📦 프로젝트 구성

```bash
Intel_Edge_BSP_Linux_project/
├── client/                 # 클라이언트 코드
│   ├── client.c             # 메인 클라이언트 프로그램
│   ├── Dice_client.c        # 주사위 게임 클라이언트
│   ├── horse_racing_client.c # 경마 게임 클라이언트
│   ├── slot_machine_client.c # 슬롯머신 게임 클라이언트
│   ├── define.h             # 공용 매크로 및 구조체 정의
│   └── images/              # 경마 게임 BMP 파일
│       ├── Red.bmp
│       ├── Blue.bmp
│       └── ... (생략)
│
├── server/                  # 서버 코드
│   ├── define.h             # 공용 매크로 및 구조체 정의
│   ├── execute.c            # 서버 실행 관리
│   ├── Dice_server.c        # 주사위 게임 서버
│   ├── horse_racing_server.c # 경마 게임 서버
│   └── slot_machine_server.c # 슬롯머신 게임 서버
│
├── README.md                # 프로젝트 설명 파일
└── .gitignore               # Git 무시 설정