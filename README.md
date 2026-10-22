# 3D Model Anything für das iPad

Build-Projekt für die [Original-App von Wes Bos](https://github.com/wesbos/3d-model-anything/tree/main/apps/house-capture).
GitHub Actions baut eine unsignierte IPA auf einem macOS-Standard-Runner.
AltStore Classic signiert und installiert die App anschließend über einen Windows-PC.

**[Installationsanleitung öffnen](INSTALLATION.md)** · **[Builds und Downloads](https://github.com/psydemekum/house-capture-ipad/actions/workflows/build-ipad.yml)**

Scannen benötigt ein iPad mit LiDAR und mindestens iPadOS 17, beispielsweise das
iPad Pro 12,9″ von 2020. Mit einem kostenlosen Apple-Konto muss AltStore die
Signatur alle sieben Tage erneuern.

Der Workflow startet manuell und baut den festgelegten Original-Commit
`31b2dc9da3fb541e501f2f0936e55b32afb70ee8`. Ein transparenter
[Build-Patch](patches/swift-type-inference.patch) ergänzt explizite Tupeltypen für
den Swift-Compiler des Runners. Die Berechnungen bleiben gleich.

Ein erfolgreicher Build bestätigt die Kompilierung und Paketprüfungen.
Installation, LiDAR-Scanning und Export müssen auf dem echten iPad geprüft werden.
Persönliche Scans und Apple-Zugangsdaten gehören nicht in dieses Repository.

Heruntergeladene Build-Dateien liegen lokal unter `downloads/` und werden von Git ignoriert.
