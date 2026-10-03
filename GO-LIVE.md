# KMS Website – Go-live-Checkliste

Stand: Übergabe nach Final Polish. Die Seite besteht aus einer Datei (`index.html`), alle Texte und Bilder sind darin enthalten.

## 1. Anfrageformular verbinden (zwingend, Netlify Forms empfohlen)

Die Seite läuft auf Netlify, deshalb ist Netlify Forms der einfachste Weg: kein externer Dienst, kein API-Key. Das Formular ist dafür vorbereitet (`name="anfrage"`, `data-netlify="true"`, Honeypot `bot-field`, verstecktes Feld `form-name`).

1. **HTML:** In `index.html` im Skriptabschnitt „Anfrage-Strecke“ ändern:
   `mode ist auf 'netlify' gestellt (erledigt).
2. **Netlify-Dashboard:** Projekt → *Forms* → „Enable form detection“ aktivieren. Danach **einmal neu deployen**, erst dann wird das Formular `anfrage` erkannt und erscheint unter *Forms*.
3. **Benachrichtigung:** Projekt → *Forms* → *Form notifications* → „Add notification“ → *Email notification* → Formular `anfrage` → E-Mail `info@kms.koeln`.
4. **Echter Test:** Auf der veröffentlichten Seite eine Anfrage absenden. Prüfen: (a) Erfolgsmeldung erscheint, (b) Eintrag unter *Forms → anfrage → Submissions*, (c) E-Mail kommt bei info@kms.koeln an (auch Spam-Ordner).

Bis dieser Test erfolgreich war, gilt der Versand **nicht** als produktionsbereit. Im Modus `none` wird nichts versendet und kein Erfolg angezeigt; Besucher erhalten den E-Mail-/Telefon-Hinweis.

Alternative `mode: 'endpoint'` (Formspree, CRM-Webhook): `endpoint` setzen, gesendet wird JSON.

## 2. Kundendaten noch offen

- Funktionsbezeichnung Klaus M. Koke (bis dahin neutral „KMS Immobilienverwaltung“).
- Optionales Statement Serkan Yetim (Vorschlag nur als HTML-Kommentar, nicht sichtbar).
- Optionales Statement Klaus M. Koke (Vorschlag nur als HTML-Kommentar, nicht sichtbar).
- Finale Teamfotos bestätigen.
- Abteilungs-E-Mails (vom Kunden per Entwurf geliefert): info@, kontakt@, service@, payment@kms.koeln.
- Logo: hochauflösende Version eingebaut (freigestellt aus JPG). Ideal wäre zusätzlich eine SVG-Datei.

## 2b. Weitere Inhalte bestätigen

- Funktionsbezeichnung von Klaus M. Koke (im HTML als TODO markiert, auch im JSON-LD `employee` ergänzen).
- Optional: persönliche Zitate von Serkan Yetim und Klaus M. Koke. Aktuell stehen dort neutrale Sätze, die Vorschläge liegen als Kommentar im Code.
- Adressen: „Leonhardsgasse 4“ (Anschrift) und „Leonhardsgasse 10“ (Büro) prüfen.
- Profil-Headline „Seit 1999. Heute digital. Morgen zukunftsorientiert.“ freigeben.

## 3. Bilder ersetzen (im Code als „TODO FINAL ASSET“ markiert)

Alle Bilder werden zentral im Objekt `IMG` im Skript zugeordnet (Kommentar „Zentrale Bildzuordnung“).

- Platzhalter von Unsplash: WEG-, Miet- und Sondereigentum-Kapitel, Galerie 01, 03, 05.
- Aus Gestaltungsentwürfen (nur Übergang, geringe Auflösung): Hero, Büro/Empfang, Büro-Logo, Galerie 02 und 04.
- Porträts werden von kms.koeln geladen. Falls der Server Fremdeinbindung blockiert, erscheint ein Monogramm. Besser: Porträts lokal einbinden.

Bildrichtung: echte Kölner Objekte (Altbau, Nachkriegsbau, Neubau, Wohn- und Geschäftshaus), Fassaden- und Treppenhausdetails, echtes Büro bei Tageslicht, Porträts mit natürlichem Licht.

## 4. Technisch vor dem Go-live

- **Pflicht:** Finales OG-Bild in 1200 × 630 erstellen und unter https://kms.koeln/og-image.jpg bereitstellen (die im Meta-Tag verwendete URL). Offen, bis die Datei dort tatsächlich abrufbar ist.
- Impressum und Datenschutzerklärung prüfen; die Datenschutzerklärung muss den gewählten Formular-Dienst nennen.
- Google Fonts werden extern geladen. Für DSGVO-Sicherheit die Schriften lokal hosten (Montserrat, Newsreader, IBM Plex Mono).
- Canonical und Links zeigen auf https://kms.koeln/ – nur beim endgültigen Domain-Umzug gültig.
