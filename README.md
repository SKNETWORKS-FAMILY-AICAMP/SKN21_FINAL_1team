<div align="center" style="color: #A6C1A6;">

<img width="400" alt="kalpie" src="assets/kaipie.png" />
<br>
<i>Kalpie: An open-source, AI-native knowledge management platform inspired by NotebookLM.</i>
<br>
<a href="https://github.com/skn21-final-1team">Organization-link</a>

</div>

<br>

## Profile

<table>
  <tr>
    <td align="center"><a href="https://github.com/nature0022"><img src="assets/kalpie-profile.png" width="150px;" alt="">
    <td align="center"><a href="https://github.com/Ne-eun"><img src="assets/kalpie-profile.png" width="150px;" alt="">
    <td align="center"><a href="https://github.com/reasonableplan"><img src="assets/kalpie-profile.png" width="150px;" alt="">
    <td align="center"><a href="https://github.com/Wjaehyun"><img src="assets/kalpie-profile.png" width="150px;" alt="">
  </tr>
  <tr>
    <td align="center"><strong>이명준</strong></td>
    <td align="center"><strong>박내은</strong></td>
    <td align="center"><strong>최자슈아주원</strong></td>
    <td align="center"><strong>우재현</strong></td>
  </tr>
    <tr>
    <td align="center"><a href="https://github.com/nature0022"><b>@nature0022</b></td>
    <td align="center"><a href="https://github.com/Ne-eun"><b>@Ne-eun</b></td>
    <td align="center"><a href="https://github.com/reasonableplan"><b>@reasonableplan</b></td>
    <td align="center"><a href="https://github.com/Wjaehyun"><b>@Wjaehyun</b></td>
  </tr>
</table>
<br>

| 역할               | 주요 업무                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------- |
| Project Manager    | 요구사항 구체화, 일정 관리, 오픈소스 라이선스 검토                                                      |
| Frontend Developer | Next.js 기반 UI 구현, 북마크 수집용 확장프로그램 구현, 챗 인터페이스 구축, 수집된 자료 기반 컨텐츠 제작 |
| Backend Developer  | FastAPI 서버 구축, 웹 크롤링 로직 및 데이터 전처리 파이프라인 설계                                      |
| AI/ML Engineer     | RAG 파이프라인 설계, 임베딩 모델 최적화, 프롬프트 엔지니어링, LangGraph 에이전트 로직 설계              |
| DevOps             | Docker를 이용한 배포 환경 구축, 서버 운영 관리                                                          |


## 프로젝트 주제

**사용자의 브라우저 북마크 및 웹 URL을 지식 베이스로 활용하는 오픈소스 RAG(검색 증강 생성) 서비스**

단순한 링크 저장을 넘어, 저장된 웹 콘텐츠의 내용을 분석하고 사용자의 질문에 근거(Source)를 제시하며 답변하는 지능형 도우미 구축.

<br>

## 문제 정의

- **정보의 파편화**: 유익한 아티클을 북마크에 저장해도 나중에 다시 찾아 읽거나 내용을 요약하기 어려움
- **기존 서비스의 폐쇄성**: NotebookLM 등은 훌륭하지만 데이터 프라이버시나 모델 선택의 자유도가 낮음
- **비용 부담**: 유료 LLM API를 사용하여 개인 지식 베이스를 구축하기에는 지속적인 비용 발생 우려

**해결책**: EXAONE-4.0-32B 등 오픈소스 모델과 GPT-4o-mini 등 API 모델을 선택적으로 활용하여 누구나 자신의 환경에 맞게 운영할 수 있는 환경 제공

<br>

## 시장조사 및 BM

### 시장 조사

