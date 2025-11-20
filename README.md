# 🔥 AI MATE – 세 가지 시스템으로 시작되는 첫 걸음 
SK Networks Family AI Camp 15기 최종 프로젝트 HinTon팀

---

## 📋 프로젝트 개요

**AI MATE** 는 Retrieval-Augmented Generation(RAG) 기반 LLM 기술을 활용하여  
**사내 문서 검색 → 요약 → 편집/생성 →  업무관리 → 메일 조회 → 웹가이드 →  **까지 한 번에 지원하는  
**신입사원  OJT AI  업무 비서 시스템**입니다.

신입사원이 입사하는 동안   반복적인 업무 인수인계 업무 적응을  줄이고,  
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



# Gmail 에이전트

## 폴더 개요

### 백엔드 (Python FastAPI)
- `main.py`: FastAPI 서버 메인 파일, Gmail 에이전트 API 엔드포인트 제공
- `agent.py`: Gmail 에이전트 메인 클래스, LangGraph 기반 워크플로우 관리
- `gmail_api_client.py`: Gmail API 클라이언트, 메일 조회/전송/수정 기능
- `llm_client.py`: OpenAI API 클라이언트, 자연어 처리 및 이메일 생성
- `graph_builder.py`: LangGraph 그래프 빌더, 에이전트 워크플로우 구성
- `nodes.py`: LangGraph 노드 구현, 각 작업 단계 처리
- `routing.py`: 라우팅 로직, 사용자 입력에 따른 액션 결정
- `state.py`: 상태 관리 시스템, 대화 컨텍스트 및 슬롯 관리
- `requirements.txt`: Python 의존성 패키지 목록

### 프론트엔드 (Chrome Extension)
- `chat_ 2/manifest.json`: Chrome 확장 프로그램 매니페스트, 사이드 패널 확장 선언 (Chrome 114+ 호환)
- `chat_ 2/panel.html/css/js`: 사이드 패널 UI 처리
- `chat_ 2/content.js`: 웹페이지 분석 및 하이라이트 오버레이 담당
- `chat_ 2/service_worker.js`: 탭 이벤트 처리 및 메시지 브릿지 관리
- `chat_ 2/server.js`: 로컬 백엔드 서버 (Express), OpenAI API와 통신 (선택사항)
- `chat_ 2/config.js`: API 서버 주소 설정 (기본값: `http://43.202.132.108:8000` 또는 `http://localhost:8000`)

**참고**: 확장 프로그램은 기본적으로 `http://localhost:8000` 또는 `http://43.202.132.108:8000`에 연결되며, FastAPI 서버가 실행 중이어야 합니다.

## 사전 준비

### Python 백엔드
- Python 3.8 이상 권장
- OpenAI API Key를 `.env` 파일에 저장:
  ```
  OPENAI_API_KEY=your-api-key-here
  ```
- Google API 자격 증명 파일 (`credentials.json`) 준비
- 의존성 설치:
  ```bash
  pip install -r requirements.txt
  ```

### Chrome Extension (선택사항)
- Node.js 18 이상 권장 (Express 서버 사용 시)
- 의존성 설치:
  ```bash
  cd chat_2
  npm install
  ```

## 백엔드 실행

### FastAPI 서버 실행 (메인 백엔드)
```bash
python main.py
```

서버가 성공적으로 시작되면 콘솔에 다음 메시지가 표시됩니다:
```
🚀 FastAPI 서버 시작 중...
📍 로컬 접속:
   서버 URL: http://localhost:8000
   API 문서: http://localhost:8000/docs
   헬스 체크: http://localhost:8000/health
```

오류가 발생하면 API 키 설정을 다시 확인하세요.

### Express 서버 실행 (선택사항, 웹 가이드 모드용)
```bash
cd chat_2
node server.js
```

서버가 성공적으로 시작되면 콘솔에 다음 메시지가 표시됩니다:
```
Server running at http://localhost:3000
```

## 크롬 확장 프로그램 등록

