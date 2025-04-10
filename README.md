# 🎰 화곡랜드 UDP 미니게임 프로젝트

## 📌 개요

"화곡랜드"는 C 언어로 구현된 UDP 기반 서버-클라이언트 미니게임 플랫폼입니다.  
클라이언트는 주사위 게임, 경마 게임, 슬롯머신 게임 중 하나를 선택해 서버에 요청하고,  
서버는 해당 게임을 실행하여 결과를 반환합니다.

---

## 🎮 주요 게임 목록

- 🎲 **Dice Game** – 유저와 서버가 주사위를 굴려 승부
- 🐎 **Horse Racing** – 말 색상에 베팅하고 경주 결과 확인
- 🎰 **Slot Machine** – (담당 구현) 회전 애니메이션 포함된 슬롯머신 게임 UI

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
