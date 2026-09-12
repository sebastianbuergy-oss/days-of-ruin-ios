# Days of Ruin (iOS)

Fan-App für die Berner Metalcore-Band Days of Ruin: nächste Shows, alle bisherigen
Konzerte, Releases mit Bandcamp-Player, Band, Fotos, Shop, Links.

- UIKit-Hülle mit `WKWebView`, die Web-App liegt gebündelt in `web/`.
- Xcode-Projekt wird mit XcodeGen aus `project.yml` erzeugt.
- Build: Codemagic Workflow `ios-testflight` (App-Store-Signierung, Upload nach TestFlight).
- Bundle-ID `com.sebastianbuergy.daysofruin`, iPhone, iOS 16+, nur Hochformat.
- Externe Links (Bandcamp, Spotify, Tickets, Mail) öffnen in Safari bzw. der jeweiligen App.

## Selbst-Aktualisierung

Die App lädt beim Start und bei jeder Rückkehr `feed/feed.json` von diesem Repo
(raw.githubusercontent.com) und zusätzlich die öffentliche Bandsintown-API der Band.
Der Feed enthält kommende Shows und Neuigkeiten und wird von einem täglichen Job
gepflegt (Bandsintown, daysofruin.ch, Bandcamp, YouTube, Instagram, Facebook).
Ohne Netz zeigt die App den gebündelten Stand.

Prüfen: `npm run check`