1. Chrome에서 `chrome://extensions/` 접속
2. 우측 상단의 "개발자 모드" 활성화
3. "압축해제된 확장 프로그램을 로드합니다" 클릭
4. `chat_ 2` 폴더 선택
5. 설치 후 서비스 워커가 자동으로 사이드 패널을 엽니다. 새 탭에서도 사이드 패널이 유지됩니다.

**사이드 패널이 보이지 않는 경우:**
- 브라우저 우측 상단의 사이드 패널 아이콘에서 "MS Side Chat" 선택
- 또는 `Ctrl+Shift+S` 단축키 사용

## 사용 흐름

### Gmail 에이전트 모드 (기본)
1. 패널에 입력한 메시지는 FastAPI 서버의 `/api/chat` 엔드포인트로 전송됩니다
2. 에이전트는 LangGraph 기반 워크플로우를 통해 다음 작업을 수행합니다:
   - **메일 조회**: "메일온거 보여줘", "기획팀 메일 확인해줘"
   - **메일 전송**: "수신자: 홍길동, 회의 메일 보내줘"
   - **초안 생성**: "회의 메일 초안 작성해줘"
   - **템플릿 사용**: "템플릿 보여줘", "1번 회의요청 템플릿 사용"
   - **메일 분류**: "메일 분류해줘"
3. Human-in-the-loop 절차:
   - 메일 전송/수정 작업은 사용자 승인을 거칩니다
   - 프론트엔드에서 yes/no 버튼으로 승인 입력을 받습니다
   - 승인 후에만 실제 Gmail API 호출이 수행됩니다
4. 대화 내용은 `chrome.storage.local`에 저장됩니다

### 웹 가이드 모드 (선택사항)
- "Web Guide Mode" 버튼으로 페이지 분석 및 하이라이트 기능을 토글할 수 있습니다
- `content.js`가 DOM을 읽어 오버레이를 생성합니다
- PDF 업로드, 히스토리, 테마 토글 기능은 `panel.js`에서 처리합니다

## 문제 해결 팁

### 패널이 "Connecting..." 상태에서 멈춤
- `python main.py`가 실행 중인지 확인하세요
- 포트 8000 충돌 여부를 확인하세요:
  ```bash
  lsof -i :8000  # macOS/Linux
  netstat -ano | findstr :8000  # Windows
  ```
- `config.js`에서 `API_BASE_URL`이 올바른 주소로 설정되어 있는지 확인하세요

### 사이드 패널이 자동으로 열리지 않음
- `chrome://extensions/`에서 확장 프로그램을 다시 로드하세요
- Chrome을 재시작해보세요
- 서비스 워커가 활성화되어 있는지 확인하세요

### 401/403 API 요청 오류
- `.env` 파일의 `OPENAI_API_KEY` 권한 및 철자를 다시 확인하세요
- Google API 자격 증명 파일 (`credentials.json`)이 올바른지 확인하세요
- Gmail API 스코프가 올바르게 설정되어 있는지 확인하세요

### 서버 주소 변경이 필요한 경우
- `chat_ 2/config.js` 파일에서 `API_BASE_URL` 값을 수정하세요:
  ```javascript
  const API_BASE_URL = "http://your-server-address:8000";
  ```
- `chat_ 2/manifest.json`의 `host_permissions`에도 새 주소를 추가하세요:
  ```json
  "host_permissions": [
    "http://your-server-address:8000/*"
  ]
  ```

### Gmail API 인증 오류
- `credentials.json` 파일이 프로젝트 루트에 있는지 확인하세요
- `token.json` 파일이 만료되었을 수 있습니다. 삭제 후 재인증하세요
- Google Cloud Console에서 Gmail API가 활성화되어 있는지 확인하세요

## 주요 기능

### 1. 자연어 메일 조회
- "메일온거 보여줘"
- "기획팀 요청 메일 보여줘"
- "읽지 않은 메일 확인해줘"

### 2. 이메일 초안 생성
- "회의 메일 초안 작성해줘"
- "프로젝트 보고서 메일 작성해줘"

