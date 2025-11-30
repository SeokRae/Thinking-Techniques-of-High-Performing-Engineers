# 워크플로우 빠른 참조 가이드

이 문서는 Issue 기반 워크플로우의 빠른 참조 가이드입니다.

상세한 설명은 [CONTRIBUTING.md](../CONTRIBUTING.md)를 참고하세요.

---

## 🚀 빠른 시작

### 모든 작업은 Issue로 시작합니다!

```
Issue 생성 → 작업 수행 → PR 생성 → 병합 → Issue 자동 닫기
```

---

## 📝 작업 유형별 워크플로우

### 1️⃣ PRD 작성

```bash
# 1. GitHub에서 Issue 생성
# - 템플릿: "PRD 작성"
# - 제목: [PRD] 프로젝트명
# - Issue #1 생성됨

# 2. 브랜치 생성
git checkout -b docs/prd-project-name

# 3. PRD 문서 작성
# - PRD-project-name.md 파일 생성
# - 요구사항, 목표, 성공 기준 작성

# 4. 커밋
git add PRD-project-name.md
git commit -m "docs(prd): add PRD for project name"

# 5. 푸시 및 PR 생성
git push origin docs/prd-project-name
# GitHub에서 PR 생성, "Closes #1" 입력

# 6. 병합
# PR 병합 → Issue #1 자동 닫기
```

### 2️⃣ 분석 작업

```bash
# 1. Issue 생성
# - 템플릿: "분석 작업"
# - 제목: [ANALYSIS] 분석 주제
# - Related PRD: #1 연결
# - Issue #2 생성됨

# 2. 브랜치 생성
git checkout -b analysis/topic-name

# 3. 분석 수행 및 리포트 작성
# - output/analysis/ 디렉토리에 결과 파일 생성

# 4. 커밋
git add output/analysis/
git commit -m "docs(analysis): add analysis report for topic"

# 5. PR 생성 및 병합
git push origin analysis/topic-name
# PR 생성, "Closes #2" 입력
```

### 3️⃣ 문서 작업

```bash
# 1. Issue 생성
# - 템플릿: "문서 작업"
# - 제목: [DOCS] 문서 작업 내용
# - Issue #3 생성됨

# 2. 브랜치 생성
git checkout -b docs/update-readme

# 3. 문서 작성/수정
# - 마크다운 파일 작성/수정
# - 링크 검증
# - 렌더링 확인

# 4. 커밋
git add README.md
git commit -m "docs: update README with new sections"

# 5. PR 생성 및 병합
git push origin docs/update-readme
# PR 생성, "Closes #3" 입력
```

### 4️⃣ 기능 개발

```bash
# 1. Issue 생성
# - 템플릿: "기능 제안"
# - 제목: [FEAT] 기능명
# - Issue #4 생성됨

# 2. 브랜치 생성
git checkout -b feature/feature-name

# 3. 개발 및 테스트
# - 코드 작성
# - 테스트 수행

# 4. 커밋
git add .
git commit -m "feat(scope): add new feature"

# 5. PR 생성 및 병합
git push origin feature/feature-name
# PR 생성, "Closes #4" 입력
```

### 5️⃣ 버그 수정

```bash
# 1. Issue 생성
# - 템플릿: "버그 리포트"
# - 제목: [BUG] 버그 설명
# - Issue #5 생성됨

# 2. 브랜치 생성
git checkout -b fix/bug-description

# 3. 버그 수정 및 테스트
# - 코드 수정
# - 재현 테스트

# 4. 커밋
git add .
git commit -m "fix(scope): fix bug description"

# 5. PR 생성 및 병합
git push origin fix/bug-description
# PR 생성, "Fixes #5" 입력
```

---

## 📋 Issue 템플릿 선택 가이드

| 상황 | 템플릿 | 브랜치 | 커밋 타입 |
|------|--------|--------|-----------|
| 새 프로젝트 시작 | PRD 작성 | `docs/prd-*` | `docs(prd):` |
| 코드/데이터 분석 | 분석 작업 | `analysis/*` | `docs(analysis):` |
| 문서 생성/수정 | 문서 작업 | `docs/*` | `docs:` |
| 새 기능 추가 | 기능 제안 | `feature/*` | `feat(scope):` |
| 버그 발견 | 버그 리포트 | `fix/*` | `fix(scope):` |