| 항목        | 내용                                                                                    |
| ----------- | --------------------------------------------------------------------------------------- |
| 타겟        | 연구자, 개발자, 대학생 등 방대한 웹 정보를 수집하지만 관리에 어려움을 느끼는 사용자     |
| 유사 서비스 | Google NotebookLM, Perplexity, Coral(Cohere)                                            |
| 차별점      | '북마크'라는 기존 습관을 데이터 소스로 활용하며, 완전한 오픈소스 및 로컬 실행 옵션 제공 |

### BM (Business Model)

- **Open Source Strategy**: 핵심 엔진은 Github에 공개하여 커뮤니티 기여 유도
- **B2B 확장**: 기업 내 내부 위키/문서 링크를 기반으로 한 사내 지식 베이스 솔루션으로 커스텀 제공
- **Managed Service**: 인프라 관리가 어려운 사용자를 위해 소액의 구독형 호스팅 서비스(SaaS) 제공 가능

`<br><br>`

## 수집 데이터 개요

| 데이터명                     | 수집 대상                    | 수집 목적                                                                                              | 사용 예정 기능                                             | 출처/저작권                                                           |
| ---------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------- | --------------------------------------------------------------------- |
| 웹 페이지 추출 텍스트 데이터 | 사용자가 입력한 웹페이지 URL | NotebookLM 벤치마킹을 위한 사용자 맞춤형 문서 기반 QA, 텍스트 청킹(Chunking) 및 임베딩(Embedding) 처리 | 웹페이지 텍스트 추출, Markdown 변환, 청킹 및 벡터화 전처리 | 사용자가 입력한 불특정 웹사이트이며, 각 웹사이트의 저작권 정책에 따름 |

<br>

## 수집 방법 및 자동화 절차

### 수집 방식

- **웹 크롤링**: robots.txt 확인 후 자동화된 웹 크롤링 수행
- **사용자 입력**: 실시간으로 사용자가 입력하는 URL 자동 처리

### 수집 도구 및 스크립트

**사용한 언어/라이브러리**: Python / `urllib.robotparser`(robots.txt 확인), `trafilatura`(정적 크롤링), `BeautifulSoup`(DuckDuckGo 우회 크롤링), `playwright`(동적 크롤링 및 렌더링)

**자동화 여부 및 주기**: 실제 유저가 URL을 입력할 때마다 실시간으로 자동화된 파이프라인 실행

### ETL 파이프라인

크롤링 이후 전처리 및 적재까지의 전체 흐름:

```
① Extract  : HybridClient (Trafilatura → Playwright 폴백)
② Transform
   - MarkdownPreprocessor  : 공백·HTML·노이즈 정규화
   - vLLM refine            : Llama-3.1-8B-Instruct 기반 내용 정제
   - vLLM summarize         : 요약 생성
   - HierarchicalPrependChunker
       마크다운 헤더(#/##/###) 기준 계층 분할 후
       헤더 경로를 각 청크 앞에 prepend
       예) [# 제목 > ## 섹션] 본문 내용...
       청크 크기 1000자, overlap 100자
③ Load     : bge-m3 임베딩 → langchain_pg_embedding (HNSW 인덱스)
              cmetadata: { source_id, seq }
④ Callback : 완료 후 Backend로 콜백 전송
```

### 오류 발생 시 예외 처리 전략

1. 대상 웹페이지의 `robots.txt`를 우선 확인하여 수집 가능 여부 판별
2. `trafilatura`를 통한 1차 정적 크롤링 시도 (Google 검색 문서 등 차단이 예상되는 경우 DuckDuckGo 엔진과 `BeautifulSoup`을 활용해 우회 접근)
3. 1차 크롤링 결과, 추출된 텍스트가 일정 글자 수 미만일 경우 동적 웹페이지로 간주하여 `playwright`를 통한 2차 크롤링(렌더링 후 추출) 진행
4. 추출된 텍스트 내에 가비지(Garbage) 데이터 패턴(예: unusual traffic, captcha, access denied, 404, 로그인 필요 등)이 정규식으로 감지될 경우 실패 처리 및 수집 중단

