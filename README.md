# 김경호 (Gyeongho Kim) · `@vwaiolet`

> **"완벽함은 더 이상 더할 것이 없을 때가 아니라, 더 이상 뺄 것이 없을 때 성취된다."** — *Antoine de Saint-Exupéry*

도메인과 런타임의 경계를 두지 않고, 문제의 제약 조건(지연 시간·메모리·운영 복잡도)에 가장 부합하는 아키텍처를 설계하고 끝까지 구현하는 소프트웨어 엔지니어입니다.  
웹/클라우드 기반의 **B2B AI 서비스 풀스택 개발**에서 출발해, 현재는 **차량·물류 현장의 Edge/Physical AI 파이프라인**과 **고성능 백엔드·시스템 엔지니어링**에 집중하고 있습니다.

- 🌐 **Portfolio**: [info.vwaiolet.com](https://info.vwaiolet.com)
- 📄 **Resume**: [Notion 이력서 바로가기](https://vwaiolet.notion.site/3bd779dcbed480648e21fbd4070ac0a3)
- 📫 **Contact**: [kito17@naver.com](mailto:kito17@naver.com)

---

## 🛠 Core Engineering Focus

- **Edge & Physical AI Systems**: K3s 경량 클러스터, 차량 CAN/SOME/IP/DoIP 통신, NVIDIA Isaac Sim 연동, ONNX/소형 LLM(Gemma 3 LoRA) 기반 멀티 스테이지 추론 파이프라인 구축
- **High-Performance Backend & Native Apps**: 워크로드 특성에 맞춘 폴리글랏 설계 (**Python / TypeScript / C# .NET Native AOT / Rust**), 대용량 스트리밍 인제스션 및 실시간 통신(WebRTC, SignalR, SSE)
- **End-to-End Product Delivery**: 데이터베이스·인프라(Docker, PostgreSQL, ClickHouse, Redis)부터 웹/모바일/데스크톱 클라이언트(React, Nuxt, WinUI 3, Expo)까지 0-to-1 설계 및 통합

---

## 📌 Featured Public Repositories

외부에서 코드와 설계 문서를 바로 확인하실 수 있는 대표 공개 프로젝트입니다.

| 프로젝트 | 핵심 기술 스택 | 설계 포인트 및 요약 |
| :--- | :--- | :--- |
| **[StelWave](https://github.com/vwaiolet/stel-wave)** | `C#` `WinUI 3` `Native AOT` `BASS` | **WASAPI Exclusive / ASIO 비트퍼펙트 하이파이 오디오 플레이어**<br/>Windows 오디오 믹서를 우회하는 하드웨어 직접 제어, 레지스트리 기반 출력 장치 비트 깊이 검출 및 실시간 오디오 경로 검증 UI 구현 |
| **[Project Nexus](https://github.com/vwaiolet/project-nexus)** | `C#` `ASP.NET Core` `Docker API` | **컨테이너 네트워크 자동 감지 기반 경량 헬스·연결성 감시 데몬**<br/>별도 설정 없이 자신이 속한 Docker 네트워크를 자동 탐색하여 컨테이너 상태, DNS/TCP 연결성, 인증 실패 로그 패턴을 수집·시각화 |
| **[Binance Archive Server](https://github.com/TriNeural/binance-archive-server)** | `C#` `.NET AOT` `ClickHouse` | **대용량 체결 데이터 제로 얼로케이션 스트리밍 수집 서버**<br/>전체 JSON을 메모리에 역직렬화하지 않고 `PipeReader`와 `Utf8JsonReader`로 순차 파싱하여 ClickHouse에 `RowBinary` 포맷으로 청크 적재 |

---

## 🏢 Key Architecture & R&D Experience

실무 및 연구 개발 프로젝트에서 주도적으로 설계·구현한 주요 시스템입니다.

### 1. 주식회사 이더블에스 — *2026*
- **Connected Car K3s Edge AI 플랫폼**
  - 차량 SocketCAN 로우 데이터 고속 수집 및 1차 이상 탐지(`tract-onnx`) 계층을 **Rust**로 구현하여 메모리 풋프린트 최소화
  - 2차 물리 법칙 검증기에 LoRA 미세조정 **Gemma 3 270M** 모델을 결합하고, Redis Streams 기반 **가변 주파수 이벤트 전파(Variable Frequency Event Propagation)** 패턴 적용
- **스마트 물류(WMS) & 디지털 트윈 통합 플랫폼**
  - NVIDIA Isaac Sim 추론 어댑터, ONNX 비전 검수 모델, 화재 감지 릴레이 및 React 관제 모노레포 구축
  - ASP.NET Core Blazor 사무실 관리자 콘솔 + Expo 현장 작업자 모바일 스캐너(오프라인 대기 큐 및 원장 트랜잭션) 및 Odoo 19 기반 WMS 커스텀 애드온 개발
- **엔터프라이즈 PLM / PMS 시스템**
  - OpenProject(Ruby on Rails) 코어 커스터마이징, CAD 뷰어 캐시 정책 개선 및 서브모듈 기반 모노레포 배포 체계 구축

### 2. (주)디엑스아이소프트 — *2023.10 ~ 2025.06*
- **B2B AI 영어 튜터 플랫폼 설계 및 풀스택 구현**
  - FastAPI, PostgreSQL(Alembic), React(TypeScript), Vertex AI / Google GenAI, SSE 및 TTS를 활용하여 선생님·학생 역할 기반 수업 관리, 실시간 AI 음성·텍스트 회화, 학습 일정 연동 단어장(`word_note`) 및 교재/영상 콘텐츠 자동 생성 파이프라인 구축
- **AI 기반 LMS(학습 관리 시스템) 고도화**
  - Django(ASGI/DRF), Celery, Redis, Next.js 환경에서 Gemini 2.0 Flash 기반 AI 튜터링, 강의 영상 기반 단어장 생성, PDF 기반 강의 자동 구성 및 토스페이먼츠 빌링 연동
- **지능형 강의 요약·RAG 및 지식 그래프 시각화 웹 서비스**
  - YouTube/강의 영상 STT(Whisper) 및 멀티 LLM(HyperCLOVA X, Mistral, Gemini, OpenAI) 기반 스트리밍 요약·퀴즈 생성·RAG 백엔드(Django/FastAPI, MongoDB, Firebase)와 타임라인 연동 플레이어·키워드 그래프(ReactFlow) 프론트엔드 개발
- **차량용 DoIP 부트로더 진단 통신 테스트 자동화**
  - ISO-13400(DoIP) 기반 부트로더의 `Request Download` / `Transfer Data` 시나리오 및 부정 응답(Negative Response) 검증을 위한 Python `DoIPClient` 테스트 스크립트 고도화 및 SW 테스트 명세 수립
