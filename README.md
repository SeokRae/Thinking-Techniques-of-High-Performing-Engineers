# 일 잘하는 엔지니어의 생각 기법 (Markdown Edition)

**원본**: "일 잘하는 엔지니어의 생각 기법" (캐리 밀샙 지음, 장현희 옮김)  
**목적**: PDF를 Markdown으로 변환하고, 학습/복습이 쉽도록 챕터별·주제별로 재구성합니다. (주요 산출물은 로컬에서 생성하며 git에는 포함하지 않습니다.)

---

## 로컬에 무엇이 생성되나요?

- `output/chapters/` — 주제별로 다시 엮은 챕터 모음 *(git 미추적, 로컬 생성)*
- `README.md` — 이 안내서

프로젝트 전체 구조는 아래와 같습니다.

```
project-root/
├── output/              # 변환 결과 (gitignore)
│   └── chapters/        # 주제별 재정리 (gitignore)
├── CONTRIBUTING.md
└── README.md
```

---

## 어떻게 읽으면 좋을까요?

1) **주제별 학습**: `output/chapters/01-observation.md` 등 챕터별 파일  
2) **순서대로 읽기**: `output/chapters/00-intro.md` → `output/chapters/01-observation.md` → …

터미널 예시 (로컬 생성 후):

```bash
ls output/chapters/
cat output/chapters/01-observation.md
```

---

## 협업·기여 가이드 (요약)

- 모든 작업은 Issue로 시작 → 브랜치 → PR → 병합 → Issue 자동 종료
- 브랜치 예시: `docs/prd-*`, `analysis/*`, `docs/*`, `feature/*`, `fix/*`
- 커밋 메시지: Conventional Commits (`type(scope): subject`)
  - 예: `docs(chapters): refine observation chapter`
- 상세한 워크플로우: `CONTRIBUTING.md`, `.github/WORKFLOW.md`

---

## 저장소 관리 메모

- `output/`는 gitignore 대상입니다. 로컬에서만 생성·활용하세요.
- 챕터 파일(`output/chapters/*.md`)은 필요 시 재생성하거나 수동 정리해 사용합니다.
- 로컬 참고용 문서가 있다면 gitignore 하에 두고, 공유가 필요할 때만 명시적으로 포함하세요.

---

## 라이선스 및 활용

- 학습/연구 목적으로 제공되며, 원본 책의 저작권은 저자와 출판사에 있습니다.
- 변환물 사용 시 출처를 명시하고 상업적 이용은 피해주세요.

---

## 빠른 길잡이

- 바로 읽기: `output/chapters/00-intro.md`, `output/chapters/01-observation.md`
- 작업 시작: Issue 등록 → 브랜치 생성 → PR
- 질문/아이디어: Issue에 남기면 빠르게 대응합니다.