<br>

## 데이터 수집 통계

### 저장 위치 및 포맷

- **저장 경로**: AWS RDS (PostgreSQL + pgvector)
- **저장 포맷**: Markdown 텍스트 형태
- **인코딩**: httpx의 response.txt을 통해 HTTP 응답의 Content-Type 헤더에 charset이 있으면 해당 인코딩을 사용하며, 누락 시 UTF-8로 간주하여 진행

<br>

## 데이터 품질 및 정합성 관리 방안

- **중복 제거 기준**: 웹페이지 갱신을 대비하여 중복 제거하지 않음
- **표준화 전략**: 마크다운 텍스트의 공백, HTML, 제목, 리스트, 코드펜스, 테이블, 빈줄을 정규식으로 정규화하여 청킹 전 노이즈 제거 수행

`<br><br>`

## 데이터베이스 설계

### 소개

이 데이터베이스는 사용자가 제공하는 URL을 기반으로 질문에 답변을 수행할 수 있도록 데이터를 저장하고 관리하기 위해 설계되었으며, 사용자 정보, 크롤링 데이터, QnA 채팅 기록, 인증 토큰, 확장 프로그램 연동 키, 벡터 임베딩을 포함합니다.

### 시스템 개요

PostgreSQL (AWS RDS)을 사용하여 벡터 데이터와 관계형 데이터를 함께 관리합니다.

| 테이블명                | 목적                                                 |
| ----------------------- | ---------------------------------------------------- |
| users                   | 사용자 정보                                          |
| refresh_tokens          | JWT 리프레시 토큰 관리                               |
| notebook                | 대화 내용, 소스 그룹 단위                            |
| chat                    | 사용자와 어시스턴트 간의 대화 내용 및 출처 인용 저장 |
| source                  | URL 기반 메타데이터 및 크롤링 데이터                 |
| directory               | 소스 관리용 폴더 (트리 구조)                         |
| extension_sync_key      | Chrome 확장 프로그램 연동 Sync Key                   |
| langchain_pg_collection | LangChain PGVector 컬렉션 (자동 생성)                |
| langchain_pg_embedding  | 청킹된 벡터 데이터 (자동 생성)                       |

<br>

### 테이블 상세 명세

#### users

사용자 정보 관리

| 컬럼명        | 데이터 타입 | 제약조건         | 설명                           |
| ------------- | ----------- | ---------------- | ------------------------------ |
| id            | INTEGER     | NOT NULL         | 사용자 아이디 (PK)             |
| email         | VARCHAR     | NOT NULL, UNIQUE | 사용자 이메일                  |
| password      | VARCHAR     | NULL             | 비밀번호 (OAuth 사용자는 NULL) |
| name          | VARCHAR     | NOT NULL         | 사용자 이름                    |
| auth_provider | VARCHAR     | NOT NULL         | 인증 방식 (local / google)     |
| created_at    | DATETIME    | NOT NULL         | 생성일                         |

#### refresh_tokens

JWT 리프레시 토큰 관리

| 컬럼명     | 데이터 타입 | 제약조건         | 설명               |
| ---------- | ----------- | ---------------- | ------------------ |
| id         | INTEGER     | NOT NULL         | 토큰 아이디 (PK)   |
| user_id    | INTEGER     | NOT NULL         | 사용자 아이디 (FK) |
| token_hash | VARCHAR     | NOT NULL, UNIQUE | 토큰 해시값        |
| expires_at | DATETIME    | NOT NULL         | 만료 시각          |
| created_at | DATETIME    | NOT NULL         | 생성일             |

#### notebook

대화 내용, 소스 그룹 단위

