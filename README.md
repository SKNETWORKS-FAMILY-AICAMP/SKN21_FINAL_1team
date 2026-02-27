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
  
| 역할 | 주요 업무 |
|------|-----------|
| Project Manager | 요구사항 구체화, 일정 관리, 오픈소스 라이선스 검토 |
| Frontend Developer | Next.js 기반 UI 구현, 북마크 수집용 확장프로그램 구현, 챗 인터페이스 구축, 수집된 자료 기반 컨텐츠 제작 |
| Backend Developer | FastAPI 서버 구축, 웹 크롤링 로직 및 데이터 전처리 파이프라인 설계 |
| AI/ML Engineer | RAG 파이프라인 설계, 임베딩 모델 최적화, 프롬프트 엔지니어링, LangGraph 에이전트 로직 설계 |
| DevOps | Docker를 이용한 배포 환경 구축, 서버 운영 관리 |  

<br><br>

## 프로젝트 주제

**사용자의 브라우저 북마크 및 웹 URL을 지식 베이스로 활용하는 오픈소스 RAG(검색 증강 생성) 서비스**

단순한 링크 저장을 넘어, 저장된 웹 콘텐츠의 내용을 분석하고 사용자의 질문에 근거(Source)를 제시하며 답변하는 지능형 도우미 구축.

<br>

## 문제 정의

- **정보의 파편화**: 유익한 아티클을 북마크에 저장해도 나중에 다시 찾아 읽거나 내용을 요약하기 어려움
- **기존 서비스의 폐쇄성**: NotebookLM 등은 훌륭하지만 데이터 프라이버시나 모델 선택의 자유도가 낮음
- **비용 부담**: 유료 LLM API를 사용하여 개인 지식 베이스를 구축하기에는 지속적인 비용 발생 우려

**해결책**: 무료/오픈소스 모델(Llama 3, Mistral 등)을 활용하여 누구나 무료로 개인 서버나 로컬에서 운영할 수 있는 환경 제공

<br>

## 시장조사 및 BM

### 시장 조사

| 항목 | 내용 |
|------|------|
| 타겟 | 연구자, 개발자, 대학생 등 방대한 웹 정보를 수집하지만 관리에 어려움을 느끼는 사용자 |
| 유사 서비스 | Google NotebookLM, Perplexity, Coral(Cohere) |
| 차별점 | '북마크'라는 기존 습관을 데이터 소스로 활용하며, 완전한 오픈소스 및 로컬 실행 옵션 제공 |

### BM (Business Model)

- **Open Source Strategy**: 핵심 엔진은 Github에 공개하여 커뮤니티 기여 유도
- **B2B 확장**: 기업 내 내부 위키/문서 링크를 기반으로 한 사내 지식 베이스 솔루션으로 커스텀 제공
- **Managed Service**: 인프라 관리가 어려운 사용자를 위해 소액의 구독형 호스팅 서비스(SaaS) 제공 가능

<br><br>

## 수집 데이터 개요

| 데이터명 | 수집 대상 | 수집 목적 | 사용 예정 기능 | 출처/저작권 |
|---------|---------|---------|-------------|----------|
| 웹 페이지 추출 텍스트 데이터 | 사용자가 입력한 웹페이지 URL | NotebookLM 벤치마킹을 위한 사용자 맞춤형 문서 기반 QA, 텍스트 청킹(Chunking) 및 임베딩(Embedding) 처리 | 웹페이지 텍스트 추출, Markdown 변환, 청킹 및 벡터화 전처리 | 사용자가 입력한 불특정 웹사이트이며, 각 웹사이트의 저작권 정책에 따름 |

<br>

## 수집 방법 및 자동화 절차

### 수집 방식

- **웹 크롤링**: robots.txt 확인 후 자동화된 웹 크롤링 수행
- **사용자 입력**: 실시간으로 사용자가 입력하는 URL 자동 처리

### 수집 도구 및 스크립트

**사용한 언어/라이브러리**: Python / `urllib.robotparser`(robots.txt 확인), `trafilatura`(정적크롤링), `BeautifulSoup`(DuckDuckGo 우회 크롤링), `playwright`(동적 크롤링 및 렌더링)

