# KD-Service

Eine responsive Vue-Website mit umschaltbaren Bereichen für Eventverleih sowie
CAD-Konstruktion und 3D-Druck.

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

Die Kontaktlinks für Eventservice und CAD/3D-Druck sind separat in `src/App.vue`
hinterlegt.