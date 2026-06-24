# repo 구조 제안

## 우선순위

| 우선순위 | repo | 역할 | 유지보수 비용 | 운영자가 해야 할 일 |
|---|---|---|---|---|
| P0 | `.github` | org 프로필, 공통 운영 문서, 기본 Issue/PR 템플릿 | 낮음 | 월 1회 링크 점검, 운영 원칙 갱신, 새 repo 제안 triage |
| P1 | `hub-docs` 또는 `KCU-Hub.github.io` | GitHub Pages 기반 공개 안내 사이트 | 중간 | 문서 IA 관리, 홈/가이드 갱신, 깨진 링크 점검 |
| P1 | `curriculum-roadmap` | 학기별, 주제별 학습 경로 | 중간 | 로드맵 issue 관리, 학기 말 정리, 난이도 태그 관리 |
| P1 | `course-notes` | 과목별 공개 노트와 참고 링크 | 중간 | 과목 폴더 규칙 유지, 오래된 링크 정리, 출처 표시 점검 |
| P2 | `workshops` | 워크숍 실습 자료, 발표 자료, starter 템플릿 | 중간 | 실습 검증, 실행 방법 업데이트, 자료 버전 관리 |
| P2 | `project-ideas` | 프로젝트 아이디어, 난이도, 예상 산출물, 멘토링 메모 | 낮음 | 중복 제거, 난이도 조정, 완료 repo 링크 연결 |
| P3 | `awesome-cuk-sw` | 외부 자료와 내부 repo 큐레이션 | 낮음 | 링크 신선도 점검, 카테고리 정리, 홍보성 링크 제한 |

## 추천 생성 순서

1. `.github`로 org 첫 화면과 운영 원칙을 고정합니다.
2. `hub-docs`로 GitHub Pages 공개 문서를 만듭니다.
3. `curriculum-roadmap`과 `course-notes`를 나눕니다.
4. 실제 워크숍이 2회 이상 쌓이면 `workshops`를 만듭니다.
5. 프로젝트 제안이 10개 이상 쌓이면 `project-ideas`를 만듭니다.
6. 외부 자료 추천이 반복되면 `awesome-cuk-sw`를 만듭니다.

## repo별 권장 구조

### `.github`

```text
profile/README.md
docs/operating-model.md
docs/repo-structure.md
docs/channel-policy.md
docs/maintainer-checklist.md
.github/ISSUE_TEMPLATE/docs-update.yml
.github/ISSUE_TEMPLATE/repo-proposal.yml
.github/pull_request_template.md
```

### `hub-docs`

```text
README.md
docs/getting-started.md
docs/repo-index.md
docs/study-guide.md
docs/project-guide.md
docs/maintainer-guide.md
```

GitHub Pages는 이 repo에서만 운영하는 것을 권장합니다. 여러 repo에서 Pages를 켜면 운영자가 배포 상태를 따라가기 어렵습니다.

### `curriculum-roadmap`

```text
README.md
roadmaps/first-year.md
roadmaps/web.md
roadmaps/data-ai.md
roadmaps/security.md
templates/roadmap-item.md
```

### `course-notes`

```text
README.md
courses/_template.md
courses/programming-basics/README.md
courses/database/README.md
courses/software-engineering/README.md
```

과목 폴더에는 공개 가능한 요약과 참고 링크만 둡니다. 성적, 수강자 정보, 비공개 강의 자료는 올리지 않습니다.

### `workshops`

```text
README.md
workshops/_template/
workshops/github-basics/
workshops/web-deploy/
workshops/ai-app-prototype/
```

### `project-ideas`

```text
README.md
ideas/_template.md
ideas/beginner/
ideas/intermediate/
ideas/advanced/
```

### `awesome-cuk-sw`

```text
README.md
sections/github.md
sections/web.md
sections/ai.md
sections/career.md
```

## 생성 보류 기준

| 상황 | 처리 |
|---|---|
| 자료가 3개 미만입니다. | 기존 docs repo의 한 문서로 시작합니다. |
| 유지보수자가 없습니다. | Issue로만 제안하고 repo 생성을 보류합니다. |
| 채팅방 공지에 가까운 내용입니다. | 외부 채널에 둡니다. |
| 민감 정보 제거가 어렵습니다. | 공개 repo에 올리지 않습니다. |
| 기존 repo와 목적이 겹칩니다. | 폴더나 문서로 흡수합니다. |