| 컬럼명     | 데이터 타입 | 제약조건 | 설명                    |
| ---------- | ----------- | -------- | ----------------------- |
| id         | INTEGER     | NOT NULL | 노트북 아이디 (PK)      |
| title      | VARCHAR     | NOT NULL | 노트북 제목             |
| user_id    | INTEGER     | NOT NULL | 사용자 아이디 (FK)      |
| is_active  | BOOL        | NULL     | 활성화 상태 (삭제 여부) |
| pinned     | BOOL        | NULL     | 상단 고정 여부          |
| created_at | DATETIME    | NOT NULL | 생성일                  |

#### chat

사용자와 어시스턴트 간의 대화 내역

| 컬럼명           | 데이터 타입 | 제약조건 | 설명                                                                 |
| ---------------- | ----------- | -------- | -------------------------------------------------------------------- |
| id               | INTEGER     | NOT NULL | 대화 아이디 (PK)                                                     |
| role             | VARCHAR     | NOT NULL | 발화자 구분 (user / assistant)                                       |
| message          | VARCHAR     | NOT NULL | 대화 내역                                                            |
| notebook_id      | INTEGER     | NOT NULL | 노트북 아이디 (FK)                                                   |
| reference_source | JSON        | NULL     | 답변 근거 청크 출처 목록 [{source_id, seq, citation_no, url, title}] |
| created_at       | DATETIME    | NOT NULL | 생성일                                                               |

#### directory

소스 데이터 관리용 폴더 — 트리 구조

| 컬럼명      | 데이터 타입 | 제약조건 | 설명                                |
| ----------- | ----------- | -------- | ----------------------------------- |
| id          | INTEGER     | NOT NULL | 디렉토리 아이디 (PK)                |
| title       | VARCHAR     | NOT NULL | 폴더명                              |
| parent_id   | INTEGER     | NULL     | 상위 디렉토리 아이디 (FK, self-ref) |
| notebook_id | INTEGER     | NOT NULL | 노트북 아이디 (FK)                  |

#### source

URL 기반 수집 데이터

| 컬럼명       | 데이터 타입 | 제약조건 | 설명                                               |
| ------------ | ----------- | -------- | -------------------------------------------------- |
| id           | INTEGER     | NOT NULL | 소스 아이디 (PK)                                   |
| title        | VARCHAR     | NOT NULL | 소스 제목                                          |
| url          | VARCHAR     | NOT NULL | 소스 URL                                           |
| raw          | TEXT        | NULL     | 크롤링 원문                                        |
| refined      | TEXT        | NULL     | vLLM 정제 텍스트                                   |
| summary      | VARCHAR     | NULL     | 수집 데이터 요약                                   |
| status       | VARCHAR     | NOT NULL | 크롤링 상태 (pending / processing / done / failed) |
| is_active    | BOOL        | NOT NULL | RAG 검색 대상 포함 여부                            |
| notebook_id  | INTEGER     | NOT NULL | 노트북 아이디 (FK)                                 |
| directory_id | INTEGER     | NULL     | 부모 디렉토리 아이디 (FK)                          |
| created_at   | DATETIME    | NOT NULL | 생성일                                             |

#### extension_sync_key

Chrome 확장 프로그램 연동 Sync Key

| 컬럼명      | 데이터 타입 | 제약조건         | 설명                         |
| ----------- | ----------- | ---------------- | ---------------------------- |
| id          | INTEGER     | NOT NULL         | 키 아이디 (PK)               |
| user_id     | INTEGER     | NOT NULL, UNIQUE | 사용자 아이디 (FK)           |
| sync_key    | VARCHAR     | NOT NULL, UNIQUE | 동기화 키 값                 |
| notebook_id | INTEGER     | NOT NULL         | 연동 대상 노트북 아이디 (FK) |
| expires_at  | DATETIME    | NOT NULL         | 만료 시각 (발급 후 15분)     |
| created_at  | DATETIME    | NOT NULL         | 생성일                       |

#### langchain_pg_collection / langchain_pg_embedding

LangChain PGVector 자동 생성 테이블 — 청킹된 벡터 데이터 저장

