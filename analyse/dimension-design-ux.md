# Analyse-Dimension: Design & UX – bbf-gruppe.com

**Stand:** 15.07.2026 · Erstellt für Vertriebstermin (Webdesign-Agentur)

## 0. Methodik-Disclaimer

**Diese Design-Analyse basiert auf Inhaltsstruktur und Code-Indizien, nicht auf visueller Begutachtung (Screenshots).** In dieser Arbeitsumgebung bestand kein Netzwerkzugriff auf bbf-gruppe.com und kein Zugriff auf Screenshot-/Rendering-Werkzeuge (kein Playwright, kein Lighthouse, kein Browser). Alle Aussagen stützen sich ausschließlich auf:

- den gecrawlten HTML/Markdown-Content der Seiten (`daten/crawl/startseite.md`, `leistungen.md`, `leistungen_hochbau.md`),
- Bilddateinamen, Alt-Texte, Linkziele und Layout-Reihenfolge, wie sie im Markdown erkennbar sind,
- technische Webflow-Indizien (CDN-Pfade, Platzhalter-Assets, Markup-Duplikate),
- die Wettbewerber-Recherche `daten/recherche/serp-wettbewerber.md`.

**Es werden keine Aussagen zu Farben, Schriftarten, Bildschirmauflösung, Ladezeiten (gemessen) oder visueller Ästhetik getroffen, die nicht aus dem Quelltext ableitbar sind.** Für eine vollständige UI-Bewertung (visuelle Konsistenz, Typografie, Farbwelt, tatsächliches Ladeverhalten, mobile Darstellung) **wird eine visuelle Prüfung per Browser vor oder im Termin dringend empfohlen** – die hier dokumentierten Befunde sind aber bereits aus dem Code heraus so konkret, dass sie im Termin unabhängig davon überzeugend gezeigt werden können (siehe Abschnitt 9).

**Datenlage:** `referenzen.md`, `kontakt.md` und `ueber-uns.md` sind inzwischen verfügbar und wurden eingearbeitet. `technical-head-analyse.md` (Webflow-Diagnose zu Ladeverhalten/Font-Loading) lag zum Erstellungszeitpunkt weiterhin **nicht vor** (paralleler Agent nicht fertig) – wo diese Quelle relevant gewesen wäre, ist das explizit als Lücke markiert.

---

## 1. Informationsarchitektur

**Navigationsstruktur (aus `leistungen.md` und `startseite.md`):**

Die Hauptleistungen werden sitewide als 9 Kategorien geführt: Projektentwicklung, Tiefbau, Hochbau, Elektrotechnik/Gebäudetechnik Elektro, Gebäudetechnik HLS, Garten- und Landschaftsbau, Gerüstbau, Planung, Vermessung. Auf der `/leistungen`-Übersichtsseite werden diese als Anker-Navigation (`#tiefbau`, `#hochbau` usw.) auf einer einzigen langen Seite dargestellt.

**Ungleiche Seitentiefe – das zentrale IA-Problem:**

| Leistung | Ziel von „Mehr erfahren“ | Seitentyp |
|---|---|---|
| Tiefbau | `/leistungen/tiefbau` | eigene interne Unterseite (USPs, FAQ, Referenzen) |
| Hochbau | `/leistungen/hochbau` | eigene interne Unterseite (USPs, FAQ, 20+ Referenzen) |
| Elektrotechnik | `/leistungen/gebaeudetechnik-elektro` | eigene interne Unterseite |
| Gebäudetechnik (HLS) | `/leistungen/gebaeudetechnik-hls` | eigene interne Unterseite |
| Garten- und Landschaftsbau | `/leistungen/garten-und-landschaftsbau` | eigene interne Unterseite |
| Projektentwicklung | `/bbf-projekt` | separate interne Seite (anderer URL-Zweig) |
| Gerüstbau | `/leistungen/geruestbau` (laut `leistungen.md`) bzw. laut Startseite **keine eigene Seite** | Widerspruch zwischen den beiden Crawl-Quellen |
| Planung | **`https://www.plant-plant.de/`** | **externe Fremddomain** |
| Vermessung | **`https://www.plan3d-berlin.de/`** | **externe Fremddomain** |

Zwei von neun „Mehr erfahren“-Klicks auf der zentralen Leistungsseite führen den Besucher **komplett von bbf-gruppe.com weg** auf die Websites zugekaufter Tochterfirmen (Beleg: `daten/crawl/leistungen.md` Zeilen 72–96). Das widerspricht dem zentralen Markenversprechen der Startseite „Alles aus einer Hand“ und reißt den Conversion-Pfad ab – auf den Fremddomains gibt es keinen erkennbaren Rückweg zum BBF-Kontaktformular.