---

## ✅ PR 체크리스트 (필수)

### Issue 연결

```markdown
## 📌 관련 이슈

Closes #번호

**Issue 제목**: [TYPE] 제목
```

### 체크리스트

- [ ] Issue에서 정의한 모든 목표 달성
- [ ] Issue의 성공 기준 충족
- [ ] 커밋 메시지 컨벤션 준수
- [ ] 불필요한 파일 제외
- [ ] 로컬 테스트 완료
- [ ] README 업데이트 (필요 시)

---

## 🔗 자동 닫기 키워드

PR 설명에 다음 키워드를 사용하면 병합 시 Issue가 자동으로 닫힙니다:

- `Closes #123` - Issue 닫기
- `Fixes #123` - 버그 수정 Issue 닫기
- `Resolves #123` - Issue 해결 및 닫기

여러 이슈를 닫으려면:

```markdown
Closes #123, #124, #125
```

---

## 📊 커밋 메시지 컨벤션

```
<type>(<scope>): <subject>

type: feat, fix, docs, style, refactor, test, chore
scope: 변경 범위 (chapters, scripts, docs 등)
subject: 간결한 설명 (50자 이내)
```

### 예시

```bash
feat(chapters): add chapter 08 advanced topics
fix(output): correct file path in README
docs: update CONTRIBUTING guide
docs(prd): add PRD for chapter analysis project
docs(analysis): add chapter quality report
```

---

## 🎯 브랜치 명명 규칙

```
<type>/<description>

type: feature, fix, docs, refactor, analysis
description: 케밥-케이스 (소문자, 하이픈)
```

### 예시

```bash
docs/prd-chapter-analysis
analysis/chapter-quality-check
docs/update-contributing
feature/add-ocr-correction
fix/broken-links
```

---

## 🔄 전체 프로세스 (한눈에 보기)

```
┌─────────────────────────────────────────────────────────────┐
│                    1. GitHub에서 Issue 생성                  │
│   템플릿 선택 → 제목/내용 작성 → 라벨 추가 → Issue #N 생성   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                  2. 로컬에서 브랜치 생성                     │
│          git checkout -b type/description                    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     3. 작업 수행                             │
│   PRD 작성 / 분석 수행 / 문서 작성 / 코드 개발 / 버그 수정   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    4. 커밋 (컨벤션 준수)                     │
│   git add . → git commit -m "type(scope): subject"           │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                  5. 푸시 및 PR 생성                          │
│   git push origin branch-name → GitHub에서 PR 생성           │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                  6. PR에 Issue 연결                          │
│   PR 설명에 "Closes #N" 추가 → 목표 및 체크리스트 작성      │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    7. 리뷰 및 테스트                         │
│        자체 리뷰 → 테스트 → 수정 (필요 시)                  │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     8. PR 병합                               │
│   Squash and merge → main 브랜치에 병합 → Issue 자동 닫기   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   9. 브랜치 삭제 및 정리                     │
│   git checkout main → git pull → git branch -d branch-name   │
└─────────────────────────────────────────────────────────────┘
```

---

## 💡 팁

### Issue 작성 시

- ✅ 구체적이고 명확한 제목
- ✅ 체크리스트로 작업 단계 정의
- ✅ 관련 Issue/PRD 연결
- ✅ 적절한 라벨 추가
- ✅ 우선순위 명시

### PR 생성 시

- ✅ Issue 번호 필수 연결
- ✅ Issue의 목표를 PR 목표로 복사
- ✅ 모든 체크리스트 확인
- ✅ 테스트 결과 포함
- ✅ 스크린샷 첨부 (필요 시)

### 커밋 시

- ✅ 의미 있는 단위로 커밋
- ✅ 컨벤션 준수
- ✅ 명확한 커밋 메시지
- ✅ 불필요한 파일 제외

---

## 📚 참고 문서

- [CONTRIBUTING.md](../CONTRIBUTING.md) - 상세한 기여 가이드
- [README.md](../README.md) - 프로젝트 개요
- [GitHub Issues 문서](https://docs.github.com/en/issues)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

**빠른 시작을 원하신다면** 이 가이드를 북마크하고 참조하세요! 🎉
