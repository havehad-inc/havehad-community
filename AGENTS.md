# AGENTS.md — havehad-community (월간 해브해드)

정적 사이트(HTML·CSS·JS, 빌드 없음). 구조·로컬 실행은 `README.md`.

## 회사 작업 시작 — 세션 첫 작업 전에 에이전트가 스스로

멤버는 명령을 치지 않는다. 아래를 조용히 하고, 막힌 것만 한 줄로 알린다.

1. cwd 가 `~/Havehad` 아래 회사 저장소(`havehad-company`·`havehad-management`·`havehad-community`)인지 확인한다. 아니면 작업하지 말고 그 폴더를 열도록 안내한다.
2. `git -C ~/Havehad/havehad-company status --short` 가 비어 있을 때만 `git -C ~/Havehad/havehad-company pull --ff-only` 한다. 지금 연 저장소도 같은 방식이다. 비어 있지 않으면 당기지 않는다 — 멤버의 미커밋 작업이다.
3. 이번 작업이 ERP·구글 시트를 쓰면 회사 스킬 `erp-direct`·`google-sheets-direct` 의 건강 점검을 먼저 한 번 돌려 직접 연결을 확인한다. 실패하면 그 스킬의 안내대로 복구하고, 안 되면 멤버에게 한 줄로 알린다.

## 마감 — 턴을 끝내기 전에

회사 지식(`havehad-company`)에만 해당한다. 이 저장소는 `main` push 가 곧 공개 사이트 배포(Vercel)이므로, 이 저장소 코드의 커밋·push 는 사람이 요청했을 때만 한다.

1. `git -C ~/Havehad/havehad-company status --short --branch` 를 본다. 이번 세션이 만든 회사 지식이 미커밋이거나 push 안 된 커밋이 있으면 끝내지 않는다.
2. 남길 것만 골라 `python3 scripts/validate_knowledge.py`(havehad-company 에서) 통과 후, 내가 만든 경로만 지정해 커밋하고 push 한다. push 가 거부되면 `git pull --rebase` 후 다시 push 하고, 충돌이면 덮어쓰지 말고 알린다.
3. 남길 가치가 없는 변경이면 무엇을 왜 안 남겼는지 한 줄로 알린다. 상세 절차는 회사 스킬 `회사작업-마무리`.

## 안전

- 사람만 확정하는 일 — 계약·가격·급여·인사평가 — 은 **초안까지만** 만든다. 확정·발송·시스템 반영은 사람에게 넘긴다.
- git: force-push·`reset --hard`·history rewrite 금지. `git add -A`·`git add .`·`commit -a` 같은 광역 스테이징 금지 — 내가 만든 경로만 지정한다. 남의 미커밋 변경은 건드리지 않는다.
- 급여·보상·인사평가·고객 개인정보(PII) 원문·비밀번호·토큰·키는 저장소에 쓰지 않는다. 발견하면 읽거나 옮기지 말고 위치만 알린다.