**Zielführung zur Kontaktaufnahme:** Der CTA „Jetzt kontaktieren“/„Kontakt aufnehmen“ ist omnipräsent (5× allein auf der Startseite, zusätzlich auf jeder Leistungsunterseite im Hero und nach dem FAQ-Block). Das ist grundsätzlich conversion-freundlich, bleibt aber undifferenziert: dieselbe CTA-Formulierung für Erstkontakt, Informationssuche und Angebotsanfrage, ohne Rücksicht auf die selbst genannten Zielgruppen (privat/gewerblich/öffentlich). Zusätzlich ist der CTA „Zu unserer Leistungsübersicht“ auf der Startseite fehlerhaft verlinkt und führt auf `/kontakt` statt auf `/leistungen` (Beleg: `startseite.md` Zeile 79) – ein Nutzer, der sich noch informieren will, landet ungewollt im Kontaktformular.

**Das Kontaktformular selbst (`kontakt.md`) ist positiv hervorzuheben:** Es bietet eine granulare Themen-Zuordnung („Auf welchen Bereich bezieht sich Ihre Nachricht?“ mit 11 Optionen, darunter auch „Verkauf & Vermietung“ und „Ankauf“ – feiner differenziert als die 9 Leistungskategorien) sowie ein Attributionsfeld „Wie sind Sie auf uns aufmerksam geworden?“. Das ist funktional durchdachtes Lead-Routing und ein Beleg dafür, dass an anderer Stelle der Seite durchaus sorgfältig gearbeitet wurde – die Qualitätsprobleme sind also ungleich verteilt, nicht flächendeckend.

**Vergleich zu Wettbewerbern (aus `serp-wettbewerber.md`):** BATEG pflegt eine „saubere thematische Seitenarchitektur“ (Leistungen/Referenzen/Über uns/Karriere) inklusive einer eigenen Ansprechpartner-Seite und nach Kategorien strukturierten Referenzen. E.L.I.A. hat für jede Kernleistung eine eigene, keyword-sauber betitelte Landingpage. Z-Geschossbau geht noch weiter mit Leistung×Region-Kombinationsseiten. BBF Gruppe hat zwar mehr Substanz (350 MA, 8 Standorte, deutlich mehr Referenzprojekte als alle genannten Wettbewerber), bildet das aber nicht in einer durchgängig konsistenten Seitenarchitektur ab – fünf Leistungen bekommen die „volle“ Behandlung (USP-Sektion, FAQ, Referenzen), vier bekommen nur einen Kurzabschnitt oder verweisen extern.

---

## 2. Content-Qualität & Sorgfalt

Aus `startseite.md` und bestätigt durch `leistungen_hochbau.md` lassen sich konkrete, leicht nachprüfbare Qualitätsmängel belegen:

**Tippfehler in Firmen- und Referenzdaten – auf zwei unabhängigen Seiten bestätigt:**
- „Chausseestaße“ statt „Chausseestraße“ (Adresse BBF Tiefbau GmbH, Bersteland) – identisch auf Startseite **und** `/kontakt` (`kontakt.md` Z. 124)
- „Sanssousi“ statt „Sanssouci“ – ausgerechnet beim Prestige-Referenzprojekt Schloss Sanssouci (UNESCO-Welterbe). Bestätigt auf der Startseite **und** als eigener Referenz-Seitentitel „3D-Vermessung Schloss Sanssousi, Potsdam“ auf `/referenzen` (`referenzen.md` Z. 946–948) – bemerkenswert: die zugehörige Bilddatei heißt korrekt „Schloss Sanssouci 2.png“, nur der von Menschen eingetippte Titeltext ist falsch
- „Oranieburg“ statt „Oranienburg“ – ebenfalls auf zwei Seiten bestätigt: Startseite **und** Referenzkarte „Alter Flugplatz, Oranieburg“ (`referenzen.md` Z. 328–330), auch hier mit korrekt geschriebenem Bilddateinamen „Oranienburg, Alter Flugplatz.png“ im Hintergrund
- „Gerneral-Barby“ (vermutlich „General-Barby“) in einer weiteren Referenzangabe
- URL-Slug-Tippfehler: `/referenzen/katholische-kirchengemeinde-sank-matthias-berlin` – „sank“ statt „sankt“ (`referenzen.md`, letzte Referenzkarte)