| 컬럼명        | 데이터 타입  | 설명                                 |
| ------------- | ------------ | ------------------------------------ |
| document      | TEXT         | 청크 텍스트 (헤더 경로 포함)         |
| embedding     | VECTOR(1024) | bge-m3 임베딩 벡터                   |
| cmetadata     | JSONB        | `{ "source_id": int, "seq": int }` |
| collection_id | UUID         | langchain_pg_collection FK           |

`<br><br>`

## 서비스 아키텍처

두 가지 흐름으로 구분합니다.

### ① 채팅 및 CRUD

```
[Frontend — Next.js 16]
       │ REST API / SSE
       ▼
[Backend — FastAPI + LangGraph] ←──────────────────── [AWS RDS]
       │                                               (노트북, 채팅, 소스
       │  RunPod Serverless                             CRUD 직접 접근)
       ├── EXAONE-4.0-32B-FP8     (답변 생성)
       ├── BAAI/bge-m3            (쿼리 임베딩)
       └── bge-reranker-v2-m3     (검색 결과 리랭킹)
```

### ② ETL 파이프라인 (URL 등록 → 크롤링 → 벡터 적재)

```
[Chrome 확장 (Bookalpie)] ──POST /directory/sync──▶ ┐
                                                       ▼
[Frontend — Next.js 16]  ───── URL 등록 요청 ──────▶ [Backend]
                                                           │ POST /crawl
                                                           ▼
                                                   [Data Service — FastAPI]
                                                           │
                                                           │  RunPod Serverless
                                                           ├── BAAI/bge-m3              (청크 임베딩)
                                                           └── Llama-3.1-8B-Instruct    (refine / summarize)
                                                           │
                                                           ▼
                                                   [AWS RDS — langchain_pg_embedding 적재]
                                                           ↑ (벡터 검색 시 Backend도 직접 조회)
```

<br>

## 기술 스택

| 서비스          | 기술                                                                    |
| --------------- | ----------------------------------------------------------------------- |
| Frontend        | Next.js 16, React 19, TypeScript, Zustand, Zod, Tailwind CSS 4          |
| Extension       | Chrome MV3, React 19, Vite + CRXJS, Zustand, dnd-kit                    |
| Backend         | FastAPI, LangGraph 1.0, SQLAlchemy, JWT, Google OAuth                   |
| Data Service    | FastAPI, Trafilatura, Playwright, HierarchicalPrependChunker            |
| AI 인프라       | RunPod Serverless (EXAONE-4.0-32B-FP8, BAAI/bge-m3, bge-reranker-v2-m3) |
| Database        | PostgreSQL (AWS RDS) + pgvector, Alembic                                |
| Package Manager | pnpm (Frontend / Extension), uv (Python 서비스)                         |

`<br><br>`

## RAG 파이프라인

LangGraph 기반 QA 에이전트의 노드 흐름:

```
질문 입력
  → classify_intent       : 질문 유형 분류 (simple / complex / casual)
  → [complex] decompose_query : 서브 질문으로 분해
  → retrieve_sources      : pgvector 유사도 검색 + bge-reranker-v2-m3 리랭킹
  → [검색 실패] rewrite_query : 쿼리 재작성 후 재검색
  → generate_answer       : 답변 생성 (EXAONE / GPT-4o-mini / GPT-5.4-mini 스트리밍)
  → save_chat             : 답변 및 출처 인용 DB 저장
```

`<br><br>`

## Chrome 확장 프로그램 — Bookalpie

- **버전**: v3.0.0 (Chrome Manifest V3)
- **주요 기능**
  - 계층형 북마크 폴더 트리 탐색 및 드래그앤드롭 정렬
  - 실시간 키워드 검색 필터
  - Sync Key 인증으로 Kalpie 노트북과 연동
  - 선택한 북마크를 노트북에 전송 → Data Service에서 자동 크롤링·임베딩 처리