**자동화 여부 및 주기**: 실제 유저가 URL을 입력할 때마다 실시간으로 자동화된 파이프라인 실행

### 오류 발생 시 예외 처리 전략

1. 대상 웹페이지의 `robots.txt`를 우선 확인하여 수집 가능 여부 판별
2. `trafilatura`를 통한 1차 정적 크롤링 시도 (Google 검색 문서 등 차단이 예상되는 경우 DuckDuckGo 엔진과 `BeautifulSoup`을 활용해 우회 접근)
3. 1차 크롤링 결과, 추출된 텍스트가 일정 글자 수 미만일 경우 동적 웹페이지로 간주하여 `playwright`를 통한 2차 크롤링(렌더링 후 추출) 진행
4. 추출된 텍스트 내에 가비지(Garbage) 데이터 패턴(예: unusual traffic, captcha, access denied, 404, 로그인 필요 등)이 정규식으로 감지될 경우 실패 처리 및 수집 중단

<br>

## 데이터 수집 통계

### 데이터 양

- **전체 수집 데이터 건수**: 실시간 적재 예정이며 현재 테스트 단계로 약 140개 데이터 수집 완료
- **추출된 고품질 데이터 건수 (필터링 후 기준)**: 필터링(가비지 텍스트 제거) 통과 및 Markdown 변환 성공 건수 기준으로 약 100개 데이터 보유

### 저장 위치 및 포맷

- **저장 경로**: runpod의 PostgreSQL DB 서버에 현재 저장 중이며, 배포단계에서 AWS RDS로 이전 예정
- **저장 포맷**: Markdown 텍스트 형태
- **인코딩**: httpx의 response.txt을 통해 HTTP 응답의 Content-Type 헤더에 charset이 있으면 해당 인코딩을 사용하며, 누락 시 UTF-8로 간주하여 진행

<br>

## 데이터 품질 및 정합성 관리 방안

- **중복 제거 기준**: 웹페이지 갱신을 대비하여 중복 제거하지 않음
- **표준화 전략**: 마크다운 텍스트의 공백, HTML, 제목, 리스트, 코드펜스, 테이블, 빈줄을 정규식으로 정규화하여 청킹 전 노이즈 제거 수행

<br><br>
## 데이터베이스 설계

### 소개

이 데이터베이스는 사용자가 제공하는 URL을 기반으로 질문에 답변을 수행할 수 있도록 데이터를 저장하고 관리하기 위해 설계되었으며, 사용자의 정보, 크롤링 데이터, QnA 채팅 기록, 북마크, 크롤링 된 데이터 기반의 컨텐츠를 포함합니다.

### 시스템 개요

PostgreSQL를 사용하여 벡터 데이터와 관계형 데이터를 관리합니다.

| 테이블명 | 목적 |
|---------|------|
| user | 사용자 정보 |
| chat | 사용자와 어시스턴트간의 대화 내용 저장 |
| notebook | 대화 내용, 각종 컨텐츠 그룹 단위 |
| contents | 페이지 데이터 기반 제작된 컨텐츠 |
| quiz | 컨텐츠 - 퀴즈 데이터 |
| flash_card | 컨텐츠 - 플래시 카드 데이터 |
| source | URL기반 메타데이터 및 크롤링 데이터 |
| directory | 소스 관리용 폴더 |
| page_data | 청킹된 Vector 데이터 |

<br>

### 테이블 상세 명세

#### User
사용자 정보 관리

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 사용자 아이디 (PK) |
| password | VARCHAR | NOT NULL | 비밀번호 |
| email | VARCHAR | NOT NULL | 사용자 이메일 |
| name | VARCHAR | NOT NULL | 사용자 이름 |
| created_at | DATETIME | NOT NULL | 생성일 |

#### Chat
사용자와 어시스턴트 간의 대화 내역

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 대화 아이디 (PK) |
| role | VARCHAR | NOT NULL | 사용자/어시스턴트 구분 |
| message | VARCHAR | NOT NULL | 대화 내역 |
| created_at | DATETIME | NOT NULL | 생성일 |

