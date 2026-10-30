# codex-kit

Codex 작업용 공통 규칙과 양식 모음입니다.

## 구성

| 파일 | 용도 |
|---|---|
| `AGENTS.md` | Codex가 자동으로 읽는 작업 규칙 |
| `skills/check-requirements/` | 필수 조건 점검 스킬 |
| `skills/write-worklog/` | 작업 기록 정리 스킬 |
| `templates/PLAN.md` | 계획 문서 양식 |
| `templates/WORKLOG.md` | 작업 기록 양식 |
| `prompts.md` | 단계별 요청 문장 모음 |

## 사용법

```bash
# 1. 작업 폴더 바깥에 받기
git clone https://github.com/<아이디>/codex-kit.git ~/kit

# 2. 작업 폴더에 AGENTS.md가 이미 있는지 확인
ls

# 3-a. 없으면 복사
cp ~/kit/AGENTS.md ./

# 3-b. 있으면 덮어쓰지 말고 Codex에게 합치기를 요청
#   "~/kit/AGENTS.md 내용을 기존 AGENTS.md에 겹치지 않게 추가해줘"
```

스킬은 Codex에게 파일을 직접 읽게 하면 어디서든 동작합니다.

```
~/kit/skills/check-requirements/SKILL.md를 읽고 그대로 해줘
```
