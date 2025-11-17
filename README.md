# 🔥 AI MATE – 당신의 첫 업무를 함께하는 AI파트너  
SK Networks Family AI Camp 15기 최종 프로젝트 HinTon팀

---

## 📋 프로젝트 개요

**AI MATE** 는 Retrieval-Augmented Generation(RAG) 기반 LLM 기술을 활용하여  
**사내 문서 검색 → 요약 → 편집/생성 → 일정 관리 → 업무 안내**까지 한 번에 지원하는  
**통합형 AI 업무 비서 시스템**입니다.

반복적인 검색/정리 업무를 줄이고,  
사용자가 **자연어로 질문·요청만 해도 업무를 이어갈 수 있도록** 돕는 것이 핵심입니다.

---

## 🎯 핵심 목표

- 🔁 **신입사원의 사내업무 조기적응화** 
- 💬 **자연어 기반 직관적 업무 보조** 제공  
- 🧑‍💼 **신입사원 온보딩 속도 향상** 및 조직 적응력 증대  
- 

---
## 👥 팀 소개

<table>
  <thead>
    <tr>
      <th align="center" width="120">이름</th>
      <th align="center" width="180">역할</th>
      <th align="left">담당 영역</th>
      <th align="center" width="140">GitHub</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">홍민식</td>
      <td align="center">⚡ PM & Backend Developer</td>
      <td align="left">프로젝트 기획·관리, Gmail Agent, LangGraph 및 REST API 설계, Gmail API 연동</td>
      <td align="center"><a href="https://github.com/minnnsik">@minnnsik</a></td>
    </tr>
    <tr>
      <td align="center">최민석</td>
      <td align="center">⚡ Backend Developer</td>
      <td align="left">시스템 총괄, Jira Agent, 이슈 CRUD/검색, Vector DB 연동, 공통 REST API 설계·구현</td>
      <td align="center"><a href="https://github.com/Minsuk1014">@Minsuk1014</a></td>
    </tr>
    <tr>
      <td align="center">한승희</td>
      <td align="center">⚡ Backend Developer</td>
      <td align="left">PDF 챗봇, 문서 요약·이미지 분석, PDF RAG 파이프라인 구성</td>
      <td align="center"><a href="https://github.com/seunghee-han">@seunghee-han</a></td>
    </tr>
    <tr>
      <td align="center">김민규</td>
      <td align="center">🎨 Frontend Developer & DevOps</td>
      <td align="left">메인 Web 페이지 UI, 에이전트 연동 화면, Docker 기반 배포 환경 구성</td>
      <td align="center"><a href="https://github.com/kmklifegk">@kmklifegk</a></td>
    </tr>
    <tr>
      <td align="center">유의정</td>
      <td align="center">🎨 Frontend Developer</td>
      <td align="left">WebGuide 챗봇, Chat UI/UX, 오버레이 인터랙션 구현</td>
      <td align="center"><a href="https://github.com/Rr-EJ">@Rr-EJ</a></td>
    </tr>
  </tbody>
</table>



## ✨ 주요 기능

### 🔍 1. Gmail

- Gmail API 연동을 통해 받은편지함 불러오기  **실시간으로 불러오기**
- 자연어로 **메일 검색 / 필터링 / 메일상세 보기**
- 템플릿기반 메일작성 및 메일수정, 메일직접작성 , 자연어 기반 초안생성 및 메일수정 
- 대화형 프롬프트를 통해 **“마케팅팀에서 온 메일 보내줘 ”**, **“김부장에게 메일을 보내고 싶어”** 등 질의 가능

---

### 📝 2. Jira

- 자연어 한줄로 Jira 이슈 **생성 / 검색 / 수정 / 삭제** 까지 처리
  예)  'MKT 프로젝트에 부트캠프 테스트 A 작업 만들어줘' -> MKT 프로젝트에 새 이슈 생성
  예)  'MKT-27 제목을 수정된 시나리오로 바꿔줘 -> 해당 이슈 제목 업데이트
  예)  'MKT-27 삭제해줘' -> 이슈삭제

- **프로젝트 / 제목 / 설명 / 담당자 / 중요도** 기준으로 검색 지원
  -  'MKT 프로젝트에서 부트캠프 테스트 검색해줘' -> A, B 이슈 모두 조회
  -  '지라에서 담당자 최민석인 거 검색해줘'
  -  '지라에서 중요도 높은 거 보여줘'

- Chroma 기반 VectorDB를 활용한 **의미 기반 이슈 검색**
-  "프로모션과 관련된 이슈", "Figma 시안 제작 해야 하는 거" 처럼
   키워드가 조금 달라도 관련 이슈를 함계 찾아줌