#### Notebook
대화 내용, 컨텐츠, 수집데이터그룹

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 노트북 아이디 (PK) |
| title | VARCHAR | NOT NULL | 노트북 제목 |
| user_id | INTEGER | NOT NULL | 사용자 아이디 (FK) |
| is_active | BOOL | NULL | 활성화 상태 (삭제여부) |
| created_at | DATETIME | NOT NULL | 생성일 |

#### Directory
페이지 소스 데이터 관리용 폴더 (북마크 폴더) - 폴더 안에 소스 트리 구조로 관리

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 디렉토리 아이디 (PK) |
| parent_id | INTEGER | NOT NULL | 디렉토리 아이디 (FK) |
| notebook_id | INTEGER | NOT NULL | 노트북 아이디 (FK) |

#### Source
URL기반 수집 데이터

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 소스 아이디 (PK) |
| title | VARCHAR | NOT NULL | 소스 제목 |
| url | VARCHAR | NOT NULL | 소스 URL |
| summary | VARCHAR | NULL | 수집 데이터 요약 정보 |
| notebook_id | INTEGER | NOT NULL | 노트북 아이디 (FK) |
| directory_id | INTEGER | NOT NULL | 부모 디렉토리 아이디 (FK) |
| created_at | DATETIME | NOT NULL | 생성일 |

#### Contents
수집 데이터 기반 생성된 각종 콘텐츠 그룹

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 콘텐츠 아이디 (PK) |
| type | VARCHAR | NOT NULL | 콘텐츠 타입 |
| notebook_id | INTEGER | NOT NULL | 노트북 아이디 (FK) |

#### Questions
콘텐츠 질문

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 질문 아이디 (PK) |
| question | VARCHAR | NOT NULL | 콘텐츠 질문 |
| content_id | INTEGER | NOT NULL | 콘텐츠 아이디 (FK) |

#### Answers
콘텐츠 답변

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 답변 아이디 (PK) |
| answer | VARCHAR | NOT NULL | 콘텐츠 답변 |
| hint | VARCHAR | NULL | 답변에 대한 힌트 |
| question_id | INTEGER | NOT NULL | 질문 아이디 (FK) |
| is_correct | BOOL | NOT NULL | 해당 답변의 정답여부 |

#### page_data
벡터 데이터

| 컬럼명 | 데이터 타입 | 제약조건 | 설명 |
|--------|-----------|--------|------|
| id | INTEGER | NOT NULL | 데이터 아이디 (PK) |
| source_id | VARCHAR | NOT NULL | 원문 소스 데이터 정보 |
| chunk_text | TEXT | NOT NULL | 청킹된 데이터 원본 |
| embedding | VECTOR | NOT NULL | 벡터화 데이터 |
| payload | JSON | NOT NULL | 성능 향상 용 메타데이터 |

<br><br>
## 데이터 전처리 결과서

### 개요

**전처리 목적**: Open LLM 모델의 성능 평가 데이터셋 구축 및 NotebookLM 방식의 웹 소스 추가 기능에 대한 POC

**평가용 데이터셋**: 한국어 위키백과 내 인공지능, 기계학습, 딥러닝 등 관련 문서 15개를 기반으로 368건의 정제된 Q&A 쌍(v3) 구축

### 평가용 데이터 구성

| 항목명 | 설명 | 예시 |
|--------|------|------|
| content_id | 문서 식별자 | doc_001 |
| title | 위키백과 문서 제목 | 인공지능 |
| section | 추출된 섹션 헤더 | 강인공지능과 약인공지능 |
| context chunk | 청크 단위 컨텍스트 | "강인공지능(strong AI)은..." |
| question | 합성 생성된 평가용 질문 | "강인공지능의 정의를 설명해주세요." |
| reference_answer | 평가용 정답 | "강인공지능은 인간과 유사한..." |
| question_type | 질문 유형 | definition, summarization 등 |

<br>

### 전처리 프로세스 개요

**전체 흐름도**: ① 크롤링 → ② 전처리 → ③ 텍스트 정제 → ④ 분할 → ⑤ 데이터 합성 → ⑥ 적재

