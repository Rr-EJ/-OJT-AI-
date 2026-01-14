# AI MATE – 신입사원 OJT AI 업무 비서 시스템

## 프로젝트 개요
**AI MATE**는 Retrieval-Augmented Generation(RAG) 기반 LLM 기술을 활용해  
사내 문서 검색 → 요약 → 편집/생성 → 업무 관리 → 메일 조회 → 웹 가이드까지 지원하는  
**신입사원 온보딩 특화 AI 비서 시스템**입니다.

신입사원이 입사 시 반복적인 인수인계와 적응 부담을 줄이고,  
**자연어 질문·요청만으로 업무를 이어갈 수 있도록 돕는 것**이 핵심 목표입니다.


**추진 배경**
현대 조직은 잦은 인사 이동과 신입사원 채용으로 인해  
새로운 구성원이 **복잡한 디지털 업무 환경에 빠르게 적응하는 것**이 중요한 과제입니다.

- 각 시스템의 메뉴 구조와 용어가 달라 혼란 발생  
- 보고·요청·문의 메일 및 이슈 등록 등 비즈니스 커뮤니케이션 형식 이해 부족  
- 반복적인 문서·메일·티켓 작성으로 업무 피로와 시간 낭비  
- 정보가 메일·문서·이슈·채팅 등에 분산되어 우선순위 판단 어려움  

기존 매뉴얼·OJT만으로는 한계가 있어,  
**자연어 기반으로 업무 화면 안내와 메일·이슈·문서 작업을 지원하는 AI 파트너**가 필요합니다.


## 핵심 목표
- 신입사원의 사내업무 조기 적응  
- 자연어 기반 직관적 업무 보조 제공  
- 온보딩 속도 향상 및 조직 적응력 증대  



## 주요 기능

| 기능 | 설명 | 예시 |
|------|------|------|
| **Gmail** | - Gmail API 연동으로 받은편지함 실시간 불러오기<br>- 자연어 기반 메일 검색/필터링/상세 보기<br>- 템플릿 기반 메일 작성·수정, 초안 생성<br>- 대화형 프롬프트 지원 | “마케팅팀에서 온 메일 보내줘”<br>“김부장에게 메일 보내고 싶어” |
| **Jira** | - 자연어로 이슈 생성/검색/수정/삭제<br>- 프로젝트/제목/설명/담당자/중요도 기준 검색<br>- VectorDB(Chroma) 기반 의미 검색<br>- Jira API + VectorDB 자동 동기화 | “MKT 프로젝트에 작업 만들어줘” → 새 이슈 생성<br>“MKT-27 제목 수정해줘” → 제목 업데이트<br>“MKT-27 삭제해줘” → 이슈 삭제 |
| **PDF 문서** | - 선택 영역 텍스트 자동 추출<br>- 한국어 ↔ 영어 번역 지원<br>- 핵심 요약 제공<br>- RAG 기반 문서 Q&A<br>- 요약/번역/질문 응답 이력 저장 | “이 문서 핵심만 알려줘”<br>“3페이지 그래프 설명해줘” |
| **Chrome 웹가이드** | - 웹페이지 버튼/메뉴 위치 오버레이 표시<br>- 관련 콘텐츠 매칭 후 자연어 답변 제공 | 웹페이지 내 시각적 안내 + 핵심 답변 |

---

## 기술 스택

🖥 **Frontend** 
| 사용 기술 | 설명 |
|------|-----------|
| HTML5 | 사이드 패널 UI 구조 및 마크업 |
|  Vanilla JavaScript | 순수 자바스크립트 기반 (프레임워크 없음) |
| Chrome.Tabs API | 탭 정보 조회 및 제어 |
| CSS Variables | 다크/라이트 테마 전환 |
| CSS Flexbox | 반응형 레이아웃 구성 |
| Async/Await | 비동기 작업 처리 |

⚙️ **Backend** 
| 사용 기술 | 설명 |
|------|-----------|
| JiraAPI | 이슈 CRUD/검색 연동 |
| Google APIs (Gmail) | Google OAuth 인증 및 메일 데이터 연동 |
| FastAPI | 고성능 비동기 웹 프레임워크 |

 🤖 **AI & RAG** 
| 사용 기술 | 설명 |
|------|-----------|
| OpenAI GPT-4o | 메인 LLM 모델 |
| LangChain & LangGraph | 에이전트 워크플로우 구성·관리 |
| ChromaDB | 벡터 DB(문서 임베딩 저장) |
| CLIP 이미지 임베딩 | PDF 내 이미지 의미 기반 검색·분석 |
| OCR 엔진 | 스캔/이미지 PDF에서 텍스트 추출 |

