# fairkaufswerkstatt.de

Website der FAIRkaufswerkstatt GmbH – eine einzige, in sich geschlossene HTML-Datei.
Alle Styles, Skripte und Bilder sind eingebettet (Bilder als Base64-Data-URI),
es gibt keinen Build-Schritt und keine Abhängigkeiten. Extern geladen werden
lediglich die Google Fonts.

Gehostet über **GitHub Pages**, Domain: <https://www.fairkaufswerkstatt.de>

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette Website inkl. Impressum, Datenschutz und AGB (als Overlay) |
| `404.html` | Fehlerseite im gleichen Design |
| `CNAME` | Custom Domain für GitHub Pages (`www.fairkaufswerkstatt.de`) |
| `.nojekyll` | Verhindert die Jekyll-Verarbeitung durch GitHub Pages |
| `favicon.png` | Browser-Tab-Icon (32×32) |
| `apple-touch-icon.png` | Homescreen-Icon iOS (180×180) |
| `og-image.jpg` | Vorschaubild beim Teilen (1200×630) |
| `robots.txt` | Erlaubt das Indexieren, verweist auf die Sitemap |
| `sitemap.xml` | Seitenverzeichnis für Google |

## Veröffentlichen

1. Repository anlegen und alle Dateien in den Wurzelordner des Branches legen
   (kein Unterordner – sonst werden Favicon und OG-Bild nicht gefunden).
2. **Settings → Pages → Source:** „Deploy from a branch", Branch `main`, Ordner `/ (root)`.
3. **Settings → Pages → Custom domain:** `www.fairkaufswerkstatt.de` eintragen
   (die `CNAME`-Datei setzt das bereits, GitHub übernimmt sie automatisch).
4. **„Enforce HTTPS"** aktivieren, sobald das Zertifikat ausgestellt ist
   (dauert nach der DNS-Umstellung meist wenige Minuten bis eine Stunde).

### DNS beim Domain-Anbieter (aktuell IONOS)

| Typ | Name | Wert |
|---|---|---|
| CNAME | `www` | `<github-benutzername>.github.io` |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

Die vier A-Records sorgen dafür, dass auch `fairkaufswerkstatt.de` ohne `www`
auf die Seite weiterleitet.

## Änderungen

`index.html` ist zwar eine einzige Datei, aber gut sortiert: erst `<head>` mit
Meta-Angaben, dann das CSS, dann der Seiteninhalt, am Ende die Rechtstexte und
das JavaScript. Für kleine Textänderungen genügt Suchen & Ersetzen direkt im
GitHub-Editor; nach dem Commit ist die Seite in ein bis zwei Minuten live.

Häufig gesuchte Stellen:

- **Kontaktformular** – `formspree.io/f/` (aktuell die ID `xrpgkvao`, gemeinsam
  mit fairkaufsboost.de genutzt; jede Anfrage enthält das Feld
  `quelle: fairkaufswerkstatt.de`)
- **Terminbuchung** – `calendar.app.google`
- **Anzahl Google-Bewertungen** – `18 Google-Bewertungen` (fest hinterlegt)
- **Provisionssatz im Rechner** – `3,57`

## Vor dem Livegang prüfen

- **Rechtstexte:** Impressum, Datenschutz und AGB wurden aus der
  Fairkaufsboost-Seite übernommen und angepasst. Der Hosting-Abschnitt der
  Datenschutzerklärung nennt **GitHub Pages** – das passt zu diesem Repository.
  Wenn die Seite doch bei IONOS bleibt, muss dieser Abschnitt zurück auf IONOS
  geändert werden. Alle Texte sind ohne anwaltliche Prüfung entstanden.
- **Formspree:** eigene Formular-ID anlegen, falls die Anfragen getrennt
  eingehen sollen.
- **Alte Seite:** Erst umstellen, wenn die neue Seite unter der GitHub-Pages-URL
  wie gewünscht aussieht.
