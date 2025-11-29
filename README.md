# 일 잘하는 엔지니어의 생각 기법 (Markdown Edition)

**원본**: "일 잘하는 엔지니어의 생각 기법" (캐리 밀샙 지음, 장현희 옮김)  
**목적**: PDF를 Markdown으로 변환하고, 학습/복습이 쉽도록 챕터별·주제별로 재구성합니다.

---

## 무엇이 들어 있나요?

- `output/raw/` — PDF를 페이지 단위로 그대로 변환한 원본 28개
- `output/chapters/` — 주제별로 다시 엮은 7개 챕터
- `output/guides/` — 학습/실습용 요약 가이드 6개
- `output/00-README.md` — 위 세 가지 묶음의 상세 안내
- `books-source/` — 원본 PDF (저작권 주의)
- 스크립트 — `scripts/pdf_to_markdown.py`, `scripts/generate_toc_index.py`, `scripts/create_optimized_guides.py` 등 변환·색인 도구 *(재생성 가능, git 미추적)*
- 프로세스/체크리스트 — `docs/process/PRD-chapter-improvement.md`, `docs/checklists/CHAPTER-IMPROVEMENT-CHECKLIST.md`

프로젝트 전체 구조는 아래와 같습니다.

```
project-root/
├── output/
│   ├── raw/             # PDF 직접 변환
│   ├── chapters/        # 주제별 재정리
│   └── guides/          # 학습용 가이드
├── books-source/        # 원본 PDF
├── archive/             # 일회용 스크립트
├── scripts/             # 변환/정리 스크립트
├── docs/                # PRD, 체크리스트 등 프로세스 문서
├── CONTRIBUTING.md
└── README.md
```

---

## 어떻게 읽으면 좋을까요?

1) **빠른 훑어보기**: `output/guides/00-LEARNING-GUIDE.md`  
2) **주제별 학습**: `output/chapters/01-observation.md` 등 챕터별 파일  
3) **원문 순서로 정독**: `output/raw/01-p001-014.md`부터 순서대로  
4) **찾아보기/색인**: `output/02-INDEX.md`, `scripts/generate_toc_index.py`

터미널 예시:

```bash
ls output/chapters/
cat output/guides/02-core-concepts.md
```

---

## 스크립트로 변환·갱신하기

> 원본 PDF 접근 시 저작권을 준수하세요.

- PDF → Markdown: `python scripts/pdf_to_markdown.py`
- 목차/색인 생성: `python scripts/generate_toc_index.py`
- 가이드 리프레시: `python scripts/create_optimized_guides.py`

필요 도구: Python 3.9+, Git, PyPDF2 설치(`pip install PyPDF2`)

---

## 협업·기여 가이드 (요약)

- 모든 작업은 Issue로 시작 → 브랜치 → PR → 병합 → Issue 자동 종료
- 브랜치 예시: `docs/prd-*`, `analysis/*`, `docs/*`, `feature/*`, `fix/*`
- 커밋 메시지: Conventional Commits (`type(scope): subject`)
  - 예: `docs(chapters): refine observation chapter`
- 상세한 워크플로우: `CONTRIBUTING.md`, `.github/WORKFLOW.md`

---

## 저장소 관리 메모

- `output/raw/`는 원본 변환물이라 git에서 제외되어 있습니다. 필요 시 스크립트로 재생성하세요.
- `scripts/`는 로컬 유틸 모음으로 git에서 제외되어 있습니다. 공유가 필요하면 `.gitignore`에서 제외 후 커밋하세요.
- 프로세스 문서·체크리스트는 `docs/`에 모여 있습니다.

---

## 라이선스 및 활용

- 학습/연구 목적으로 제공되며, 원본 책의 저작권은 저자와 출판사에 있습니다.
- 변환물 사용 시 출처를 명시하고 상업적 이용은 피해주세요.

---

## 빠른 길잡이

- 바로 읽기: `output/00-README.md`, `output/guides/00-LEARNING-GUIDE.md`
- 작업 시작: Issue 등록 → 브랜치 생성 → PR
- 질문/아이디어: Issue에 남기면 빠르게 대응합니다.
