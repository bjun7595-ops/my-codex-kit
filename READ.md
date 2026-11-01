# ai-build-harness

시간 제한이 있는 **"데이터 + 업무 규칙 → 계산·최적화 → 역할별 웹 서비스"** 빌드 과제를 코딩 에이전트와 함께 수행하기 위한 하네스.
Codex 규격(`AGENTS.md` + `.agents/skills/<이름>/SKILL.md`)을 따른다.

**코드는 들어 있지 않다.** 절차, 체크리스트, 판단 기준, 알고리즘 아이디어만 담고, 구현은 매번 작업 공간에서 에이전트와 새로 한다.

## 설치

작업 공간의 루트 `README.md`나 기존 파일을 덮어쓰지 않도록, 다른 위치에 받아서 필요한 것만 복사한다.

```bash
git clone --depth 1 <this-repo-url> /tmp/ai-build-harness
cd <작업_공간>
cp /tmp/ai-build-harness/AGENTS.md .            # 이미 AGENTS.md 가 있으면 내용을 합친다
mkdir -p .agents
cp -R /tmp/ai-build-harness/.agents/skills .agents/
```

설치 후 에이전트에게: **"AGENTS.md를 읽고 task-kickoff 스킬로 시작해."**

## 구성

```
AGENTS.md                      절대 규칙 · 우선순위 · 진행 방식(브리핑→구역→얇게 연결→두껍게) · 기록 형식 · 문서 검색 · 마감 체크
.agents/skills/
  task-kickoff/                첫 브리핑(BRIEF.md), 요구사항 매트릭스, 함정 체크리스트, 구역 지도·시연 시나리오
  data-audit/                  데이터 전수 점검 항목과 관찰 → 행동
  stakeholder-questions/       업무 담당자 질문 유형·작성법·반영
  dataset-lifecycle/           데이터셋 선택·검증·적용, 결과 최신성, 변형 데이터 준비
  optimization-strategy/       문제 유형 판별, 제약 3층, 사전식 기준, 시나리오 비교
  routing-problems/            노선·순회형
  assignment-problems/         배정·매칭형
  scheduling-problems/         일정·시간표·교대형
  selection-packing/           거점 선정·덮개·적재·선택형
  result-verifier/             엔진과 독립된 결과 검증기 설계
  web-service/                 서버·DB·로그인·역할·파일창 없는 내보내기
  visual-views/                지도 없는 그래프, 타임라인, 진행 위치 보간
  deploy-if-required/          배포 준비 요구가 있을 때만
  submission/                  시연 확인, 제출 문서, 마지막 점검
  retrieval-qa/                과제가 문서 질의응답·검색 서비스일 때
```

## 원칙

1. 하드 규칙 준수와 검증 가능성이 최우선. 결과는 엔진과 독립된 검증기로 확인한다.
2. 필수 기능의 폭이 최적화 깊이보다 먼저.
3. 업무 해석은 담당자에게 확인하고 기록한다. 확인 못 한 것은 [가정].
4. 결과·오류 하드코딩 금지, 지정 데이터 대체 금지, 응시 환경 제약 준수, 외부 전송 금지.
5. 외부 코드는 일부 알고리즘 차용만, 출처 명시.

사용하는 환경의 규정(허용 도구, 외부 자료 범위)을 먼저 확인하고 그 범위 안에서 쓴다.
