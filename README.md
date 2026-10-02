# Open Design

Open Design is a local-first design workbench that connects an installed coding-agent CLI or a configured BYOK provider to reusable design skills and design systems. It streams generated artifacts into a preview, then lets the user save them to disk.

> **Status:** Source tree and package scripts inspected. This README does not claim production readiness, model quality, secure isolation, deployment availability, or test results.

The root package describes a local-first design product. Its workspace contains a daemon, web interface, desktop shell, agent adapters, skills, design systems, and build tools. The Quickstart describes prototype artifacts and previews; generated output still needs human review and project-specific validation.

## Components

| Area | Location | Role |
|---|---|---|
| Daemon and CLI | apps/daemon/ | Agent discovery, project/session handling, artifact events, and local services |
| Web interface | apps/web/ | Design workspace and artifact preview |
| Desktop shell | apps/desktop/ | Desktop runtime integration |
| Skills | skills/ | Reusable design and workflow instructions |
| Design systems | design-systems/ | Reusable design-system material |
| Build and tooling | tools/, scripts/ | Workspace development and packaging |

## Requirements

The root package declares Node.js 24.x and pnpm 10.33.2. The Quickstart lists macOS, Linux, and WSL2 as primary paths. Optional installed coding-agent CLIs or BYOK credentials are needed for generation.

## Quick start

From the repository root:

    corepack enable
    pnpm install
    pnpm tools-dev run web

Open the URL printed by the command. To start the daemon, web app, and desktop shell in the background, see [QUICKSTART.md](QUICKSTART.md).

These commands are taken from the checked-in Quickstart; they were not run during this documentation update.

## Data, providers, and safety

- Prompts and project context may be sent to the selected agent CLI or BYOK provider. A local agent CLI does not guarantee local-only inference.
- The app previews generated artifacts. Review code, links, assets, and scripts before use in another project.
- The repository describes a sandboxed preview, but this README is not an isolation or security certification.
- Keep provider credentials and customer design files out of commits, screenshots, test fixtures, and public issues.

## Documentation

- [Documentation index](docs/README.md)
- [Quickstart](QUICKSTART.md)
- [Architecture](docs/architecture.md)
- [Modes](docs/modes.md)
- [Agent adapters](docs/agent-adapters.md)
- [Skills protocol](docs/skills-protocol.md)
- [Contributing](CONTRIBUTING.md)
- [Changelog](CHANGELOG.md)
- [License](LICENSE)

## Validation

The root package defines test, typecheck, build, and end-to-end scripts. No tests, builds, or deployment checks were run for this README update.