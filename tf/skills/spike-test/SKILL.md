---
description: "Spike 테스트: agent 병렬 호출 검증. 테스트가 끝나면 삭제 예정."
user-invocable: true
allowed-tools: Bash, Glob, Grep, Read, Write, Task
argument-hint: "<리서치 주제>"
---

# Spike 테스트: Agent 병렬 호출

## 목적
Skill 안에서 여러 agent를 병렬로 호출할 수 있는지 검증한다.

## 진행 방식

1. 사용자로부터 리서치 주제를 받는다 (argument로 전달됨).

2. **Task 도구를 사용하여 2개의 agent를 병렬로 실행한다:**
   - test-agent-a: 주제에 대한 기본 리서치
   - test-agent-b: 주제에 대한 대안/경쟁 리서치
   - 두 Task를 **동시에** 호출한다 (하나의 메시지에서 두 개의 Task tool call).

3. 두 agent의 결과를 받으면 종합하여 사용자에게 보여준다.

4. 검증 결과를 보고한다:
   - 병렬 호출이 가능했는가?
   - 각 agent가 독립적으로 동작했는가?
   - 결과를 종합할 수 있었는가?