-  데이터는 Jira API + VectorDB(Chroma)를 통해 **자동 동기화**되어,
   최신 이슈 상태를 기준으로 답변을 한다.
---

### 🗓️ 3. PDF 문서 번역 및 문서요약

- PDF 내 **선택한 영역의 텍스트를 자동 추출**하고, 한/영 기반으로 **핵심만 요약**해주는 기능  
- 문서 안 특정 문단·표 등을 선택하면 **한국어 ↔ 영어 자동 번역** 지원  
- “이 문서 핵심만 알려줘”, “3페이지 그래프 설명해줘”처럼 질문하면  
  RAG 기반으로 **문서 내용을 이해해서 답변하는 챗봇 기능** 제공  
- 요약·번역·질문 응답 이력을 저장해, 동일 문서 재조회 시 **연속적인 대화 흐름 유지**


---

### 🤖 4. Chrome 웹가이드 챗봇 

- 사용자의 요청에 따라 웹페이지 내 버튼이나 메뉴 위치를 화면위에 **오버레이(시각적 안내)를 표시** 
- 사용자의 질문을 웹페이지의 관련 콘텐츠와 매칭하여 핵심만 뽑아 자연어로 답변

---


## 크롬 챗봇
### 폴더 개요
- manifest.json에서 사이드 패널 확장으로 선언되어 Chrome 114+ 버전에서 동작합니다.
- panel.html/css/js가 사이드 패널 UI, content.js가 웹페이지 분석 및 하이라이트 오버레이, service_worker.js가 탭 이벤트 처리 및 메시지 브릿지를 담당합니다.
- server.js는 OpenAI API와 통신하는 로컬 백엔드입니다. 확장은 기본으로 http://localhost:3000에 연결하므로 서버가 켜져 있어야 합니다.
### 사전 준비
- Node.js 18 이상 권장.
- OpenAI API Key를 발급받아 .env 파일에 저장합니다. 
- 의존성 설치: npm install
### 백엔드 실행
- 로컬 서버를 켭니다: node server.js
- 정상 기동 시 콘솔에 Server running at http://localhost:3000이 표시됩니다. (에러가 나면 API 키 설정을 다시 확인하세요.)
### 크롬 확장 프로그램 등록
- Chrome 주소창에 chrome://extensions/ 입력 → 오른쪽 상단 개발자 모드 활성화.
- 압축해제된 확장 프로그램을 로드 버튼 → 이 폴더(예: chrome-sidechat) 선택.
- 설치 직후 서비스 워커가 사이드 패널을 자동으로 열어줍니다. 새 탭에서도 패널이 유지됩니다.
- 패널이 보이지 않으면 브라우저 우측 상단 사이드 패널 아이콘(또는 Ctrl+Shift+S)으로 “MS Side Chat”을 선택하세요.
### 사용 흐름
- 패널에서 메시지를 입력하면 로컬 서버 /chat 엔드포인트를 통해 OpenAI 응답을 받아옵니다.
- 웹 가이드 모드 버튼으로 페이지 분석/하이라이트 기능을 토글할 수 있습니다. 하이라이트는 content.js가 DOM을 읽어 생성합니다.
- PDF 업로드, 히스토리, 테마 토글 등은 panel.js에서 처리합니다. 대화 내용은 chrome.storage.local에 저장됩니다.
### 문제 해결 팁
- 패널이 “Connecting…”에서 멈추면 node server.js가 실행 중인지, 포트 3000이 다른 프로그램과 충돌하지 않는지 확인하세요.
- 사이드 패널이 자동으로 열리지 않으면 chrome://extensions에서 확장을 다시 로드하거나 Chrome을 재시작합니다.
- API 요청이 401/403이면 .env의 API 키 권한과 철자를 다시 점검하세요.
- 서버 주소를 변경해야 한다면 panel.js 안의 safeFetch("http://localhost:3000/…") 부분을 원하는 도메인으로 수정합니다.






##  Gmail




## 🏗️ 전체 시스템 아키텍처

### 1. 시스템 구성도



## 🤖 AI 에이전트 워크플로우 상세

### 1. Multi-Step Workflow 아키텍처 (LangGraph 기반)




### 2. Sequence Diagram


#### 2.2 AI 채팅 (메일조회 예시)
- 

#### 2.3 AI 채팅 (메일전송 예시)
- “


### 3. 새로운 워크플로우 구조