**Doppelte/redundante Inhalte:**
- Die Referenzkarte „MITTENWALDE (HOCHBAU)“ (Grundstück 4.984 m², Nutzfläche 966 m²) erscheint laut Startseiten-Slider 3× identisch – und ist auf `/leistungen/hochbau` **direkt zweimal hintereinander** mit demselben Bild (`DJI_0021 1.webp`) und denselben Werten bestätigt (Zeilen 113–136 der Datei). Kein Einzelfall, sondern auf zwei Seiten reproduzierbar.
- Auffällig: Der exakte Grundstückswert „4.984 m²“ taucht auf `/leistungen/hochbau` bei **drei völlig unterschiedlichen Projekten** auf – Mittenwalde (Hochbau), „Beamten-Wohnungs-Verein zu Berlin e.G.“ und „Katholische Kirchengemeinde Sankt Matthias Berlin“ (Zeilen 117–119, 345–347, 359–361). Das ist mit an Sicherheit grenzender Wahrscheinlichkeit kopiertes Platzhalter-Datenmaterial, das nie durch echte, projektspezifische Werte ersetzt wurde.
- Die Leistungs-Sektion („Planen, bauen und betreuen“) erscheint laut Analysehinweis in `startseite.md` zweifach im Markup (Desktop-/Mobil-Variante) – ein technisches Indiz für eine nicht sauber responsive umgesetzte Sektion.

**Leere Datenfelder:** Auf `/leistungen/hochbau` fehlt bei rund der Hälfte der ca. 20 gelisteten Referenzprojekte entweder der Wert für „Grundstück:“ oder „Nutzfläche:“ (u. a. Gesundheitszentrum Schwante, Ferienhaus Mönblick Dranske, Wohnhäuser Borkwalde, Stadthäuser Zeuthener Winkel, Dianastraße Potsdam, mehrere Sanierungsprojekte). Auf der Startseite wird dasselbe Muster für ~70 Referenzkarten sitewide bestätigt.

**Tote/falsche Links – jetzt mit exakten Ziel-URLs bestätigt (`kontakt.md`):**
- Maps-Link „Wegbeschreibung“ von BBF Elektrotechnik GmbH ist wörtlich `(#)` – toter Anker, führt nirgendwohin (`kontakt.md` Z. 236–240)
- Maps-Link von BBF Spree Gerüstbau GmbH (Lehe Weg 2, Luckau) führt zu den exakt gleichen Koordinaten wie BBF Hochbau GmbH – „Nottestraße 2, 15749 Mittenwalde“ (`kontakt.md` Z. 254–258) – falscher Standort, ca. 90 km vom echten Ziel entfernt
- Maps-Links von BBF Herold Ingenieurgesellschaft GaLaBau (Soldiner Str. 53, Berlin) und JoMi Gartenbau (ebenfalls Soldiner Str. 53, Berlin) führen beide zu den identischen Koordinaten wie „Eichenstraße 1, 15537 Grünheide“ (`kontakt.md` Z. 164–168, 181–185) – copy-paste-typischer Fehler, gleicher falscher Link zweimal vergeben
- E-Mail-Link von „plant Hey Dahlke Meurer Planungsgesellschaft mbH“ enthält ein unsichtbares Steuerzeichen direkt im `mailto:`-Href (`kontakt.md` Z. 228: `Kontakt@plant-plant.de﻿`) – der Link ist damit potenziell technisch defekt

**Markenfragmentierung:** Mehrere Tochtergesellschaften nutzen Fremddomain-E-Mail-Adressen statt `@bbf-gruppe.com` (`info@heroldgalabau.de`, `jomi@gartenbau-in-berlin.de`, `Info@plan3d-berlin.de`, `Kontakt@plant-plant.de`, `info@spreegeruestbau.de`) – ein Widerspruch zum zentralen Markenversprechen „Ganzheitliche Lösungen … alles aus einer Hand“.

