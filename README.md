# sunnestube.ch – Website

Statische Website, keine Abhängigkeiten, kein Build. Hosting: Netlify. Domain: hosttech.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Startseite (Onepager) |
| `impressum.html` | Impressum & Datenschutz |
| `danke.html` | Bestätigung nach Formular |
| `style.css` | Design |
| `script.js` | Interaktionen: Scroll-Animationen, Schnee, Lightbox, Mobile-Menü |
| `_redirects` | Alte Wix-URLs → neue Seite, www erzwingen |
| `favicon.svg` | Browser-Icon |
| `images/` | Fotos (siehe unten) |
| `merkblatt.html` | Merkblatt für Gäste (Anreise, Schlüssel, WLAN, Ausstattung) |

## Fotos

Alle Fotos liegen web-optimiert (max. 2000 px, JPG) in `images/` und sind eingebaut:
Hero `hero.jpg` (Belalp über dem Nebelmeer), `blatten-nacht.jpg` (Region), Galerie (Esszimmer, Terrasse, Schlafzimmer, Küche, Bad, Zimmer), `grundriss.png`,
`residence-panorama.jpg`, `familie.jpg`.
Nicht verwendet, aber vorhanden: `blatten-winter.jpg`, `bad-wanne.jpg`, `schlafzimmer-detail.jpg`, `essbereich-detail.jpg`, `esszimmer-fenster.jpg`, `garderobe.jpg`.

Foto tauschen: Datei in `images/` ersetzen oder in `index.html` den `src` anpassen. `og:image` im `<head>` zeigt auf `images/hero.jpg` (Vorschaubild bei WhatsApp/Social).

## Deployment auf Netlify

1. netlify.com → Konto erstellen (kostenlos).
2. «Add new site → Deploy manually» und diesen Ordner per Drag & Drop hochladen
   (oder: Ordner in ein GitHub-Repo, dann «Import from Git» – Build command leer, Publish directory `/`).
3. Site settings → Forms: Form «kontakt» erscheint nach dem ersten Deploy automatisch. Unter
   Forms → Notifications eine E-Mail-Benachrichtigung an officemoser@bluewin.ch einrichten.
4. Domain management → Add custom domain → `www.sunnestube.ch` und `sunnestube.ch`.
   Netlify zeigt die nötigen DNS-Einträge an.

## DNS bei hosttech

Im hosttech-Kundencenter unter DNS der Domain sunnestube.ch:

| Typ | Name | Wert |
|---|---|---|
| CNAME | www | `<dein-site-name>.netlify.app` |
| A | @ | `75.2.60.5` (Netlify Load Balancer, aktuellen Wert in Netlify prüfen) |

Die bisherigen Wix-Einträge (A-Records auf Wix-IPs, CNAME www → wix) löschen.
SSL stellt Netlify nach der DNS-Umstellung automatisch aus (Let's Encrypt), dauert meist unter einer Stunde.

## Vor dem Livegang


- [ ] Fakten Winter/Sommer mit belalp.ch abgleichen (Saisondaten, Hexenabfahrt-Datum)
- [ ] Formular einmal testen (Netlify → Forms)
- [ ] Nach DNS-Umstellung: Wix-Abo kündigen

## Später pflegen

Texte direkt in `index.html` ändern, Ordner erneut auf Netlify ziehen (oder Git-Push). Fertig.
