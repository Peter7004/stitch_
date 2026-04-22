# Git 레포지토리 설정 및 배포 가이드

## ✅ Git에 올리기 전에 확인하세요

### 1. .gitignore 확인
이미 생성되었습니다. 다음이 제외됩니다:
- `.env` 파일 (API 키)
- `node_modules/`
- IDE 설정 파일
- 캐시 및 로그 파일

### 2. 민감한 정보 제거
- ❌ API 키를 코드에 직접 입력하지 마세요
- ✅ localStorage에서 사용자가 입력하도록 설정됨
- ✅ 서버 배포 시 환경 변수로 관리

### 3. 필요한 파일 확인
다음 파일들이 생성되었습니다:
- `.gitignore` - Git 제외 설정
- `README.md` - 프로젝트 설명
- `.env.example` - 환경 변수 템플릿
- `package.json` - 프로젝트 메타데이터
- `netlify.toml` - Netlify 배포 설정

---

## 🚀 Git 레포지토리 생성 및 푸시

### 1단계: 로컬 Git 초기화
```bash
cd /path/to/stitch_
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

### 2단계: 파일 추가 및 커밋
```bash
# 모든 파일 추가 (제외 파일은 .gitignore로 자동 제외)
git add .

# 커밋 메시지 작성
git commit -m "Initial commit: ElecMaster 전기기능사 학습 플랫폼"
```

### 3단계: 원격 레포지토리 연결

#### GitHub 사용 (권장)
```bash
# GitHub에서 새 레포지토리 생성 후:
git branch -M main
git remote add origin https://github.com/yourusername/elecmaster.git
git push -u origin main
```

#### GitLab 사용
```bash
git branch -M main
git remote add origin https://gitlab.com/yourusername/elecmaster.git
git push -u origin main
```

---

## 🌐 Netlify에 배포하기

### 1단계: GitHub 연결
1. [Netlify](https://netlify.com)에 가입
2. GitHub 계정 연결
3. 레포지토리 선택

### 2단계: 배포 설정
- **Build command**: 비우기 (정적 사이트이므로 불필요)
- **Publish directory**: `.` (루트)

### 3단계: 환경 변수 설정 (선택사항)
Netlify Dashboard에서:
```
Site settings → Build & deploy → Environment
```

다음 변수 추가 (선택사항):
- `OPENROUTER_API_KEY` = [API 키]
- `FINNHUB_API_KEY` = [API 키]
- `EXCHANGERATE_API_KEY` = [API 키]

> **주의**: 클라이언트에서 API를 직접 호출하므로, API 키는 환경 변수가 아닌 사용자 입력(localStorage)으로 관리됨

### 4단계: 배포 확인
```
https://[sitename].netlify.app
```

---

## 🔒 보안 체크리스트

- [ ] .gitignore에 .env 파일이 포함됨
- [ ] API 키가 코드에 하드코딩되지 않음
- [ ] localStorage 사용자 입력 방식 확인
- [ ] git history에서 민감한 정보가 없음
- [ ] 배포 후 프라이빗 데이터 없음 확인

---

## 📋 배포 후 확인 사항

1. **웹사이트 접속 테스트**
   ```
   https://[sitename].netlify.app
   ```

2. **AI 센터 테스트**
   - API 키 입력 가능 여부 확인
   - 질문 입력 및 응답 테스트

3. **기출문제 로드 테스트**
   - 각 년도/회차 문제 정상 로드
   - 문제 선택 및 진행 상황 저장

4. **환율/금융 정보 로드**
   - 실시간 정보 업데이트 확인

---

## 🔄 향후 업데이트 및 배포

### 코드 수정 후 배포
```bash
git add .
git commit -m "설명: 변경 내용"
git push origin main
```

### 자동 배포
- Netlify는 GitHub 푸시를 감지하여 자동 배포
- 빌드 로그: Netlify Dashboard → Deploys

---

## ❓ 자주 묻는 질문

### Q1: API 키를 안전하게 보호하려면?
**A**: 현재 방식(localStorage, 사용자 입력)은 로컬 개발용입니다. 프로덕션에서는:
- 백엔드 서버 구축
- 서버 환경 변수로 API 키 관리
- 클라이언트는 서버를 통해서만 API 호출

### Q2: 프라이빗 레포지토리 사용 가능?
**A**: 네, 가능합니다. GitHub/GitLab에서 프라이빗 설정 후 Netlify 연결

### Q3: 배포 취소 방법?
**A**: Netlify Dashboard → Deploys → 해당 배포 → Unpublish

### Q4: 자체 도메인 연결 방법?
**A**: Netlify Dashboard → Domain settings → 도메인 추가

---

## 📞 문제 해결

### Git 푸시 오류
```bash
# 다시 시도
git pull origin main
git push origin main
```

### Netlify 배포 실패
- Netlify Dashboard → Deploys → 실패한 배포 → 로그 확인
- 대개 환경 설정 문제

### API 호출 실패
- 브라우저 개발자도구(F12) → Network, Console 확인
- API 키 입력 여부 확인

---

**모든 설정이 완료되었습니다! 이제 git에 안전하게 올릴 수 있습니다.** 🎉