**Personendaten-Inkonsistenz – durch `kontakt.md` weiter erhärtet:**
- Raúl Comesaña M. wird als Ansprechpartner für 5 verschiedene Gesellschaften geführt (BBF Bau, JoMi Gartenbau, BBF Elektrotechnik, BBF Spree Gerüstbau, sowie laut Startseite auch BBF Gebäudetechnik), dabei aber mit **mindestens 2 unterschiedlichen Bilddateien** dargestellt: ein Foto für BBF Bau GmbH (`68ac0f853c5a60549d63cae6_Raul...webp`), ein zweites, identisches Foto wiederverwendet für JoMi Gartenbau, BBF Elektrotechnik **und** BBF Spree Gerüstbau (`689b499d1a612b0ecb17ead7...webp`) – austauschbar über drei Firmen hinweg statt individuell gepflegt.
- **Widerspruch zwischen Startseite und Kontaktseite:** Die Startseite nennt Raúl Comesaña M. als Ansprechpartner für „BBF Gebäudetechnik GmbH“, die Kontaktseite nennt für dieselbe Gesellschaft „Benjamin Thom“ als Geschäftsführer (`kontakt.md` Z. 104–118) – zwei verschiedene Namen für denselben Ansprechpartner-Slot, je nachdem, welche Seite man besucht.
- **Name/Foto-Mismatch bei Gebr. Pfeil GmbH:** Die Kontaktseite zeigt für „Gebr. Pfeil Garten- und Landschaftsbau GmbH“ den Namen „Enrico Pollnick“ (identisch mit dem direkt darüber gelisteten BBF-Tiefbau-Ansprechpartner), verwendet dafür aber die Bilddatei „Mark Ahner.jpg“ (`kontakt.md` Z. 151–155) – die Startseite wiederum nennt für Pfeil GmbH korrekt „Mark Ahner“. Klassischer Copy-Paste-Fehler: Name der vorherigen Zeile nicht ausgetauscht.

**Systematischer Befund auf `/referenzen` (alle 81 Referenzkarten geprüft):**
- **Ausnahmslos alle 81 Referenzkarten** haben ein Bild ohne Alt-Text (`![](...)`) **und** einen Projekt-Link ohne sichtbaren Linktext (`[](/referenzen/...)`) – kein Einzelfall, sondern ein durchgängiges Muster über die komplette Referenzseite.
- Auf **158 Zeilen** erscheinen rohe GPS-Koordinaten (z. B. `52.53958463322082` / `13.48193231141988`) als **sichtbarer Klartext mitten in jeder Referenzkarte**, ohne Beschriftung oder erkennbaren Nutzen für den Besucher – ein technischer Konfigurationsfehler, bei dem ein für eine Kartenintegration gedachtes Datenfeld ungefiltert im sichtbaren Seiteninhalt landet, statt nur eine Karte zu positionieren.
- Die Grundstücks-/Nutzflächenangaben unterscheiden sich zwischen Seiten für dasselbe Projekt: „Katholische Kirchengemeinde Sankt Matthias Berlin“ zeigt auf `/leistungen/hochbau` „Grundstück: 4.984 m² / Nutzfläche: 966 m²“, auf `/referenzen` dagegen gar keine Flächenangabe, nur Kategorie-Tags – dieselbe Referenz wird je nach Seite unterschiedlich präsentiert.

Diese Befunde sind in ihrer Summe deutlich mehr als „Kleinigkeiten“: Sie betreffen ausgerechnet die Inhalte, die im Vertriebsprozess Vertrauen aufbauen sollen (Referenzen, Standortdaten, Ansprechpartner) und sind alle direkt auf der Seite nachprüfbar, teils sogar auf zwei unabhängigen Seiten identisch reproduzierbar.

**Positiver Gegenbeleg – die Seite `/ueber-uns` zeigt, dass BBF es besser kann:** Die Unternehmensseite (`ueber-uns.md`) ist inhaltlich sorgfältig gepflegt: ein korrektes Hero-Bild mit Alt-Text („Drohnenshot“), eine detaillierte, gut lesbare Historie mit konkreten Jahreszahlen und Akquisitionen (Gründung 1994, Integration Dahmeland Bau 2021, Übernahme JoMi 2025 usw.) sowie eine klar formulierte Philosophie mit sieben Werte-Karten. Das zeigt: Die Qualitätsprobleme sind kein grundsätzliches Kompetenzproblem, sondern ein **Pflege-/QA-Problem, das sich ungleich über die Seiten verteilt** – Startseite und Referenzbereich sind sichtbar schlechter gepflegt als die Über-uns-Seite. Einzige Auffälligkeit dort: In der Meilenstein-Timeline sind zwei Einträge mit Jahr „2025“ beschriftet, deren eigener Beschreibungstext jedoch „im Januar 2026“ nennt (Zusammenschluss mit Plan 3D bzw. plant Hey Dahlke Meurer, `ueber-uns.md` Z. 150–160) – ein kleiner, aber selbst hier vorhandener Datums-Widerspruch.

---

## 3. Bildsprache & Medien

**Positiv:** Die Referenzgalerie auf `/leistungen/hochbau` enthält professionell wirkende Drohnenaufnahmen (Alt-Text „Drohnenshot“, Dateiname `DJI_0021…`), was auf tatsächlich vorhandenes, hochwertiges Bildmaterial hindeutet. Neuere Bild-Uploads tragen sprechende, SEO-taugliche Dateinamen (z. B. „Sanierung Wohn- und Geschäftshaus Zeuthen“, „BBF Bauprojekt ADAC Oberkraemer“, „BBF Neubau Biesdorf“).