#### 3-1. 워크플로우 오케스트레이터 (LangGraph 노드 구조)
- 모든 요청은 **오케스트레이터 노드**를 통해 진입하며,
  - 의도 분석 → 라우팅 → 후속 에이전트 호출 → 결과 병합  
  을 담당합니다.
- 각 노드는 공통 상태(State)를 공유해,  
  현재까지의 검색 결과·편집 이력·사용자 설정 등을 기반으로 다음 액션을 결정합니다.

#### 3-2. DocumentSearchAgent (핵심 라우팅 구조)
- 유저 쿼리를 **키워드 + 의미 기반 검색 쿼리**로 변환하고,
  - 로컬 문서
  - 업로드 파일
  - 외부 시스템 연동 결과  
  를 통합해서 검색합니다.
- 검색 결과는 후속 에이전트(요약, 편집, 보고서 생성 등)에 넘겨질 수 있도록  
  **표준화된 구조(문서 ID, 스니펫, 스코어 등)** 로 반환됩니다.

#### 3-3. DocumentEditorAgent (핵심 라우팅 구조)
- 문서 편집 요청을 분석해
  - 요약 / 구조 재편성 / 문체·톤 변경 / 특정 섹션 편집  
  등의 **편집 전략을 선택**합니다.
- 선택된 전략에 따라 LLM 프롬프트를 구성하고,  
  결과를 HTML/Markdown 등 프론트엔드가 바로 사용할 수 있는 형태로 반환합니다.
- 편집 이력을 상태에 누적해, **연속적인 편집 세션**을 지원합니다.

















## 🔧 기술 스택

### 🖥 Frontend
- **React 19 + Vite** – 모던 프론트엔드 개발 환경
- **Tiptap** – 리치 텍스트 에디터 기반 문서 편집
- **Tailwind CSS** – 반응형 UI 디자인
- **React Big Calendar** – 일정 관리 인터페이스
- **Axios** – API 통신

### ⚙️ Backend
- **JiraAPI** – 이슈 CRUD/검색 연동
- **Google APIs (Gmail)** – 메일데이터 연동
- **FastAPI** – 고성능 비동기 웹 프레임워크
- **SQLModel** – 타입 세이프 ORM
- **SQLite** – 로컬 데이터베이스

### 🤖 AI & RAG
- **OpenAI GPT-4o** – 메인 LLM 모델
- **LangChain & LangGraph** – 에이전트 워크플로우 구성·관리
- **ChromaDB** – 벡터 DB(문서 임베딩 저장)
- **CLIP 이미지 임베딩** - PDF 내 이미지 의미 기반 검색·분석
- **OCR 엔진** - 스캔/이미지 PDF에서 텍스트 추출 (PDF 챗봇용)

### ☁️ Infrastructure
- **Docker** – 컨테이너 기반 배포
- **AWS** – 클라우드 인프라 EC2


## 📁 프로젝트 구조

```bash
FinalProject/
├── backend/                          # FastAPI 백엔드
│   ├── ChatBot/                      # AI 챗봇 모듈
│   │   ├── agents/                   # 에이전트 정의
│   │   ├── config/                   # 환경설정
│   │   ├── core/                     # 상태·워크플로 그래프
│   │   ├── prompts/                  # 시스템 프롬프트
│   │   ├── tools/                    # 검색·편집 툴 & 전략
│   │   └── utils/                    # 에러 핸들링 등 유틸
│   ├── database/                     # DB 레이어(SQLModel)
│   │   ├── models/                   # 캘린더·채팅·문서·유저 모델
│   ├── routers/                      # API 라우터(auth, chat, document 등)
│   ├── services/                     # 서비스 레이어
│   ├── etc/
│   │   └── llm_tools/                # RAG, 외부 API, hwpx 처리 등
│   ├── main.py                       # FastAPI 엔트리포인트
│   ├── Dockerfile
│   └── requirements.txt
│
├── frontend-ui/                      # React 프론트엔드
│   ├── src/
│   │   ├── App.jsx
│   │   ├── components/               # UI 컴포넌트
│   │   ├── assets/
│   │   └── index.js / main.jsx
│   ├── tailwind.config.js
│   ├── vite.config.js
│   └── Dockerfile
│
├── chroma_db/                        # ChromaDB 저장소
│   └── chroma.sqlite3
├── tests/                            # 유닛·통합 테스트
│   ├── test_agents.py
│   ├── test_api.py
│   ├── test_database.py
│   └── test_integration_advanced.py
├── locust/                           # 부하 테스트 리포트
├── editable_markdown/                # 편집 가능한 문서 샘플
└── uploaded_files/                   # 업로드된 사용자 파일





