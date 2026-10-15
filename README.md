# 🧵 Pintos
### 크래프톤 정글 · 운영체제 구현 프로젝트

**C · Assembly · x86-64 · Docker · QEMU**

운영체제의 핵심 기능을 직접 구현하며, 코드와 실제 실행 결과로 동작 원리를 이해하는 팀 학습 프로젝트입니다.

---

## 📌 프로젝트 소개

KAIST 권영진(Youngjin Kwon) 교수님의 **x86-64 Pintos**를 기반으로 스레드 관리, 동기화, 사용자 프로그램 실행, 가상 메모리와 파일 시스템을 학습합니다.

기본 커널의 구조를 분석하고 기능을 확장하며, 테스트와 GDB를 통해 실행 흐름과 상태 변화를 검증합니다.

> 🎯 **현재 진행: Project 1 — Threads**  
> Alarm Clock과 기본 우선순위 동작을 검증했으며, Condition Variable과 Priority Donation을 구현·검증하고 있습니다.

## 👥 팀 구성

| 프로필 | 이름 | GitHub | 이메일 |
| :---: | :---: | --- | --- |
| <a href="https://github.com/HeoJunekang"><img src="https://github.com/HeoJunekang.png?size=140" width="70" height="70" alt="HeoJunekang 프로필"></a> | **HeoJunekang** | [@HeoJunekang](https://github.com/HeoJunekang) | — |
| <a href="https://github.com/BurningWings"><img src="https://github.com/BurningWings.png?size=140" width="70" height="70" alt="이강현 프로필"></a> | **이강현** | [@BurningWings](https://github.com/BurningWings) | [a01057364452@gmail.com](mailto:a01057364452@gmail.com) |
| <a href="https://github.com/jaehoo0305"><img src="https://github.com/jaehoo0305.png?size=140" width="70" height="70" alt="조재후 프로필"></a> | **조재후** | [@jaehoo0305](https://github.com/jaehoo0305) | [grooochyjeff1234@gmail.com](mailto:grooochyjeff1234@gmail.com) |

## 🤝 협업 방식

**같은 개념과 기능을 각자 학습·구현하고, 함께 리뷰하여 좋은 부분을 취합합니다.**

### 🔄 학습·개발 흐름

| 단계 | 활동 | 내용 |
| :---: | --- | --- |
| 1 | 📖 개념 학습 | 프로젝트 순서에 따라 필요한 개념 학습 |
| 2 | 💬 개념·설계 공유 | 학습한 내용과 구현 아이디어 논의 |
| 3 | 🛠️ 개별 구현 | 각자 기능을 구현하고 선택한 방식 정리 |
| 4 | 🔍 공동 리뷰 | PR을 통해 코드와 주석을 함께 검토 |
| 5 | 🧪 병합·테스트 | 좋은 부분을 취합하여 develop에서 검증 |
| 6 | ✅ 결과 반영 | 검증한 결과를 main에 반영 |
| 7 | 🔄 동기화 | 최신 상태를 받아 다음 학습 진행 |

### 🗣️ 의사결정 원칙

- **공동 참여:** PR 검토와 병합은 팀원 모두가 함께 진행합니다.
- **근거 중심:** 제안하는 방향과 그 이유를 명확히 설명하고 기록합니다.
- **선호 존중:** 이유가 분명한 제안자의 의견을 우선 고려합니다.
- **실무 경험:** 별도 선호가 없다면 실무에서 사용하는 방식을 기준으로 결정합니다.

### 📋 작업 관리

Jira에서 **할 일·담당자·우선순위·기한**을 관리합니다. 세부 작업 내용은 개인이 정리하고 필요할 때 팀에 공유하며, 작업 양식은 Jira 설정 후 확정합니다.

[📄 팀 협업 규칙 원문](https://app.notion.com/p/3f49cc36746d80819943e554268157cb?source=copy_link)

## 🗺️ 프로젝트 로드맵

| 단계 | 프로젝트 | 주요 학습 내용 | 진행 상황 |
| :---: | --- | --- | --- |
| 01 | **Threads** | 스레드 관리 · 스케줄링 · 동기화 · 우선순위 기부 | 🛠️ 진행 중 |
| 02 | User Programs | 프로그램 로딩 · 인자 전달 · 시스템 콜 · 프로세스 관리 | ⏳ 후속 학습 |
| 03 | Virtual Memory | 지연 로딩 · 페이지 교체 · Swap · 메모리 매핑 | ⏳ 후속 학습 |
| 04 | File Systems | FAT · 파일 확장 · 디렉터리 · 심볼릭 링크 | ⏳ 후속 학습 |

기능별 구현 상태와 실제 테스트 결과는 내부 README에 기록합니다.

## 💻 개발 환경

| 구분 | 사용 환경 |
| --- | --- |
| 호스트 | macOS |
| 개발 환경 | Docker Desktop · VS Code Dev Containers |
| 컨테이너 | Ubuntu 22.04 · x86-64 |
| 언어·빌드 | C · Assembly · GCC · GNU Make |
| 실행·디버깅 | QEMU · GDB |

## 📂 문서 안내

- 🛠️ **[구현 현황·설계·테스트 결과](pintos_22.04_lab_docker/pintos/README.md)** — 기능별 구현 내용, 검증 결과와 현재 한계
- 🧰 **[개발 환경 설정](pintos_22.04_lab_docker/README.md)** — Docker와 VS Code 개발 컨테이너 사용 안내

## 🔗 참고 자료

- [KAIST Pintos 공식 문서](https://casys-kaist.github.io/pintos-kaist/)
- [KAIST Pintos 원본 저장소](https://github.com/casys-kaist/pintos-kaist)
- [크래프톤 정글 Docker 개발 환경](https://github.com/krafton-jungle/pintos_22.04_lab_docker)
- 권영진 교수님 Pintos 강의 자료