**Uneinheitliche Bildqualität/-pflege:** Ältere Uploads tragen generische, nicht sprechende Dateinamen (`DJI_0071.JPG`, `image6.jpg`, `01_edited.jpg`, `03.jpg`, `05.jpg`) – ein Indiz für unterschiedliche Sorgfalt je nach Upload-Zeitpunkt bzw. fehlende einheitliche Asset-Konventionen.

**Kritisches Signal im Hero:** Auf der Startseite ist das erste Bild im Hero-Slider laut Analysehinweis ein **Platzhalter-Asset des Webflow-Basic-Plugins** (`plugins/Basic/assets/placeholder.60f9b1840c.svg`), kein echtes Projekt- oder Firmenfoto. Das ist der allererste visuelle Eindruck, den ein Website-Besucher – etwa ein Investor vor dem heutigen Termin – von der BBF Gruppe bekommt.

**Mobile-/responsive Bildvarianten:** Aus dem vorliegenden Markdown/HTML-Content lässt sich **kein direkter Beleg** für echte responsive Bildauslieferung (z. B. `srcset`/`picture`-Varianten) ableiten – diese Information wäre Teil von `technical-head-analyse.md`, das noch nicht vorlag. Die einzige „Mobil-Variante“, die im Content sichtbar ist, betrifft nicht Bilder, sondern die doppelt im Markup vorhandene Leistungs-Sektion (siehe Abschnitt 2) – das ist eher ein Code-Qualitäts-Hinweis als ein Beleg für eine durchdachte Responsive-Strategie. **Lücke, sollte bei Vorliegen von `technical-head-analyse.md` nachgetragen werden.**

---

## 4. Technische Umsetzung (Webflow)

`technical-head-analyse.md` lag zum Erstellungszeitpunkt nicht vor (siehe Disclaimer). Aus dem vorhandenen Material lassen sich dennoch folgende technische Indizien ableiten:

- Die Seite läuft auf **Webflow** (CDN-Pfad `cdn.prod.website-files.com`, Plugin-Pfad `plugins/Basic/assets/…`).
- Das Vorhandensein eines Webflow-„Basic“-Plugin-Platzhalterbilds im produktiven Hero deutet auf eine Content-Lücke bei der Umsetzung/Übergabe hin (ein Bild wurde nicht final ersetzt) – das ist typischerweise ein Redaktions-/QA-Versäumnis, kein grundsätzliches Werkzeugproblem.
- Die doppelt vorkommende Leistungs-Sektion (Desktop-/Mobil-Variante im selben Markup) ist ein bekanntes Muster bei nicht optimal konfigurierten Webflow-Breakpoint-Sektionen: Statt eine Sektion responsiv umzubauen, wird der komplette Block dupliziert und je nach Breakpoint ein-/ausgeblendet. Das bläht das DOM auf und kann zu doppelt vorgelesenem Content für Screenreader sowie unnötigem Ballast führen.
- Bilddateien liegen in gemischten Formaten vor (`.webp`, `.jpg`, `.JPG`, `.png`) – kein durchgängig modernes/optimiertes Format über alle Assets hinweg, was auf unterschiedliche Upload-Zeitpunkte/-Workflows hindeutet.

Für belastbare Aussagen zu Ladezeiten, Font-Loading und vollständiger Alt-Text-Abdeckung wird auf `technical-head-analyse.md` verwiesen, sobald verfügbar.

---

## 5. Barrierefreiheit-Indizien

Aus dem Markdown ist erkennbar, dass die **Mehrheit der Bilder ohne Alt-Text** ausgeliefert wird:

- Auf `/leistungen/hochbau` tragen nur die ersten beiden Referenzbilder einen Alt-Text („Drohnenshot“); alle folgenden ca. 18 Referenzbilder in derselben Galerie sind als reines `![](url)` ohne jede Beschreibung eingebunden.
- Auf `/leistungen` ist es ähnlich: Nur das Hero-Bild trägt einen Alt-Text („Grundpfeiler eines Neubauprojektes“), alle neun Leistungsbilder darunter sind ohne Alt-Text.
- Auf der Startseite wird zusätzlich mindestens ein Partner-Logo ohne Alt-Text ausgeliefert.

