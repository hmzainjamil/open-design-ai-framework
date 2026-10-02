# Open Design

Open Design ist eine lokale Design-Workbench. Sie verbindet eine installierte Coding-Agent-CLI oder einen konfigurierten BYOK-Anbieter mit wiederverwendbaren Skills und Design-Systemen. Erzeugte Artefakte werden in einer Vorschau angezeigt und können gespeichert werden.

> **Status:** Quellstruktur und Paket-Skripte geprüft. Installation, Tests, Anbieter, Bereitstellung, Sicherheit und Ausgabequalität wurden bei dieser README-Aktualisierung nicht validiert.

## Komponenten

- apps/daemon/: lokaler Dienst und CLI
- apps/web/: Design-Oberfläche und Vorschau
- apps/desktop/: Desktop-Shell
- skills/ und design-systems/: wiederverwendbare Arbeitsabläufe und Designvorgaben

## Anforderungen und Start

Das Hauptpaket verlangt Node.js 24.x und pnpm 10.33.2. macOS, Linux und WSL2 sind laut Quickstart die primären Umgebungen.

    corepack enable
    pnpm install
    pnpm tools-dev run web

Die Befehle stammen aus dem Repository-Quickstart und wurden hier nicht ausgeführt. Für vollständigen Desktop-Start und weitere Optionen siehe [Quickstart auf Deutsch](QUICKSTART.de.md) und [englische Produktdokumentation](README.md).

## Datenschutz und Grenzen

Eingaben und Projektkontext können an die gewählte Agent-CLI oder den BYOK-Anbieter gesendet werden. Eine lokale CLI garantiert keine lokale Inferenz. Prüfe generierte Artefakte vor der Wiederverwendung. Diese README ist keine Sicherheits- oder Isolationszertifizierung.

- [Dokumentationsindex](docs/README.md)
- [Architektur](docs/architecture.md)
- [Mitwirken](CONTRIBUTING.de.md)
- [Lizenz](LICENSE)