☁️ **Infrastructure** 
| 사용 기술 | 설명 |
|------|-----------|
| Docker | 컨테이너 기반 배포 |
| AWS EC2 | 클라우드 인프라 |



## 🏗️ 전체 시스템 아키텍처

### 시스템 구성도
<img width="1862" height="735" alt="image" src="https://github.com/user-attachments/assets/ae3b4dfe-7b2e-4a6a-983d-4fa0eb310aa4" />

### 상세 워크플로우
| 크롬 익스텐션 |Jira Agent – 라우팅 | Gmail Agent – 라우팅|
|---|---|---|
|<img width="1928" height="705" alt="image" src="https://github.com/user-attachments/assets/fe71ead0-7029-4b40-9902-867467be9274" />|<img width="726" height="670" alt="image" src="https://github.com/user-attachments/assets/b0d281aa-b7da-4eec-baa7-f219883ee4b1" />|<img width="639" height="759" alt="image" src="https://github.com/user-attachments/assets/95ed7340-65bd-440f-a454-3ba224d89280" />|



---

## 🎯 기대 효과

| 효과 | 설명 |
|------|------|
| ⏱ **업무·온보딩 시간 단축** | 반복 작업 자동화, 자연어 기반 검색/초안 지원 |
| 📋 **표준화된 지식 전수** | 최신 프로세스 기반 일관된 절차 제공, 표준 업무 방식 학습 |
| 🤝 **협업 효율성 향상** | Gmail·Jira·웹 시스템 통합 인터페이스, 자연어 기반 검색·정리 |
| 🧑‍💼 **온보딩 경험 개선** | Human-in-the-loop 승인 절차, 화면 안내, 자동 초안 생성 |



---



# 상세 설명 


## 📁 프로젝트 구조
```
FinalProject/
├── backend/                          # FastAPI 백엔드
│   ├── ChatBot/                      # AI 챗봇 모듈
│   │   ├── agents/                   # 에이전트 정의
│   │   ├── config/                   # 환경 설정
│   │   ├── core/                     # 상태·워크플로 그래프
│   │   ├── prompts/                  # 시스템 프롬프트
│   │   ├── tools/                    # 검색·편집 툴 & 전략
│   │   └── utils/                    # 에러 핸들링 등 유틸
│   ├── database/                     # DB 레이어 (SQLModel)
│   │   └── models/                   # 캘린더·채팅·문서·유저 모델
│   ├── routers/                      # API 라우터 (auth, chat, document 등)
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
│
├── tests/                            # 유닛·통합 테스트
│   ├── test_agents.py
│   ├── test_api.py
│   ├── test_database.py
│   └── test_integration_advanced.py
│
├── locust/                           # 부하 테스트 리포트
├── editable_markdown/                # 편집 가능한 문서 샘플
└── uploaded_files/                   # 업로드된 사용자 파일
```



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



## Gmail 에이전트

### 폴더 개요

#### 백엔드 (Python FastAPI)
- `main.py`: FastAPI 서버 메인 파일, Gmail 에이전트 API 엔드포인트 제공
- `agent.py`: Gmail 에이전트 메인 클래스, LangGraph 기반 워크플로우 관리
- `gmail_api_client.py`: Gmail API 클라이언트, 메일 조회/전송/수정 기능
- `llm_client.py`: OpenAI API 클라이언트, 자연어 처리 및 이메일 생성
- `graph_builder.py`: LangGraph 그래프 빌더, 에이전트 워크플로우 구성
- `nodes.py`: LangGraph 노드 구현, 각 작업 단계 처리
- `routing.py`: 라우팅 로직, 사용자 입력에 따른 액션 결정
- `state.py`: 상태 관리 시스템, 대화 컨텍스트 및 슬롯 관리
- `requirements.txt`: Python 의존성 패키지 목록

#### 프론트엔드 (Chrome Extension)
- `chat_ 2/manifest.json`: Chrome 확장 프로그램 매니페스트, 사이드 패널 확장 선언 (Chrome 114+ 호환)
- `chat_ 2/panel.html/css/js`: 사이드 패널 UI 처리
- `chat_ 2/content.js`: 웹페이지 분석 및 하이라이트 오버레이 담당
- `chat_ 2/service_worker.js`: 탭 이벤트 처리 및 메시지 브릿지 관리
- `chat_ 2/server.js`: 로컬 백엔드 서버 (Express), OpenAI API와 통신 (선택사항)
- `chat_ 2/config.js`: API 서버 주소 설정 (기본값: `http://43.202.132.108:8000` 또는 `http://localhost:8000`)

**참고**: 확장 프로그램은 기본적으로 `http://localhost:8000` 또는 `http://43.202.132.108:8000`에 연결되며, FastAPI 서버가 실행 중이어야 합니다.

---

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

---

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


---


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





