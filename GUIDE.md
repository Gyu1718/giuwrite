# Brunch CMS — 완전 설정 가이드

## 필요한 것들

- Google 계정
- GitHub 계정 (이미 있음 ✓)
- 스마트폰 or 태블릿 (Safari / Chrome)

---

## 1단계 — GitHub 설정

### 1-1. 새 레포지토리 만들기

1. github.com 접속 → 로그인
2. 우측 상단 **+** → **New repository**
3. Repository name: `brunch-cms` (또는 원하는 이름)
4. **Public** 선택
5. **Create repository**

### 1-2. 파일 업로드

1. `brunch_pwa_v2.zip` 압축 풀기
2. GitHub 레포 페이지에서 **Add file → Upload files**
3. 4개 파일 모두 드래그:
   - `index.html`
   - `portfolio.html`
   - `manifest.json`
   - `sw.js`
   - `icon.svg`
4. **Commit changes**

### 1-3. GitHub Pages 활성화

1. 레포 상단 **Settings** 탭
2. 좌측 메뉴 **Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / **(root)** 선택
5. **Save**

약 1~2분 후 주소 생성:
```
https://계정명.github.io/brunch-cms
```

---

## 2단계 — Google Drive 연동 설정

### 2-1. Google Cloud Console

1. console.cloud.google.com 접속
2. 상단 **새 프로젝트** 클릭
3. 프로젝트 이름: `Brunch CMS` → **만들기**

### 2-2. Google Drive API 활성화

1. 좌측 메뉴 **API 및 서비스 → 라이브러리**
2. 검색: `Google Drive API`
3. **사용 설정**

### 2-3. OAuth 동의 화면

1. **API 및 서비스 → OAuth 동의 화면**
2. 사용자 유형: **외부** → **만들기**
3. 앱 이름: `Brunch CMS`
4. 사용자 지원 이메일: 내 이메일
5. **저장 후 계속** (나머지는 기본값)

### 2-4. OAuth Client ID 발급

1. **API 및 서비스 → 사용자 인증 정보**
2. **+ 사용자 인증 정보 만들기 → OAuth 클라이언트 ID**
3. 애플리케이션 유형: **웹 애플리케이션**
4. 이름: `Brunch CMS Web`
5. 승인된 JavaScript 원본 추가:
   ```
   https://계정명.github.io
   ```
   (로컬 테스트용 추가):
   ```
   http://localhost
   http://127.0.0.1
   ```
6. **만들기**
7. **클라이언트 ID** 복사 (형식: `숫자-영문자.apps.googleusercontent.com`)

### 2-5. 앱에 연결

1. `https://계정명.github.io/brunch-cms` 접속
2. 우측 상단 **설정** 버튼
3. **Google Drive 동기화** 섹션
4. Client ID 붙여넣기
5. **Google Drive 연결** 버튼
6. Google 로그인 팝업 → 허용
7. "Google Drive 연결됨 ✓" 토스트 확인

---

## 3단계 — GitHub 포트폴리오 설정

### 3-1. Personal Access Token 발급

1. GitHub → 우측 상단 프로필 → **Settings**
2. 좌측 맨 아래 **Developer settings**
3. **Personal access tokens → Tokens (classic)**
4. **Generate new token (classic)**
5. Note: `Brunch CMS Portfolio`
6. Expiration: **No expiration**
7. Scope: **repo** 체크
8. **Generate token**
9. 토큰 복사 (페이지 이동 시 다시 볼 수 없음!)

### 3-2. 앱에 입력

1. 앱 설정 → **GitHub 포트폴리오** 섹션
2. Personal Access Token 붙여넣기
3. GitHub 계정명 입력 (예: `giukim`)
4. 레포 이름 입력 (예: `brunch-cms`)
5. **저장**

---

## 4단계 — PWA 설치 (홈 화면)

### iPhone / iPad (Safari)

1. Safari에서 `https://계정명.github.io/brunch-cms` 접속
2. 하단 공유 버튼 (□↑)
3. **홈 화면에 추가**
4. 이름 확인 → **추가**

### Android (Chrome)

1. Chrome에서 접속
2. 우측 상단 ⋮ → **앱 설치** 또는 **홈 화면에 추가**

### Mac / PC (Chrome)

1. Chrome에서 접속
2. 주소창 우측 설치 아이콘(⊕) 클릭
3. **설치**

---

## 매일 사용하는 방법

### 기본 흐름

```
앱 열기 (홈 화면 아이콘)
  → 자동으로 Google Drive 연결
  → 모든 기기에서 동일한 데이터
```

### 새 에피소드 작성

1. 사이드바에서 에피소드 선택
2. **아웃라인** 탭 → 각 필드 클릭해서 직접 수정
3. **에디터** 탭 → 마크다운으로 집필
4. 자동 저장 (1.8초 후)

### 마크다운 기본 문법

```markdown
# 제목 1
## 제목 2

**굵게** *기울임*

> 인용문

- 목록 항목
1. 번호 목록

---  (구분선)
```

### 테마/폰트 변경

설정 → 테마 6종 / 서체 4종 / 글자 크기 / 줄 간격

---

## 포트폴리오 업데이트

에피소드를 추가하거나 아웃라인을 수정한 후:

1. 에피소드 선택 (에피소드가 있어야 버튼이 표시됨)
2. 상단 **↑ 포트폴리오** 버튼
3. 잠시 후 "포트폴리오 업데이트 완료 ✓"

공개 URL: `https://계정명.github.io/brunch-cms/portfolio.html`

RSS: `https://계정명.github.io/brunch-cms/rss.xml`

---

## SEO 설정

1. 사이드바에서 연재 에피소드 선택
2. 설정 → **SEO 설정** 섹션
3. 포트폴리오 페이지 제목, 설명, 키워드 입력
4. **SEO 저장** → **↑ 포트폴리오** 업데이트

---

## 버전 히스토리

에피소드 집필 중 → 상단 **히스토리** 버튼  
최근 10개 버전 확인 → 원하는 버전으로 복원 가능

---

## 데이터 백업

설정 → **전체 데이터 백업 (JSON)**  
→ `brunch_backup_날짜.json` 저장

복원: **데이터 복원** → JSON 파일 선택

---

## 커스텀 도메인 연결 (선택)

`giu.kr` 같은 개인 도메인이 있다면:

1. 도메인 DNS 설정에서 CNAME 추가:
   ```
   이름: @  또는  www
   값:  계정명.github.io
   ```
2. GitHub 레포 → Settings → Pages → Custom domain 입력
3. Enforce HTTPS 체크

---

## 문제 해결

**Google Drive 연결이 안 될 때**
- OAuth Client ID가 정확한지 확인
- 승인된 JavaScript 원본에 앱 URL이 추가되어 있는지 확인
- 팝업 차단 해제

**포트폴리오 업데이트가 안 될 때**
- GitHub PAT가 만료되지 않았는지 확인
- 레포 이름과 계정명이 정확한지 확인
- PAT에 `repo` 권한이 있는지 확인

**앱이 오래된 버전으로 보일 때**
- 브라우저 강제 새로고침: Shift+새로고침
- 또는 설정 → 애플리케이션 → 서비스 워커 → 제거 후 재접속