**전처리 파이프라인 요약**:

| 단계 | 목적 | 수행 작업 | 사용 도구/라이브러리 |
|------|------|---------|-------------------|
| 크롤링 | 웹 소스 수집 | Wikipedia Crawling | Requests, BS4 |
| 전처리 | 비정상 데이터 제거 | 영어와 한국어를 제외한 다른 문자, 문서와 의미론적으로 다른 글자 제거 | Python, Claude cli |
| 텍스트 정제 | 노이즈 제거 | 사이드 바, 페이지 네비게이션 등 잔여물 및 특수문자 정리 | Re, Python |
| 분할 | 의미 단위 청킹 | 마크다운 (#) 기준 분할 및 문장 단위 재분할 | Python |
| 데이터 합성 | LLM-as-Judge 평가 데이터셋 구축 | 컨텍스트 기반 QA 및 reference_answer 합성 데이터 생성 | Claude cli |
| 적재 | 저장 및 버전 관리 | Csv 형식으로 저장 및 버저닝 | Os, Pathlib |

<br>

### 세부 전처리 단계

#### 텍스트 정제 및 노이즈 제거

**정제 대상 및 기준**:
- **위키백과 특수 요소**: mw-editsection(편집 링크), reflist(각주 목록), [편집] 텍스트 등 가독성을 해치는 요소 제거
- **하이퍼링크 오류**: 존재하지 않는 문서로 연결되는 class="new"(빨간 링크) 텍스트의 혼입 방지
- **사이드바/네비게이션**: 본문 시작 전 나열되는 주제별 링크 블록을 식별하여 제거

**처리 방식 및 영향**:
- 정규표현식(re)과 BeautifulSoup4를 활용한 태그 및 패턴 기반 제거
- v1 대비 v2에서 원본 데이터 크기를 약 31% 감소(298KB → 206KB)시켜 고밀도의 텍스트 정보만 확보

#### 의미 단위 청킹 (Section-based Chunking)

**분할 로직 및 기준**:
- **섹션 기반 분할**: 단순 글자 수 기준이 아닌, 위키 마크다운의 ## 헤더를 기준으로 주제별 1차 분할 수행
- **길이 제한 및 재분할**: 단일 섹션이 800자를 초과할 경우에만 문장 경계를 탐색하여 2차 분할을 수행하며, 80자 미만의 짧은 청크는 제외

**코드 예시**:
```python
# 섹션 기반 분할 로직 예시
def split_by_sections(text):
    sections = text.split('##')
    return [s.strip() for s in sections if len(s.strip()) >= 80]

# 긴 섹션 문장 단위 재분할
if len(section_text) > 800:
    chunks = split_long_section(section_text, max_len=800)
```

#### 평가용 합성 데이터(Q&A) 생성

**데이터 생성 전략**:
- **Definition**: "용어(English)"와 같은 괄호 패턴을 추출하여 개념 정의형 질문 생성 (162건)
- **Summarization**: 섹션 제목을 활용하여 해당 단락의 전체 내용을 묻는 요약형 질문 생성 (97건)
- **Temporal**: "YYYY년" 패턴을 기반으로 시계열적 사실 관계를 묻는 질문 생성 (100건)

**데이터 변환 및 생성 결과**:
- **Reference Answer**: Judge LLM이 모델의 답변을 채점할 수 있는 'Golden Answer'를 컨텍스트 기반으로 자동 생성
- **Question Type**: 각 데이터에 질문 유형 레이블을 부여하여 모델의 영역별 성능 분석 가능

#### 데이터 적재 및 버전 관리

- **최종 데이터 수**: 368건의 정제된 Q&A 쌍 (v3 기준)
- **적재 방식**: os, pathlib 라이브러리를 사용하여 `data/processed/processed_v3.csv` 경로에 저장 및 버전별 이력 관리

<br>

### 전처리 결과 요약 및 평가

**향후 활용 방안**:
- 텍스트 분류
- 대화 응답 분기 조건 설계
- LLM 학습데이터 구축

<br><br>

## 인공지능 모델 선정 및 평가

### LLM Model

#### 모델 선정 기준

- **언어적 등가성**: 한국어와 영어 웹 문서가 혼재된 비즈니스 환경에서 두 언어에 대해 지식 손실 없이 고품질의 결과를 도출해야 함
- **제한된 하드웨어 내 구동 효율성**: RunPod의 RTX 4090/5090과 같은 24GB/32GB VRAM 환경에서 32B 파라미터 규모의 모델을 4비트 또는 8비트 양자화하여 사용하는 것이 이상적인 '스위트 스팟'임
- **긴 컨텍스트 윈도우 지원과 어텐션 효율성**: RAG 시스템은 수만 토큰에 달하는 검색 문서를 입력받아야 하므로, 중간 실종(Lost in the Middle) 현상 없이 문서 전체의 맥락을 파악하고 KV 캐시 증가를 억제할 수 있는 아키텍처가 중요함
- **추론 모드(Reasoning Mode)의 유무**: 모델이 단순한 텍스트 생성을 넘어 자체적인 사고 과정을 통해 논리적 모순을 식별하고 RAG 답변의 신뢰도를 높일 수 있어야 함

#### EXAONE-4.0 선정이유

- **압도적인 다국어(한국어-영어) RAG 성능**: 설계 단계부터 한국어와 영어 데이터 비중을 1:1로 맞춘 14조 개의 토큰을 학습하여, 두 언어 간의 지식 불균형을 원천적으로 해결한 최고 수준의 모델임

#### 선정 모델 및 향후 계획

**선정 모델**: LGAI-EXAONE/EXAONE-4.0-32B-FP8
- 기술적 정확성과 언어적 균형을 위해 LGAI-EXAONE/EXAONE-4.0-32B 모델에 FP8(8비트) 양자화를 적용한 버전을 선정
- 양자화를 통해 모델 가중치가 차지하는 메모리 사용량을 절감하여, 남은 VRAM 공간을 RAG의 긴 문서 처리를 위한 KV 캐시로 확보 가능

**활용방안**:
- 웹 소스(HTML 등)를 파싱 및 시맨틱 청킹(Semantic Chunking)하여 벡터 데이터베이스에 저장
- 다국어 웹 문서를 크로스 참조하여 방대한 컨텍스트 속에서 핵심 정보 추출
- EXAONE 4.0의 추론 모드를 결합해 정확한 사실 관계 기반의 구조화된 문서 요약 및 QA 서비스 제공

**향후 계획**:
1. **실사용 환경 평가**: 테스트 데이터로 실제 서비스 환경에서의 RAG 답변 정확도를 평가. 상용 폐쇄형 API(예: GPT-4o)를 '평가자(LLM-as-a-Judge)'로 활용한 대조군 실험 진행 중

2. **경량화된 모델 고려**: 단순 정보 추출이나 높은 처리 속도가 요구되는 구간에서 TinyBERT나 EXAONE-3.0 (7.8B) 같은 경량화 모델의 하이브리드 도입 검토

3. **다양한 환경 비교 평가**: 단일 GPU(24-32GB) 단일 환경과 A100/H100 고성능 멀티 GPU, 또는 RTX5090 2개 이상 활용한 병렬 처리 간의 속도 및 가성비 비교 평가

4. **vLLM 서빙 및 API 구축**: Docker 컨테이너 기반의 vLLM 프레임워크를 RunPod에 배포하여 FastAPI 기반의 비동기 스트리밍 API 구축. vLLM의 PagedAttention 기술을 통해 다중 사용자 접속 시의 메모리 파편화 방지

<br>

### Embedding Model

#### 선정 기준

- **다국어 지원**: 한국어와 영어 혼합 문서(위키피디아, 기술 블로그 등)를 동일 벡터 공간에서 처리
- **최대 토큰 수**: 청킹 단위가 1,000자(약 300~500토큰)이므로, 긴 청크도 잘림 없이 인코딩 가능
- **벡터 차원**: 검색 정확도와 저장/연산 비용 간 균형. 1024차원이 현 프로젝트 규모에 적합
- **로컬 실행 가능**: 외부 API 의존 없이 서버 내에서 추론 가능 (비용 절감, 지연시간 최소화)
- **Query-Document 비대칭 처리**: 짧은 쿼리와 긴 문서 간의 의미 매칭이 정확해야 함

#### 후보 모델 비교

| 항목 | BAAI/bge-m3 | intfloat/multilingual-e5-large |
|--------|-----------|--------|
| 벡터 차원 | 1024 | 1024 |
| 최대 토큰 | 8,192 | 512 |
| 다국어 지원 | 100+ 언어 | 100+ 언어 |
| 입력 전처리 | 불필요 | "query: " prefix 필수 |
| MTEB 한국어 Retrieval | 상위권 | 중상위권 |
| 모델 크기 | ~2.2GB | ~2.2GB |
| 추론 프레임워크 | sentence-transformers | sentence-transformers |

#### 선정 결과: BAAI/bge-m3

**선정사유**:
- **최대 토큰 수 8,192**: 현재 청킹 설정(1,000자, overlap 100자) 기준으로 청크가 잘릴 위험이 없음. multilingual-e5-large는 512토큰 제한으로 긴 청크에서 정보 손실 우려

- **전처리 불필요**: e5 계열은 쿼리와 문서에 각각 "query: ", "passage: " prefix를 붙여야 하므로 인덱싱과 검색 시 서로 다른 전처리 로직이 필요. bge-m3는 prefix 없이 동일한 방식으로 인코딩하므로 파이프라인이 단순함

- **다국어 Retrieval 성능**: MTEB 벤치마크에서 한국어를 포함한 다국어 검색 태스크에서 상위 성능을 보이며, Dense + Sparse + ColBERT 멀티 표현 지원으로 확장 가능성이 높음

- **검색-인덱싱 모델 일치**: retriever에서 쿼리 임베딩 시 동일한 bge-m3 모델을 사용하여 인덱싱과 검색 간 벡터 공간 불일치 문제를 원천 방지

#### 시스템 통합 구조

**인덱싱**: 크롤링 텍스트 → 청킹(1000자) → bge-m3 임베딩(1024d) → pgvector 저장 (HNSW 인덱스)

**검색**: 사용자 쿼리 → bge-m3 임베딩(1024d) → 코사인 유사도 검색 → Top-K 반환

**설정 상세**:
- 배치 크기: 32
- 벡터 정규화: 활성화 (코사인 유사도 기반 검색에 최적화)
- DB 인덱스: HNSW (m=16, ef_construction=64, vector_cosine_ops)

#### 향후 계획

| 단계 | 내용 |
|------|------|
| 평가 체계 구축 | RAGAS 기반 context_precision / context_recall 자동 평가 파이프라인 구축 중. TestsetGenerator를 활용한 테스트셋 자동 생성 예정 |
| OpenAI 임베딩 기준선 설정 | text-embedding-3-large (3072d) / text-embedding-3-small (1536d)를 baseline으로 설정하여 검색 정확도 기준점 확보 |
| 로컬 모델 비교 실험 | GPU 환경(RunPod) 확보 후 bge-m3 vs multilingual-e5-large 외에도 gte-multilingual-base, multilingual-e5-large-instruct 등 최신 로컬 모델 후보 추가 비교 |
| Reranker 도입 | 1차 벡터 검색(top-k) 결과를 Cross-Encoder 기반 리랭커로 재정렬하여 정밀도 향상. BAAI/bge-reranker-v2-m3 또는 ms-marco-MiniLM-L-12-v2 검토 |
| 비용 효율 분석 | 로컬 GPU 운용 비용(RunPod 시간당 단가 × 추론량) vs OpenAI API 비용(토큰당 단가 × 호출량) 비교 |
| 최종 모델 확정 | 정확도·비용·지연시간 관점에서 최적 모델 확정. API 모델이 우세할 경우 로컬 모델 대신 API 전환도 고려 |
| 청킹 전략 연동 최적화 | 확정된 임베딩 모델에 맞춰 청킹 파라미터(chunk_size, overlap, splitter 종류) 조합별 검색 품질 실험 |

<br><br>