Das ist sowohl ein WCAG-Konformitätsproblem (Screenreader-Nutzer erhalten keine Bildbeschreibung für Referenzprojekte, die inhaltlich zentrale Vertrauensanker der Seite sind) als auch ein SEO-Nachteil (Google-Bildersuche kann die Bilder nicht sinnvoll einordnen). Positiv hervorzuheben: Wo Alt-Text vorhanden ist, ist er sinnvoll und nicht nur floskelhaft gesetzt („Drohnenshot“, „Grundpfeiler eines Neubauprojektes“) – das Problem ist also nicht mangelndes Know-how, sondern lückenhafte, nicht flächendeckende Umsetzung.

**Bestätigt in voller Breite auf `/referenzen`:** Eine vollständige Prüfung aller 81 Referenzkarten dieser Seite zeigt: **ausnahmslos jedes einzelne Bild** ist ohne Alt-Text eingebunden, und **ausnahmslos jeder Projekt-Link** hat keinen sichtbaren/vorlesbaren Linktext (`[](/referenzen/...)` statt z. B. „Zum Projekt Konrad-Wolf-Straße“). Für Screenreader-Nutzer ist die komplette Referenzseite damit praktisch eine Abfolge nichtssagender Links und unbeschrifteter Bilder – ein systematischer, nicht nur vereinzelter Barrierefreiheits-Mangel auf der Seite, die die stärkste Kompetenz-Beweisführung der ganzen Website leisten soll.

---

## 6. Vergleich zur Wettbewerber-Präsentation

Auf Basis von `serp-wettbewerber.md` (Struktur-Analyse, keine visuelle Prüfung der Wettbewerber möglich):

| Aspekt | BBF Gruppe | Wettbewerber |
|---|---|---|
| Seitenarchitektur | Uneinheitlich: 5 von 9 Leistungen mit Volltiefe, 2 mit externem Verweis | BATEG: durchgängig „Leistungen/Referenzen/Über uns/Karriere“; E.L.I.A.: je Leistung eine Landingpage |
| Referenzdarstellung | ~70+ Karten, aber Duplikate, leere Felder, keine Story/Ergebnis-Erzählung | BATEG: nach Kategorien strukturiert; E.L.I.A.: mit harten Projektdaten inkl. Bauzeiten, ohne erkennbare Lücken |
| Ansprechpartner | Auf der Startseite als Tabellenspalte, teils mit inkonsistenten Fotos | BATEG: eigene, vertrauensbildende Ansprechpartner-Seite |
| Trust-Elemente | Keine Testimonials, keine Bewertungssterne, keine Siegel (nur Partnerlogos) | – (aus Recherche nicht direkt vergleichbar, aber BBF fällt durch Fehlen auf) |
| Markenkonsistenz | Domain-/E-Mail-Zersplitterung über mehrere Tochterfirmen | Wörpel, E.L.I.A., BATEG treten jeweils unter einer Domain/Marke auf |
| Content-Tiefe pro Leistung | Vorhanden (USPs, FAQ) bei den Hauptleistungen – grundsätzlich konkurrenzfähig | Wörpel: Gewerke-Landingpages bis auf Detailebene; Z-Geschossbau: zusätzlich Regional-Landingpages |

**Fazit:** BBF Gruppe hat inhaltlich mehr Substanz als die meisten verglichenen Wettbewerber (mehr Referenzen, mehr Mitarbeiter, mehr Standorte), verspielt diesen Vorteil aber durch mangelnde Sorgfalt in der Umsetzung und eine inkonsistente Seitenarchitektur. Kleinere Wettbewerber wirken durch konsequentere, fehlerfreiere Struktur tendenziell professioneller, obwohl sie objektiv weniger zu zeigen haben.

---

## 7. Findings-Tabelle

