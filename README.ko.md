# Open Design

Open Design은 로컬 우선 디자인 워크벤치입니다. 설치된 코딩 에이전트 CLI 또는 설정된 BYOK 제공자를 재사용 가능한 Skill과 Design System에 연결합니다. 생성된 산출물은 미리보기에서 확인하고 저장할 수 있습니다.

> **상태:** 소스 구조와 패키지 스크립트를 확인했습니다. 이번 README 업데이트에서는 설치, 테스트, 외부 제공자, 배포, 보안, 출력 품질을 검증하지 않았습니다.

## 구성

- apps/daemon/: 로컬 서비스와 CLI
- apps/web/: 디자인 작업 공간과 미리보기
- apps/desktop/: 데스크톱 셸
- skills/ 및 design-systems/: 재사용 가능한 작업 지침과 디자인 자료

## 요구 사항 및 시작

루트 패키지는 Node.js 24.x와 pnpm 10.33.2를 지정합니다. Quickstart는 macOS, Linux, WSL2를 주요 환경으로 안내합니다.

    corepack enable
    pnpm install
    pnpm tools-dev run web

이 명령은 저장소 Quickstart를 따른 것이며 이번 업데이트에서 실행하지 않았습니다. 데스크톱 시작 및 추가 단계는 [영문 Quickstart](QUICKSTART.md)를 확인하세요.

## 데이터와 한계

입력과 프로젝트 맥락은 선택한 에이전트 CLI 또는 BYOK 제공자로 전송될 수 있습니다. 로컬 CLI를 사용해도 추론이 기기 안에서만 실행된다는 뜻은 아닙니다. 생성된 산출물을 재사용하기 전에 검토하세요. 이 README는 보안이나 격리 인증을 의미하지 않습니다.

- [문서 색인](docs/README.md)
- [아키텍처](docs/architecture.md)
- [기여 안내](CONTRIBUTING.md)
- [라이선스](LICENSE)