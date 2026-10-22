# 3D Model Anything auf dem iPad installieren

Zielgerät: iPad Pro 12,9″, 4. Generation (2020), mit aktuellem iPadOS.
Dieses Modell besitzt LiDAR. Die Original-App unterstützt iOS/iPadOS ab Version 17.

## Stand

Das öffentliche Repository [psydemekum/house-capture-ipad](https://github.com/psydemekum/house-capture-ipad)
ist eingerichtet. Der [Release-Build vom 22. Oktober 2026](https://github.com/psydemekum/house-capture-ipad/actions/runs/39799098288)
ist erfolgreich und stellt eine unsignierte IPA bereit. Der Download wurde zusätzlich
unter Windows geprüft: ZIP-Integrität, SHA-256-Prüfsumme, ARM64-Gerätecode,
iPad-Unterstützung und Kameraberechtigungstext sind bestätigt.

Die IPA ist 5.033.066 Bytes groß und unterstützt iPadOS ab 17.0. Das GitHub-Artefakt
bleibt drei Tage verfügbar; die lokale Kopie liegt unter `downloads/39799098288/`.
Bei Bedarf den Workflow erneut starten. Installation, LiDAR-Scan und Export auf dem
echten iPad stehen noch aus.

Ein kleiner Build-Patch ergänzt explizite Tupeltypen in `CoverageEngine.swift`.
Das Originalprojekt veröffentlicht den Quellcode; seine Release-Unterlagen bestätigen
keine abgeschlossene TestFlight- oder App-Store-Veröffentlichung.

## App ohne eigenen Mac bauen

1. Das [öffentliche Build-Repository](https://github.com/psydemekum/house-capture-ipad) öffnen.
   Persönliche Scans gehören nicht hinein.
2. Unter **Actions → iPad-App bauen → Run workflow** den Build starten.
3. Nach einem erfolgreichen Lauf das Artefakt **3D-Model-Anything-iPad** herunterladen.
4. Das ZIP entpacken. Es enthält `3D-Model-Anything-unsigned.ipa`, eine SHA-256-Prüfsumme,
   die Original-Lizenz, den Build-Patch und die genaue Quellcode-/Build-Referenz.

Der Workflow lädt den Originalquellcode von `wesbos/3d-model-anything`, festgelegt auf
Commit `31b2dc9da3fb541e501f2f0936e55b32afb70ee8` vom 22. Oktober 2026.
Er ergänzt explizite Tupeltypen für den Swift-Compiler des Runners; die Berechnungen
bleiben gleich. Anschließend baut er die App in **Release** für echte iOS-Geräte und prüft vor dem
Verpacken ARM64, iPad-Unterstützung und den Kameraberechtigungstext.

Verwendet wird der Standard-Runner `macos-26`. GitHub beschreibt Standard-Runner in
öffentlichen Repositories als kostenlos. Der Build startet ausschließlich manuell;
in privaten Repositories wird der Job übersprungen. Apple-Zugangsdaten oder
Signaturzertifikate werden für diesen Build nicht benötigt.

## Mit Windows installieren

1. [AltStore Classic nach der offiziellen Windows-Anleitung einrichten](https://faq.altstore.io/altstore-classic/how-to-install-altstore-windows).
   Dabei die dort angegebenen Apple-Versionen von iTunes und iCloud beachten.
2. Das entsperrte iPad per USB mit dem PC verbinden und dem Computer vertrauen.
3. AltServer starten und über sein Taskleistensymbol **Install AltStore** für das iPad wählen.
   Das Apple-Konto direkt in AltServer eingeben.
4. Auf dem iPad dem Entwicklerprofil unter **Einstellungen → Allgemein → VPN und
   Geräteverwaltung** vertrauen. Den **Entwicklermodus** unter **Datenschutz & Sicherheit**
   aktivieren und den verlangten Neustart bestätigen.
5. Die entpackte IPA auf das iPad übertragen, beispielsweise über iCloud Drive oder
   einen anderen bereits eingerichteten Dateitransfer.
6. In AltStore **My Apps → +** öffnen, die IPA auswählen und installieren.
   AltServer auf dem PC muss dabei erreichbar sein, über USB oder im selben WLAN.
7. **3D Model Anything** öffnen, den Kamerazugriff erlauben und einen kleinen Raum scannen.
   Den Raum speichern, erneut öffnen und den Export über die Teilen-Funktion prüfen.

Mit einem kostenlosen Apple-Konto laufen die Signaturen nach **sieben Tagen** ab.
AltStore kann sie erneuern, solange AltServer erreichbar ist. Regelmäßig **Refresh All**
kontrollieren. Vor einer Neuinstallation vorhandene Scans exportieren und sichern.

## Quellen

- [Original-App und Voraussetzungen](https://github.com/wesbos/3d-model-anything/blob/main/apps/house-capture/README.md)
- [Veröffentlichungsstand](https://github.com/wesbos/3d-model-anything/blob/main/docs/release-status.md)
- [Apple: iPad Pro 12,9″, 4. Generation](https://support.apple.com/de-de/111977)
- [GitHub Actions: Abrechnung](https://docs.github.com/en/billing/concepts/product-billing/github-actions)
- [AltStore Classic: Windows-Installation](https://faq.altstore.io/altstore-classic/how-to-install-altstore-windows)
- [AltStore: Signatur erneuern](https://faq.altstore.io/altstore-classic/your-altstore)
