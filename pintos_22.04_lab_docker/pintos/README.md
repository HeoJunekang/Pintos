# 🛠️ Pintos 구현 기록

**Project 1 — Threads**

스레드의 실행·대기·복귀와 우선순위에 따른 실행 순서를 구현하고 검증한 기록입니다.

[🏠 프로젝트·팀 소개](../../README.md) · [🧰 개발 환경 설정](../README.md)

---

## 🎯 개발 범위

| 기능 | 핵심 내용 | 현재 상태 |
| --- | --- | --- |
| ⏰ Alarm Clock | Busy Waiting 제거 · 대기·깨우기 | ✅ 제공 테스트 전체 통과 |
| 🥇 Priority Scheduling | 우선순위 기반 실행 대상 선택 | ✅ 기본 동작 테스트 통과 |
| 🚥 Semaphore | 우선순위 기반 대기자 처리 | ✅ 해당 테스트 통과 |
| 🔔 Condition Variable | 신호 전달 · Lock 재획득 | 🔧 구현·검증 중 |
| 🤝 Priority Donation | Lock 대기에 따른 우선순위 기부 | 🔧 부분 구현 |
| ⚖️ MLFQS | CPU 사용량·부하 기반 스케줄링 | 🟡 미완성·일부 테스트 통과 |

## 🧪 테스트 결과

**전체 27개 중 12개 통과 · 15개 실패**

| 채점 영역 | 통과 / 전체 |
| --- | :---: |
| ⏰ Alarm Clock | **6 / 6** |
| 🥇 Priority Scheduling · Donation | **4 / 12** |
| ⚖️ MLFQS | **2 / 9** |

📅 **검증일:** 2026-10-15 · 🔖 **소스:** `01d7260`  
📊 **내장 가중 채점:** 36.7 / 100점

기존 결과를 재사용하지 않은 새 빌드에서 실행했습니다. 점수는 저장소 내장 채점 기준입니다.

[📄 상세 결과·검증 조건·원본 로그](docs/TEST_RESULTS.md)

---

## 🛠️ 핵심 구현

| 기능 | 구현 내용 |
| --- | --- |
| ⏰ Alarm Clock | Sleep 목록 등록 · 깨울 시각 관리 · Thread 대기·복귀 |
| 🥇 Priority Scheduling | READY 목록 정렬 · 우선순위 비교 · 실행 전환 판단 |
| 🚥 Semaphore | 대기 목록 정렬 · 깨우기 이후 실행 우선순위 확인 |
| 🔔 Condition Variable | 대기 항목별 Semaphore · 신호 대상 선택 |
| 🤝 Priority Donation | 대기 스레드의 우선순위를 Lock 소유자에게 반영 |

MLFQS는 전체 동작이 완성되지 않았으며, 균등 CPU 배분 테스트 2개만 통과했습니다.

## 🧩 핵심 설계

| 설계 관점 | 적용 내용 |
| --- | --- |
| **책임 분리** | 시간 처리는 timer.c, Thread 상태·목록 관리는 thread.c에서 담당 |
| **기능별 함수 분리** | 대기 요청·목록 등록·상태 전환·깨우기를 구분 |
| **실행 순서 관리** | 대기자 선택과 CPU 실행 대상 선택을 구분 |
| **상태 변화 추적** | BLOCKED → READY → RUNNING의 흐름을 기준으로 분석 |

## 🚧 현재 한계

- **Condition Variable:** 기대한 깨우기 출력과 실행 순서를 충족하지 못함
- **Priority Donation:** 기부 유지·해제와 다중·중첩 기부 검증 미완료
- **MLFQS:** 부하·최근 CPU 사용량·nice·대기 관련 테스트 미통과

## 🔍 주요 학습

- **깨우기 ≠ 즉시 실행:** READY 전환과 CPU 배정을 구분
- **개별 호출 보호 ≠ 전체 작업 보호:** 메시지 출력이 섞이는 현상 분석
- **기부 적용 ≠ 기부 완료:** 우선순위를 높이는 시점과 기부가 끝나는 시점을 함께 고려
- **로그와 실행 흐름 연결:** 기대 출력·실제 출력·GDB 상태를 함께 확인

## 💻 검증 환경

| 구분 | 환경 |
| --- | --- |
| 운영 환경 | Ubuntu 22.04 · x86_64 · Docker |
| 컴파일러 | GCC 11.4.0 |
| 실행·디버깅 | QEMU 6.2.0 · GDB |
| 빌드 | GNU Make |

## 📂 상세 문서

- 📊 [테스트 상세 보고서](docs/TEST_RESULTS.md)
- 🧰 [실행·채점·GDB 사용 가이드](docs/DEVELOPMENT.md)
- 📖 [KAIST Pintos 공식 문서](https://casys-kaist.github.io/pintos-kaist/)

기반 프로젝트: Operating Systems and Lab (CS330), KAIST, by Youngjin Kwon.
