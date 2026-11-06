# Drey app hook / Drey 앱 전용 훅

**English** — `hooks.json` is the hook Drey Browser uses when it opens a Claude Code session. It runs `DreyBrowser.Mcp.exe --claude-hook` from the app folder (read-only: summarizes and checks the work documents).

- It does not work in a plain Claude Code install, because `DreyBrowser.Mcp.exe` is not there. That is why it is not in the plug-in's default hook folder (`hooks/`).
- Drey Browser uses the same file from its own installation (the source). Do not copy this copy into your global settings.

**한국어** — `hooks.json` 은 Drey Browser 가 Claude Code 탭을 열 때 함께 쓰는 훅이다. 앱 폴더의 `DreyBrowser.Mcp.exe --claude-hook`(읽기 전용: 작업 문서 요약·검사)을 부른다.

- 일반 Claude Code 설치에서는 `DreyBrowser.Mcp.exe` 가 없어 동작하지 않는다. 그래서 플러그인 기본 훅 위치(`hooks/`)에 두지 않았다.
- Drey Browser 는 본체 설치 파일 안의 같은 내용(정본)을 쓴다. 이 사본을 사용자 전역 설정에 직접 넣지 않는다.
