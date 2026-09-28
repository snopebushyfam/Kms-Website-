# KMS Website – Go-live-Checkliste

Stand: Übergabe nach Final Polish. Die Seite besteht aus einer Datei (`index.html`), alle Texte und Bilder sind darin enthalten.

## 1. Anfrageformular verbinden (zwingend)

Im Skript steht ganz unten im Abschnitt „Anfrage-Strecke“:

```js
const FORM_CONFIG = { mode: 'none', endpoint: '', timeout: 15000 };
```

- `mode: 'none'` (aktuell): Es wird **nichts** versendet und **kein** Erfolg angezeigt. Besucher sehen einen Hinweis und können ihre Angaben per E-Mail senden oder anrufen.
- `mode: 'netlify'`: Netlify Forms. Im Netlify-Projekt unter *Forms* die Formularerkennung aktivieren und eine E-Mail-Benachrichtigung an kontakt@kms.koeln einrichten. Das Formular heißt `anfrage` und hat einen Spam-Schutz (Honeypot).
- `mode: 'endpoint'`: eigener Dienst (z. B. Formspree, CRM-Webhook). `endpoint` auf die URL setzen; gesendet wird JSON.

Eine Erfolgsmeldung erscheint nur, wenn der Server den Eingang bestätigt (HTTP 2xx). Nach der Umstellung einmal eine Testanfrage senden und den Eingang prüfen.

## 2. Inhalte vom Kunden bestätigen lassen

- Funktionsbezeichnung von Klaus M. Koke (im HTML als TODO markiert, auch im JSON-LD `employee` ergänzen).
- Optional: persönliche Zitate von Serkan Yetim und Klaus M. Koke. Aktuell stehen dort neutrale Sätze, die Vorschläge liegen als Kommentar im Code.
- Adressen: „Leonhardsgasse 4“ (Anschrift) und „Leonhardsgasse 10“ (Büro) prüfen.
- Profil-Headline „Seit 1999. Heute digital. Morgen zukunftsorientiert.“ freigeben.

## 3. Bilder ersetzen

Alle Bilder werden zentral im Objekt `IMG` im Skript zugeordnet (Kommentar „Zentrale Bildzuordnung“).

- Platzhalter von Unsplash: WEG-, Miet- und Sondereigentum-Kapitel, Galerie 01, 03, 05.
- Aus Gestaltungsentwürfen (nur Übergang, geringe Auflösung): Hero, Büro/Empfang, Büro-Logo, Galerie 02 und 04.
- Porträts werden von kms.koeln geladen. Falls der Server Fremdeinbindung blockiert, erscheint ein Monogramm. Besser: Porträts lokal einbinden.

Bildrichtung: echte Kölner Objekte (Altbau, Nachkriegsbau, Neubau, Wohn- und Geschäftshaus), Fassaden- und Treppenhausdetails, echtes Büro bei Tageslicht, Porträts mit natürlichem Licht.

## 4. Technisch vor dem Go-live

- `og-image.jpg` (1200 × 630) unter https://kms.koeln/og-image.jpg bereitstellen.
- Impressum und Datenschutzerklärung prüfen; die Datenschutzerklärung muss den gewählten Formular-Dienst nennen.
- Google Fonts werden extern geladen. Für DSGVO-Sicherheit die Schriften lokal hosten (Montserrat, Newsreader, IBM Plex Mono).
- Canonical und Links zeigen auf https://kms.koeln/ – nur beim endgültigen Domain-Umzug gültig.