### 3. 템플릿 시스템
- 5가지 비즈니스 템플릿 제공 (회의 요청, 보고서 제출, 인사, 질문/문의, 감사 인사)
- "템플릿 보여줘"로 목록 확인
- "1번 회의요청"으로 템플릿 사용

### 4. Human-in-the-loop 보안
- 메일 전송 전 사용자 승인 필수
- 초안 수정 시 확인 절차
- 잘못된 작업으로 인한 데이터 손상 방지

### 5. 실시간 메일 동기화
- 60초마다 자동 동기화 (메모리 최적화)
- 최신 메일 정보 유지












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
- 의도 분석 → 라우팅 → 후속 에이전트 호출 → 결과 병합을 담당합니다.
- 각 노드는 공통 상태(State)를 공유해,   현재까지의 검색 결과·편집 이력·사용자 설정 등을 기반으로 다음 액션을 결정합니다.

#### 3-2. Gmail Agent (핵심 라우팅 구조)

<img width="307" height="365" alt="핵심 라우팅 지메일에이전트 " src="https://github.com/user-attachments/assets/566a9f0c-1ee0-4e76-860d-e932b0510ccb" />


#### 3-3. Jira Agent (핵심 라우팅 구조)


















## 🔧 기술 스택

### 🖥 Frontend
- **HTML5** – 사이드 패널 UI 구조 및 마크업, 웹페이지(Side Panel UI Structure & Markup)
- **Vanilla JavaScript** – 순수 자바스크립트 기반 (프레임워크 없음)
- **Chrome.Tabs API** – 탭 정보 조히 및 제어 
- **CSS Variables** – 다크/라이트 테마 전환 (Dark/Light Theme Switching)
- **CSS Flexbox** – 반응형 레이아웃 구성 (Responsive Layout Structure)
- **Async/Await** – 비동기 작업 처리 (Asynchronous Task Handling)
  
### ⚙️ Backend
- **JiraAPI** – 이슈 CRUD/검색 연동
- **Google APIs (Gmail)** – Google OAuth 인증및 ,메일데이터 연동
- **FastAPI** – 고성능 비동기 웹 프레임워크

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

'''bash
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



📊 추진 배경 및 기대 효과

⸻

📈 추진 배경
현대 조직에서는 잦은 인사 이동과 신입사원 채용, 부서 간 협업이 늘어나면서
새 구성원이 복잡한 사내 시스템에 빠르게 적응하도록 돕는 것이 중요한 과제가 되었습니다.

그러나 여전히 PPT 매뉴얼, 위키, 구두 안내 등에 의존하다 보니
	•	어디를 눌러야 할지 모르는 UI 불안
	•	사수에게 반복해서 물어봐야 하는 의존·비효율
	•	Gmail, Jira, 사내 웹 등 여러 시스템을 오가야 하는 업무 피로

가 지속되고 있습니다.

이를 해결하기 위해, 자연어로 질문하면 업무 화면 위에서 길을 안내해 주고
메일·티켓·문서 작업을 함께 처리해 주는 **온보딩 특화 AI 비서 “AI MATE”**의 필요성이 커졌습니다.

⸻

🎯 기대 효과
	•	⏱️ 업무·온보딩 시간 절감
반복적인 메뉴 탐색, 문서 검색, 메일·티켓 작성 과정을 자동화하여
신입·전배자의 초기 적응 시간을 단축
	•	📚 지식 전달 표준화
사수·팀마다 다른 설명 대신, AI MATE가 최신 프로세스를 기준으로
일관된 절차와 메시지를 안내하여 업무 품질을 균일화
	•	🤝 협업 효율 향상
Gmail, Jira, Web Guide를 하나의 패널에서 연결해
이슈 공유, 문의 응답, 피드백 과정을 매끄럽게 지원
	•	🚀 신입사원 온보딩 경험 개선
실수에 대한 불안을 줄이고, 문서 기반 Q&A와 실시간 화면 가이드를 통해
신입이 자기주도적으로 업무를 익히도록 지원


