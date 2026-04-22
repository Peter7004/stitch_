# ElecMaster - 전기기능사 학습 플랫폼

ElecMaster는 전기기능사 시험 준비를 위한 통합 학습 플랫폼입니다.

## 🌟 주요 기능

### 1. **메인 페이지** (`main/`)
- 서비스 소개 및 네비게이션
- 학습 자료 접근

### 2. **핵심요약** (`study/`)
- 전기이론, 전기기기, 전기설비 핵심 내용 정리
- 시험에 자주 나오는 개념 설명

### 3. **기출문제** (`quiz/`)
- 2021년도 2회, 3회, 4회 기출문제
- 문제별 진행 상황 추적
- 제1과목(전기이론), 제2과목(전기기기), 제3과목(전기설비) 분류

### 4. **AI 센터** (`ai/`)
- OpenRouter API를 통한 GPT-4o-mini 기반 AI 튜터
- 전기기능사 관련 질문에 대한 상세한 답변
- 하루 5회 질문 제한 (쿨다운: 10분)

### 5. **설정** (`settings/`)
- 사용자 환경 설정

## 🚀 시작하기

### 로컬 실행
```bash
# 저장소 클론
git clone <repository-url>
cd stitch_

# 간단한 HTTP 서버로 실행
python -m http.server 8000
# 또는
npx http-server
```

브라우저에서 `http://localhost:8000`으로 접속하세요.

### OpenRouter API 키 설정
AI 센터를 사용하려면 OpenRouter API 키가 필요합니다:
1. [OpenRouter](https://openrouter.ai)에 가입
2. API 키 발급
3. AI 센터에 접속하면 프롬프트에서 키 입력
4. localStorage에 자동 저장됨

## 📁 프로젝트 구조

```
stitch_/
├── main/          # 메인 페이지
├── study/         # 핵심요약
├── quiz/          # 기출문제 목록
├── quizui/        # 기출문제 상세 (2021b.html, 2021c.html, 2021d.html)
├── ai/            # AI 튜터
├── settings/      # 설정
├── result/        # 결과 페이지 (예비)
├── _3.md          # 문서
└── .gitignore     # git 제외 파일 설정
```

## 🔧 기술 스택

- **Frontend**: HTML5, CSS3 (Tailwind CSS), JavaScript
- **API**: OpenRouter (AI), Finnhub (금융 정보), ExchangeRate API (환율)
- **로컬 저장소**: localStorage (사용자 답변, API 키)

## 💾 주요 파일 설명

- `main/index.html` - 메인 랜딩 페이지
- `quiz/code.html` - 기출문제 선택 페이지
- `quizui/2021b.html` - 2021년 2회 기출문제 (60문항)
- `quizui/2021c.html` - 2021년 3회 기출문제 (60문항)
- `quizui/2021d.html` - 2021년 4회 기출문제 (60문항)
- `ai/code.html` - AI 튜터 (OpenRouter API 사용)
- `study/code.html` - 핵심 내용 정리
- `settings/code.html` - 사용자 설정

## 🔐 보안 주의사항

- **API 키는 코드에 하드코딩하지 마세요**
- 사용자 입력 시 localStorage에 저장되므로 개인 기기에서만 사용 권장
- 프로덕션 배포 시 서버 사이드 인증 추가 필요

## 📝 호스팅 방법

### Netlify 배포 (권장)
```bash
# 1. GitHub에 푸시
git add .
git commit -m "Initial commit"
git push origin main

# 2. Netlify에서 GitHub 레포 연결
# - netlify.com 접속
# - "New site from Git" 선택
# - GitHub 계정 연동
# - 레포 선택 후 배포
```

### 환경 변수 설정 (Netlify)
Netlify Dashboard → Site settings → Build & deploy → Environment에서:
- `OPENROUTER_API_KEY`: OpenRouter API 키 (선택사항, 클라이언트에서 입력 가능)
- `FINNHUB_API_KEY`: Finnhub API 키 (선택사항)
- `EXCHANGERATE_API_KEY`: ExchangeRate API 키 (선택사항)

## 🤝 기여 방법

1. 이슈 제출
2. 포크 및 브랜치 생성
3. 기능 추가 또는 버그 수정
4. 풀 리퀘스트 제출

## 📄 라이선스

MIT License

## 📮 연락처

문제 발생 시 이슈를 등록해주세요.

---

**마지막 업데이트**: 2026년 4월
