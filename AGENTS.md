# LG전자 AX 팀 프로젝트 규칙
이 파일은 Claude Code, Codex 등 모든 AI 도구가 따르는 팀 규칙입니다.

## 팀원
| 이름 | GitHub ID | 영문 이름 | 역할 |
| --- | --- | --- | --- |
| 강태우 | 0216tw | taewoo | 팀장 |
| 김현식 | 0216tw-clone | hyunsik | 팀원 |

## 브랜치 규칙
- 형식: `<타입>/<영문 이름>/<기능>`
- 타입: feat(새 기능), fix(버그), docs(문서), refactor(정리), test(테스트), chore(설정)
- 예시: `feat/taewoo/alert-setting`, `docs/taewoo/erd`

## 커밋 규칙
- 형식: `타입: 한글 요약`
- 커밋 하나에는 의도 하나만 담습니다.

## 작업 순서
1. 최신 main 받기
2. 규칙에 맞는 브랜치 만들기
3. 작업 → 커밋 → push
4. Code Review Rules로 셀프 리뷰 → PR 올리기
5. 팀원 1명이 승인하면 PR을 올린 사람이 merge

## 최신 내용 받기
- `git switch main` → `git pull`
- 작업 중인 브랜치에 main 변경을 반영할 때: 위를 먼저 한 뒤 `git switch <내 브랜치>` → `git merge main`

## PR 규칙
- 제목: `타입: 한글 요약`
- 본문: `.github/pull_request_template.md` 형식
- PR 전에 Code Review Rules로 셀프 리뷰하고, 결과를 "AI 리뷰 결과"에 적습니다.

## 충돌 해결
- PR을 올린 사람이 자기 브랜치에서 해결합니다.
- 충돌난 양쪽 내용을 보여주고, 어떻게 합칠지 사용자에게 확인받은 뒤 반영합니다.
- 다른 사람이 쓴 부분의 의도가 애매하면 그 사람과 상의합니다.

## 에이전트 규칙
- main에서 바로 작업하지 않고 규칙에 맞는 브랜치부터 만듭니다.
- main 직접 push와 force push는 하지 않습니다.
- `.env`, API 키, `docs/00_source/`의 파일(README.md 제외)은 절대 커밋하지 않습니다.
- 커밋·push 전에 변경 요약을 보여주고 확인을 받습니다.
- 코드를 바꾸면 `docs/`의 관련 산출물도 같은 PR에서 고칩니다.

## Code Review Rules
- API 키·비밀번호가 코드나 프론트 환경변수에 들어가지 않았는가
- 사용자 입력을 검증하고, 실패 시 사용자에게 안내하는가
- AI 호출에 타임아웃과 실패 시 대체 동작이 있는가
- 프론트와 백엔드의 API 요청·응답 형식이 docs의 명세와 같은가
- 코드를 바꿨는데 docs/의 관련 문서가 그대로면 지적한다