- **권한**: `bookmarks`, `storage`, `tabs`

`<br><br>`

## 데이터 전처리 결과서

### 개요

**전처리 목적**: 실제 웹 URL을 대상으로 크롤링 → 정제 → 청킹 → 임베딩 파이프라인의 동작을 검증하고, RAG 파이프라인의 검색 품질 및 응답 신뢰도(Faithfulness)를 평가하기 위한 테스트 데이터셋을 구축

### 테스트 데이터 구성

#### 크롤링 테스트 URL (`data/test/urls.py`)

기술 블로그, GitHub, Wikipedia, 뉴스, 커뮤니티, 공공/기업 사이트 등 한국어·영어 혼합 도메인 **51개 URL**을 수집하여 HybridClient의 정적/동적 크롤링 전략 및 전처리 파이프라인 전 구간을 검증

#### 리트리버 파이프라인 테스트셋 (`data/test/testset.json`)

위 URL 기반으로 크롤링·청킹·임베딩된 소스에 대해 청킹 전략, 임베딩 품질, 리트리버 검색 정확도를 평가하기 위한 **47개 Q&A 쌍**

| 항목         | 설명                     | 예시                                                    |
| ------------ | ------------------------ | ------------------------------------------------------- |
| question     | 소스 기반 사실 확인 질문 | "nanochat 프로젝트는 무엇인가요?"                       |
| ground_truth | 정답 텍스트              | "nanochat은 LLM 훈련을 위한 가장 간단한 실험 도구로..." |

#### RAG 품질 평가 테스트셋 (`backend/agent/testset.json`)

검색 품질(Context Precision/Recall)과 응답 신뢰도(Faithfulness)를 평가하기 위한 **50개 Q&A 쌍** — 복합 질문 형태로 구성하여 멀티홉 검색 및 답변 정확도 검증

| 항목         | 설명                | 예시                                                                    |
| ------------ | ------------------- | ----------------------------------------------------------------------- |
| question     | 복합 관점 포함 질문 | "Notion AI가 제공하는 핵심 기능들과 관리자가 데이터를 보호하는 방식은?" |
| ground_truth | 상세 정답 텍스트    | "Notion AI는 AI 노트로 회의 기록을 요약하고..."                         |

<br>

### 전처리 파이프라인 요약

**전체 흐름도**: ① 크롤링 → ② 정규화 → ③ 정제(vLLM) → ④ 요약(vLLM) → ⑤ 청킹 → ⑥ 임베딩 → ⑦ 적재

| 단계   | 목적           | 수행 작업                                       | 사용 도구/라이브러리         |
| ------ | -------------- | ----------------------------------------------- | ---------------------------- |
| 크롤링 | 웹 소스 수집   | 정적 크롤링 → 동적 폴백                        | Trafilatura, Playwright      |
| 정규화 | 노이즈 제거    | 공백·HTML·특수문자 정규화                     | MarkdownPreprocessor         |
| 정제   | 내용 품질 향상 | 불필요 요소 제거 및 구조화                      | vLLM (Llama-3.1-8B-Instruct) |
| 요약   | 소스 요약 생성 | 핵심 내용 요약                                  | vLLM (Llama-3.1-8B-Instruct) |
| 청킹   | 텍스트 분할    | 마크다운 헤더 기준 계층 분할, 헤더 경로 prepend | HierarchicalPrependChunker   |
| 임베딩 | 벡터화         | 청크 텍스트 → 1024차원 벡터                    | BAAI/bge-m3 (RunPod)         |
| 적재   | DB 저장        | HNSW 인덱스로 pgvector 적재                     | langchain_pg_embedding       |

<br>

## 인공지능 모델 선정 및 평가

### LLM Model

#### 모델 선정 기준

