# KD-Eventservice

Eine responsive, einseitige Vue-Website für den Eventverleih in Ankum.

## Lokal starten

```sh
npm install
npm run dev
```

## Produktion bauen

```sh
npm run build
npm run preview
```

Der Build liegt im Ordner `dist`. Die Vite-Basis ist auf `/Website-Test/` gesetzt,
damit Website und Produktbilder unter GitHub Pages korrekt geladen werden.

## GitHub Pages veröffentlichen

Der Workflow unter `.github/workflows/deploy.yml` baut und veröffentlicht bei
jedem Push auf `main`. In den Repository-Einstellungen unter **Pages** muss als
Build-Quelle **GitHub Actions** ausgewählt sein.

Vor dem Veröffentlichen in `src/App.vue` die `contactUrl` auf das eigene
Kleinanzeigen-Profil oder eine konkrete Anzeige ändern. Aktuell führt der Link
zur Kleinanzeigen-Startseite.