| # | Finding | Schweregrad | Beleg | Business-Impact |
|---|---|---|---|---|
| 1 | Platzhalter-SVG als erstes Hero-Bild auf der Startseite | kritisch | `startseite.md` Z. 14 | Erster visueller Eindruck ist ein Icon/Platzhalter statt eines Bau-/Firmenfotos – schadet dem Ersteindruck bei Investoren/Bauherren |
| 2 | Zwei von neun „Mehr erfahren“-Links (Planung, Vermessung) führen auf externe Fremddomains ohne Rückweg | kritisch | `leistungen.md` Z. 72–96 | Conversion-Leck: Besucher verlassen bbf-gruppe.com mitten im Funnel, kein Rückweg zum Kontakt-CTA |
| 3 | Tippfehler „Sanssousi“ statt „Sanssouci“ bei Prestige-Referenz Schloss Sanssouci | hoch | `startseite.md` Z. 85 | Ausgerechnet die glaubwürdigkeitsstiftende Referenz wird durch einen Rechtschreibfehler entwertet |
| 4 | Referenzkarte „MITTENWALDE (HOCHBAU)“ 3× identisch (Startseite) bzw. 2× direkt hintereinander (Leistungsseite) mit identischem Bild und identischen Werten | hoch | `startseite.md` Z. 83; `leistungen_hochbau.md` Z. 113–136 | Wirkt wie ungepflegte CMS-Datenbank statt kuratierter Leistungsschau; auf zwei Seiten reproduzierbar |
| 5 | Identischer Platzhalterwert „4.984 m²“ bei 3 unterschiedlichen Referenzprojekten | hoch | `leistungen_hochbau.md` Z. 117–119, 345–347, 359–361 | Referenzdaten wirken nicht verifizierbar/vertrauenswürdig, Indiz für Copy-Paste-Pflege |
| 6 | CTA-Bug: „Zu unserer Leistungsübersicht“ verlinkt auf /kontakt statt /leistungen | hoch | `startseite.md` Z. 79 | Nutzer landet ungewollt im Kontaktformular statt bei der gewünschten Information; verzerrte Klickpfade |
| 7 | Kaputte/falsche Maps-Links bei 4 Tochtergesellschaften (toter Anker bzw. falscher Standort) | hoch | `startseite.md` Standorttabelle | Kunden/Bewerber finden den richtigen Standort nicht – direkte Auswirkung auf Anfahrt/Vor-Ort-Termine |
| 8 | Weitere Tippfehler: „Chausseestaße“, „Oranieburg“, „Gerneral-Barby“ | mittel | `startseite.md` Standorttabelle/Referenzliste | Häufung von Tippfehlern wirkt unprofessionell, besonders bei Adress-/Prestigeangaben |
| 9 | Rund die Hälfte der Referenzkarten mit leeren Feldern „Grundstück:“/„Nutzfläche:“ | mittel | `leistungen_hochbau.md`, mehrfach; `startseite.md` Z. 85 | Unfertig wirkende Datenblätter; verschenkte Chance auf konkrete, überzeugende Kennzahlen |
| 10 | Mehrheit der Bilder ohne Alt-Text (Referenzgalerien, Leistungsbilder, mind. 1 Partnerlogo) | mittel/hoch (A11y) | `leistungen_hochbau.md`, `leistungen.md` durchgängig; `startseite.md` Z. 94 | WCAG-Verstoß, Screenreader-Nutzer ohne Bildbeschreibung; SEO-Nachteil in Bildersuche |
| 11 | Leistungs-Sektion doppelt im Markup (Desktop-/Mobil-Variante) | mittel | `startseite.md` Z. 67 | Aufgeblähtes DOM, potenziell doppelt vorgelesener Content, Indiz für nicht optimierte Umsetzung |
| 12 | Fremddomain-E-Mail-Adressen bei mehreren Tochterfirmen statt @bbf-gruppe.com | mittel | `startseite.md` Standorttabelle | Widerspricht dem Markenversprechen „alles aus einer Hand“, wirkt wie loser Konzernverbund |
| 13 | Fehlende Trust-Elemente (keine Testimonials, keine Bewertungssterne, keine Siegel) | mittel | `startseite.md` Rohbefunde | Social-Proof-Layer fehlt trotz großer Referenz-Substanz; Wettbewerber (BATEG) nutzen Kategorien-Referenzen stärker |
| 14 | Uneinheitliche Seitentiefe: 5 von 9 Leistungen mit Volltiefe (USP/FAQ/Referenzen), 4 ohne eigene interne Seite | hoch | `leistungen.md`; `startseite.md` Z. 69–78 | Inkonsistentes Nutzererlebnis, einzelne Kernleistungen wirken nachrangig behandelt |
| 15 | Unsichtbares Steuerzeichen im E-Mail-Link (plant Hey Dahlke Meurer) | mittel | `kontakt.md` Z. 228 | mailto-Link potenziell technisch defekt, Kontaktaufnahme kann scheitern |
| 16 | Rohe GPS-Koordinaten als sichtbarer Klartext in jeder der 81 Referenzkarten (158 Zeilen betroffen) | hoch | `referenzen.md`, durchgängig | Wirkt wie ein technischer Defekt/unfertige Umsetzung; verwirrt Besucher, kein erkennbarer Nutzen der sichtbaren Zahlen |
| 17 | Alle 81 Referenzkarten auf `/referenzen` ohne Bild-Alt-Text und ohne sichtbaren Linktext | hoch (A11y) | `referenzen.md`, durchgängig (81/81) | Systematischer, nicht vereinzelter Barrierefreiheits-Mangel ausgerechnet auf der Kompetenz-Beweis-Seite |
| 18 | Widersprüchliche Ansprechpartner-Zuordnung: Startseite nennt Raúl Comesaña für BBF Gebäudetechnik, Kontaktseite nennt Benjamin Thom; bei Gebr. Pfeil GmbH zeigt die Kontaktseite den Namen „Enrico Pollnick“ mit dem Foto von Mark Ahner | hoch | `kontakt.md` Z. 104–118, 151–155; Abgleich mit `startseite.md` | Kunden wissen nicht, wer tatsächlich zuständig ist; wirkt bei genauerem Hinsehen unseriös gepflegt |
| 19 | Maps-Links exakt lokalisiert: Spree Gerüstbau→Mittenwalde-Koordinaten, Herold GaLaBau & JoMi→Grünheide-Koordinaten, Elektrotechnik→„(#)“ | hoch | `kontakt.md` Z. 164–168, 181–185, 236–240, 254–258 | Auf zwei Seiten (Start + Kontakt) identisch reproduzierbar – kein Einzelfall, sondern systematischer Pflegefehler |

---

## 8. 3 Killer-Argumente für den Vertriebstermin

**1. „Klicken Sie mit mir auf ‚Mehr erfahren‘ bei Planung oder Vermessung – Sie verlassen gerade Ihre eigene Website.“**
Live im Termin an einem der beiden Buttons auf `/leistungen` demonstrierbar: Der Klick führt nicht auf eine BBF-Seite, sondern direkt auf `plant-plant.de` bzw. `plan3d-berlin.de` – fremde Domains, fremdes Branding, kein Rückweg zum eigenen Kontaktformular. Zwei von neun Kernleistungen schicken interessierte Besucher aktiv von der eigenen Website weg, mitten im Entscheidungsprozess. Das ist ein direkter, messbarer Conversion-Verlust und in Sekunden live vorführbar.

**2. „Ihr eindrucksvollstes Referenzprojekt hat einen Rechtschreibfehler – ausgerechnet beim Namen, und zwar auf zwei verschiedenen Seiten.“**
Schloss Sanssouci, eines der bekanntesten Bauwerke Deutschlands und UNESCO-Welterbe, wird sowohl auf der Startseite als auch als eigener Referenz-Seitentitel auf `/referenzen` als „Sanssousi“ geführt – derselbe Fehler an zwei unabhängigen Stellen, während die zugehörige Bilddatei im Hintergrund korrekt „Schloss Sanssouci“ heißt. Das ist in zehn Sekunden zeigbar (Strg+F auf der Live-Seite) und wirkt gerade deshalb so stark, weil es exakt die Referenz betrifft, die am meisten Kompetenz und Prestige signalisieren soll. Ergänzend zeigbar: dieselbe Referenzkarte „Mittenwalde (Hochbau)“ taucht dreifach identisch auf, und der Wert „4.984 m²“ wiederholt sich bei drei völlig verschiedenen Projekten – das lässt sich als Muster („das ist kein Einzelfall, das ist System“) erzählen, nicht als Petitesse.

**3. „Auf jeder einzelnen der 81 Referenzkarten stehen nackte GPS-Koordinaten im Text – und Ihr Leistungsübersicht-Button tut nicht das, was er verspricht.“**
Öffnet man `/referenzen`, erscheinen auf allen 81 Projektkarten rohe Zahlen wie „52.53958463322082 / 13.48193231141988“ mitten im sichtbaren Text – ein technischer Konfigurationsfehler, der auf einen Blick als „hier stimmt etwas mit der Umsetzung nicht“ lesbar ist, ganz ohne dass man Code können muss. Kombiniert mit dem CTA-Bug auf der Startseite („Zu unserer Leistungsübersicht“ verlinkt fälschlich auf das Kontaktformular statt auf die Leistungsseite) und den mindestens vier fehlerhaften Google-Maps-Links bei Tochtergesellschaften (Spree Gerüstbau zeigt auf Mittenwalde statt Luckau, Elektrotechnik verlinkt auf „#“) lässt sich in drei, vier Klicks im Termin ein durchgängiges Bild zeichnen: Diese Website wurde aufgesetzt, aber seither nicht mehr systematisch gepflegt oder getestet.

---

*Erstellt für den Vertriebstermin am 15.07.2026. `referenzen.md`, `kontakt.md` und `ueber-uns.md` sind eingearbeitet. Eine Ergänzung aus `technical-head-analyse.md` sollte nachgetragen werden, sobald diese Datei vorliegt – insbesondere für Abschnitt 3 (Mobile-Bildvarianten) und Abschnitt 4 (Ladeverhalten/Font-Loading).*