- **언어적 등가성**: 한국어와 영어 웹 문서가 혼재된 비즈니스 환경에서 두 언어에 대해 지식 손실 없이 고품질의 결과를 도출해야 함
- **제한된 하드웨어 내 구동 효율성**: RunPod의 RTX 4090/5090과 같은 24GB/32GB VRAM 환경에서 32B 파라미터 규모의 모델을 4비트 또는 8비트 양자화하여 사용하는 것이 이상적인 '스위트 스팟'임
- **긴 컨텍스트 윈도우 지원과 어텐션 효율성**: RAG 시스템은 수만 토큰에 달하는 검색 문서를 입력받아야 하므로, 중간 실종(Lost in the Middle) 현상 없이 문서 전체의 맥락을 파악하고 KV 캐시 증가를 억제할 수 있는 아키텍처가 중요함
- **추론 모드(Reasoning Mode)의 유무**: 모델이 단순한 텍스트 생성을 넘어 자체적인 사고 과정을 통해 논리적 모순을 식별하고 RAG 답변의 신뢰도를 높일 수 있어야 함

#### EXAONE-4.0 선정이유

- **압도적인 다국어(한국어-영어) RAG 성능**: 설계 단계부터 한국어와 영어 데이터 비중을 1:1로 맞춘 14조 개의 토큰을 학습하여, 두 언어 간의 지식 불균형을 원천적으로 해결한 최고 수준의 모델임

#### 선정 모델 및 배포

**선정 모델**: LGAI-EXAONE/EXAONE-4.0-32B-FP8

- 기술적 정확성과 언어적 균형을 위해 LGAI-EXAONE/EXAONE-4.0-32B 모델에 FP8(8비트) 양자화를 적용한 버전을 선정
- 양자화를 통해 모델 가중치가 차지하는 메모리 사용량을 절감하여, 남은 VRAM 공간을 RAG의 긴 문서 처리를 위한 KV 캐시로 확보 가능

**배포**: RunPod Serverless에 vLLM 기반으로 배포 완료. PagedAttention 기술을 통해 다중 사용자 접속 시 메모리 파편화 방지

**활용방안**:

- 웹 소스(HTML 등)를 파싱 및 시맨틱 청킹(Semantic Chunking)하여 벡터 데이터베이스에 저장
- 다국어 웹 문서를 크로스 참조하여 방대한 컨텍스트 속에서 핵심 정보 추출
- EXAONE 4.0의 추론 모드를 결합해 정확한 사실 관계 기반의 구조화된 문서 요약 및 QA 서비스 제공

<br>

### Embedding Model

#### 선정 기준

- **다국어 지원**: 한국어와 영어 혼합 문서(위키피디아, 기술 블로그 등)를 동일 벡터 공간에서 처리
- **최대 토큰 수**: 청킹 단위가 1,000자(약 300~500토큰)이므로, 긴 청크도 잘림 없이 인코딩 가능
- **벡터 차원**: 검색 정확도와 저장/연산 비용 간 균형. 1024차원이 현 프로젝트 규모에 적합
- **로컬 실행 가능**: 외부 API 의존 없이 서버 내에서 추론 가능 (비용 절감, 지연시간 최소화)
- **Query-Document 비대칭 처리**: 짧은 쿼리와 긴 문서 간의 의미 매칭이 정확해야 함

#### 후보 모델 비교

| 항목                  | BAAI/bge-m3           | intfloat/multilingual-e5-large |
| --------------------- | --------------------- | ------------------------------ |
| 벡터 차원             | 1024                  | 1024                           |
| 최대 토큰             | 8,192                 | 512                            |
| 다국어 지원           | 100+ 언어             | 100+ 언어                      |
| 입력 전처리           | 불필요                | "query: " prefix 필수          |
| MTEB 한국어 Retrieval | 상위권                | 중상위권                       |
| 모델 크기             | ~2.2GB                | ~2.2GB                         |
| 추론 프레임워크       | sentence-transformers | sentence-transformers          |

