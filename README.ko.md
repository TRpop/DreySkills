# Drey 스킬

[English](README.md) · **한국어**

Drey Browser 의 AI Agent 화면이 Claude Code·Codex 세션에 더하는 스킬 모음입니다. 형식은 [Agent Skills](https://agentskills.io/specification) — 스킬마다 `skills/<이름>/SKILL.md`(머리에 `name`·`description`, 이어서 지침).

| 스킬 | 하는 일 | 출처 |
|---|---|---|
| debugging | 버그·오류·시험 실패·예상과 다른 결과를 고치기 전에 쓴다 | obra/superpowers (MIT) 기반 |
| handoff | 사용자가 인수인계 문서를 부탁하거나 실제로 다른 세션에 일을 넘길 때만 docs/drey/handoff.md 를 쓴다. 세션을 바꾸거나 대화를  | 자체 작성 |
| plan-consensus | 새 기능·새 일·큰 변경을 시작하기 전에 | obra/superpowers (MIT) 기반 |
| port-check | 포팅(다른 언어·구현으로 옮김) 결과가 같은지 확인할 때 | 자체 작성 |
| update-docs | 단계를 끝냈거나 합의했을 때 docs/drey/ 의 단계별 업무 문서(backlog·planning·worklist·review·done)와 p | 자체 작성 |
| workspace-setup | 작업 규칙 만들기·이어 정비 | 자체 작성 |

## 쓰는 방법

- **Drey Browser 안에서** — 설치할 것이 없습니다. Drey Browser 는 이 스킬을 앱 안에 담고, 자기가 시작한 세션에만 더합니다(Claude Code 는 세션 플러그인, Codex 는 추가 스킬 폴더). 사용자 전역 Claude Code·Codex 설정은 바꾸지 않습니다.
- **Claude Code 만 쓸 때** — 이 저장소는 Claude Code 플러그인입니다(`.claude-plugin/plugin.json`). 예: `claude --plugin-dir <이 저장소 경로>` 로 세션을 시작하거나, Claude Code 플러그인 안내대로 설치합니다.
- **Codex 등 다른 에이전트** — 쓰려는 `skills/<이름>` 폴더를 그 도구의 스킬 위치에 복사합니다. 위치는 그 도구 안내를 따릅니다.
- **Drey 전용 부분** — 일부 스킬(`update-docs`·`workspace-setup`·`plan-consensus`)은 Drey Browser 의 작업 문서 도구(MCP `work_docs_*`·`work_task_*` 또는 `DreyBrowser.Mcp.exe --drey-docs`)를 먼저 씁니다. Drey 없이도 Markdown 을 직접 고치는 방법을 안내하지만 그 도구는 동작하지 않습니다.
- **훅(`drey-app/hooks.json`)** — Drey Browser 앱 폴더의 `DreyBrowser.Mcp.exe` 를 부르므로 **일반 Claude Code 설치에서는 동작하지 않습니다**. 그래서 플러그인 기본 위치(`hooks/`)가 아니라 `drey-app/` 에 두었습니다. [drey-app/README.md](drey-app/README.md) 참고.

## 정본과 이 저장소

이 저장소는 Drey Browser 저장소의 단일 정본(`browser/src/Browser.App/Assets/claude/drey-plugin`)을 원본 커밋 `ea88256567272d7f882fad0e9051c3f9917c14f5` 기준으로 내보낸 것입니다. 그 커밋으로 만든 Drey Browser 빌드에 같은 파일이 들어갑니다. 고칠 때는 정본에서 고치고 앱과 함께 시험한 뒤 다시 내보냅니다 — 이 사본을 직접 고치지 말고 [DreyBrowserRelease 이슈](https://github.com/TRpop/DreyBrowserRelease/issues)로 알려 주세요. Drey Browser 는 실행 중에 이 저장소에서 스킬을 내려받지 않습니다.

## 라이선스

- Drey 자체 작성 부분: MIT License, Copyright (c) 2026 TRpop — [LICENSE](LICENSE).
- `debugging`·`plan-consensus` 는 [obra/superpowers](https://github.com/obra/superpowers) 의 스킬(systematic-debugging·brainstorming)을 바탕으로 했습니다: MIT License, Copyright (c) 2025 Jesse Vincent — [NOTICE.md](NOTICE.md), 원문 [LICENSES/superpowers-MIT.txt](LICENSES/superpowers-MIT.txt). 두 고지를 함께 유지합니다.