#### 선정 결과: BAAI/bge-m3

**선정사유**:

- **최대 토큰 수 8,192**: 현재 청킹 설정(1,000자, overlap 100자) 기준으로 청크가 잘릴 위험이 없음. multilingual-e5-large는 512토큰 제한으로 긴 청크에서 정보 손실 우려
- **전처리 불필요**: e5 계열은 쿼리와 문서에 각각 "query: ", "passage: " prefix를 붙여야 하므로 인덱싱과 검색 시 서로 다른 전처리 로직이 필요. bge-m3는 prefix 없이 동일한 방식으로 인코딩하므로 파이프라인이 단순함
- **다국어 Retrieval 성능**: MTEB 벤치마크에서 한국어를 포함한 다국어 검색 태스크에서 상위 성능을 보이며, Dense + Sparse + ColBERT 멀티 표현 지원으로 확장 가능성이 높음
- **검색-인덱싱 모델 일치**: retriever에서 쿼리 임베딩 시 동일한 bge-m3 모델을 사용하여 인덱싱과 검색 간 벡터 공간 불일치 문제를 원천 방지

#### 시스템 통합 구조

**인덱싱**: 크롤링 텍스트 → 청킹(1000자) → bge-m3 임베딩(1024d) → pgvector 저장 (HNSW 인덱스)

**검색**: 사용자 쿼리 → bge-m3 임베딩(1024d) → 코사인 유사도 검색 → Top-K 반환 → bge-reranker-v2-m3 리랭킹

**설정 상세**:

- 배치 크기: 32
- 벡터 정규화: 활성화 (코사인 유사도 기반 검색에 최적화)
- DB 인덱스: HNSW (m=16, ef_construction=64, vector_cosine_ops)

#### Reranker

검색 결과의 정밀도 향상을 위해 **BAAI/bge-reranker-v2-m3** Cross-Encoder 기반 리랭커를 도입하여 1차 벡터 검색(top-k) 결과를 재정렬합니다. RunPod Serverless에 배포 완료.

`<br><br>`

### RAG 파이프라인 평가

> 평가 프레임워크: deepeval / Judge 모델: GPT-4o-mini / 테스트셋: `backend/agent/testset.json` (50개 Q&A)

#### RAG 노드 개선 이력

| 버전      | 주요 변경사항                                                                   |  Faithfulness  | Answer Relevancy |
| --------- | ------------------------------------------------------------------------------- | :-------------: | :--------------: |
| BASELINE  | 기준 (2-intent, 기본 검색)                                                      |      0.916      |      0.773      |
| v1        | 3-intent 분류, reranker(min_score=0.05), rewrite_query 노드, 소스 인용 프롬프트 |      0.867      |      0.811      |
| v2        | v1 + 할루시네이션 제거 프롬프트 강화                                            |      0.889      |      0.788      |
| v3        | 3-intent + reranker 최적화 + 프롬프트 수정                                      | **0.919** |      0.856      |
| v4        | decompose_query 노드, simple rewrite 스킵, sub-query별 rerank, 재시도 라우팅    |      0.881      | **0.933** |
| v5 (최종) | sub-query rerank 최적화                                                         |      0.877      |      0.924      |

#### 모델별 최종 성능 비교 (v5 파이프라인 기준)

| 모델               | Contextual Precision | Contextual Recall | Faithfulness | Answer Relevancy |
| ------------------ | :------------------: | :---------------: | :----------: | :--------------: |
| gpt-4o             |        0.882        |       0.886       |    0.916    |      0.935      |
| gpt-5-mini         |        0.855        |       0.848       |    0.903    |      0.861      |
| gpt-4o-mini (기본) |        0.843        |       0.834       |    0.898    |      0.804      |
| EXAONE-4.0-32B     |        0.709        |       0.636       |    0.891    |      0.655      |

---

## 라이선스

MIT License. See [LICENSE](../LICENSE) for details.
