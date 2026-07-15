# Analyse-Dimension: Design & UX – bbf-gruppe.com

**Stand:** 15.07.2026 · Erstellt für Vertriebstermin (Webdesign-Agentur)

## 0. Methodik-Disclaimer

**Diese Design-Analyse basiert auf Inhaltsstruktur und Code-Indizien, nicht auf visueller Begutachtung (Screenshots).** In dieser Arbeitsumgebung bestand kein Netzwerkzugriff auf bbf-gruppe.com und kein Zugriff auf Screenshot-/Rendering-Werkzeuge (kein Playwright, kein Lighthouse, kein Browser). Alle Aussagen stützen sich ausschließlich auf:

- den gecrawlten HTML/Markdown-Content der Seiten (`daten/crawl/startseite.md`, `leistungen.md`, `leistungen_hochbau.md`),
- Bilddateinamen, Alt-Texte, Linkziele und Layout-Reihenfolge, wie sie im Markdown erkennbar sind,
- technische Webflow-Indizien (CDN-Pfade, Platzhalter-Assets, Markup-Duplikate),
- die Wettbewerber-Recherche `daten/recherche/serp-wettbewerber.md`.

**Es werden keine Aussagen zu Farben, Schriftarten, Bildschirmauflösung, Ladezeiten (gemessen) oder visueller Ästhetik getroffen, die nicht aus dem Quelltext ableitbar sind.** Für eine vollständige UI-Bewertung (visuelle Konsistenz, Typografie, Farbwelt, tatsächliches Ladeverhalten, mobile Darstellung) **wird eine visuelle Prüfung per Browser vor oder im Termin dringend empfohlen** – die hier dokumentierten Befunde sind aber bereits aus dem Code heraus so konkret, dass sie im Termin unabhängig davon überzeugend gezeigt werden können (siehe Abschnitt 9).

**Datenlage:** Die parallel angeforderten Zusatzquellen `technical-head-analyse.md`, `referenzen.md`, `kontakt.md` und `ueber-uns.md` lagen zum Zeitpunkt der Erstellung dieses Dokuments **noch nicht vor** (paralleler Agent nicht fertig). Wo diese Quellen relevant gewesen wären, ist das explizit als Lücke markiert. Die Kernaussagen dieses Dokuments stehen unabhängig davon bereits auf solider Quellenbasis (Startseite + zwei Leistungsseiten sind vollständig ausgewertet).

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

**Vergleich zu Wettbewerbern (aus `serp-wettbewerber.md`):** BATEG pflegt eine „saubere thematische Seitenarchitektur“ (Leistungen/Referenzen/Über uns/Karriere) inklusive einer eigenen Ansprechpartner-Seite und nach Kategorien strukturierten Referenzen. E.L.I.A. hat für jede Kernleistung eine eigene, keyword-sauber betitelte Landingpage. Z-Geschossbau geht noch weiter mit Leistung×Region-Kombinationsseiten. BBF Gruppe hat zwar mehr Substanz (350 MA, 8 Standorte, deutlich mehr Referenzprojekte als alle genannten Wettbewerber), bildet das aber nicht in einer durchgängig konsistenten Seitenarchitektur ab – fünf Leistungen bekommen die „volle“ Behandlung (USP-Sektion, FAQ, Referenzen), vier bekommen nur einen Kurzabschnitt oder verweisen extern.

---

## 2. Content-Qualität & Sorgfalt

Aus `startseite.md` und bestätigt durch `leistungen_hochbau.md` lassen sich konkrete, leicht nachprüfbare Qualitätsmängel belegen:

**Tippfehler in Firmen- und Referenzdaten:**
- „Chausseestaße“ statt „Chausseestraße“ (Adresse BBF Tiefbau GmbH, Bersteland)
- „Sanssousi“ statt „Sanssouci“ – ausgerechnet beim Prestige-Referenzprojekt Schloss Sanssouci (UNESCO-Welterbe)
- „Oranieburg“ statt „Oranienburg“
- „Gerneral-Barby“ (vermutlich „General-Barby“) in einer weiteren Referenzangabe

**Doppelte/redundante Inhalte:**
- Die Referenzkarte „MITTENWALDE (HOCHBAU)“ (Grundstück 4.984 m², Nutzfläche 966 m²) erscheint laut Startseiten-Slider 3× identisch – und ist auf `/leistungen/hochbau` **direkt zweimal hintereinander** mit demselben Bild (`DJI_0021 1.webp`) und denselben Werten bestätigt (Zeilen 113–136 der Datei). Kein Einzelfall, sondern auf zwei Seiten reproduzierbar.
- Auffällig: Der exakte Grundstückswert „4.984 m²“ taucht auf `/leistungen/hochbau` bei **drei völlig unterschiedlichen Projekten** auf – Mittenwalde (Hochbau), „Beamten-Wohnungs-Verein zu Berlin e.G.“ und „Katholische Kirchengemeinde Sankt Matthias Berlin“ (Zeilen 117–119, 345–347, 359–361). Das ist mit an Sicherheit grenzender Wahrscheinlichkeit kopiertes Platzhalter-Datenmaterial, das nie durch echte, projektspezifische Werte ersetzt wurde.
- Die Leistungs-Sektion („Planen, bauen und betreuen“) erscheint laut Analysehinweis in `startseite.md` zweifach im Markup (Desktop-/Mobil-Variante) – ein technisches Indiz für eine nicht sauber responsive umgesetzte Sektion.

**Leere Datenfelder:** Auf `/leistungen/hochbau` fehlt bei rund der Hälfte der ca. 20 gelisteten Referenzprojekte entweder der Wert für „Grundstück:“ oder „Nutzfläche:“ (u. a. Gesundheitszentrum Schwante, Ferienhaus Mönblick Dranske, Wohnhäuser Borkwalde, Stadthäuser Zeuthener Winkel, Dianastraße Potsdam, mehrere Sanierungsprojekte). Auf der Startseite wird dasselbe Muster für ~70 Referenzkarten sitewide bestätigt.

**Tote/falsche Links:**
- Maps-Link von BBF Elektrotechnik GmbH ist „#“ (toter Anker, führt nirgendwohin)
- Maps-Link von BBF Spree Gerüstbau GmbH zeigt auf Mittenwalde statt auf den tatsächlichen Standort Luckau
- Maps-Links von BBF Herold Ingenieurgesellschaft GaLaBau und JoMi Gartenbau zeigen beide auf Grünheide statt auf die angegebene Adresse Soldiner Str. 53, Berlin
- E-Mail-Link von „plant Hey Dahlke Meurer Planungsgesellschaft mbH“ enthält laut Analysehinweis ein unsichtbares Steuerzeichen – der `mailto:`-Link ist damit potenziell technisch defekt

**Markenfragmentierung:** Mehrere Tochtergesellschaften nutzen Fremddomain-E-Mail-Adressen statt `@bbf-gruppe.com` (`info@heroldgalabau.de`, `jomi@gartenbau-in-berlin.de`, `Info@plan3d-berlin.de`, `Kontakt@plant-plant.de`, `info@spreegeruestbau.de`) – ein Widerspruch zum zentralen Markenversprechen „Ganzheitliche Lösungen … alles aus einer Hand“.

**Personendaten-Inkonsistenz:** Raúl Comesaña M. wird auf der Startseite als Ansprechpartner für 5 verschiedene Gesellschaften geführt, dabei aber mit 3 unterschiedlichen Portraitfotos/Dateien dargestellt – ein Indiz für unkoordinierte Content-Pflege über mehrere Tochtermarken hinweg.

Diese Befunde sind in ihrer Summe deutlich mehr als „Kleinigkeiten“: Sie betreffen ausgerechnet die Inhalte, die im Vertriebsprozess Vertrauen aufbauen sollen (Referenzen, Standortdaten, Ansprechpartner) und sind alle direkt auf der Seite nachprüfbar.

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
| 15 | Unsichtbares Steuerzeichen im E-Mail-Link (plant Hey Dahlke Meurer) | mittel | `startseite.md` Z. 61 | mailto-Link potenziell technisch defekt, Kontaktaufnahme kann scheitern |

---

## 8. 3 Killer-Argumente für den Vertriebstermin

**1. „Klicken Sie mit mir auf ‚Mehr erfahren‘ bei Planung oder Vermessung – Sie verlassen gerade Ihre eigene Website.“**
Live im Termin an einem der beiden Buttons auf `/leistungen` demonstrierbar: Der Klick führt nicht auf eine BBF-Seite, sondern direkt auf `plant-plant.de` bzw. `plan3d-berlin.de` – fremde Domains, fremdes Branding, kein Rückweg zum eigenen Kontaktformular. Zwei von neun Kernleistungen schicken interessierte Besucher aktiv von der eigenen Website weg, mitten im Entscheidungsprozess. Das ist ein direkter, messbarer Conversion-Verlust und in Sekunden live vorführbar.

**2. „Ihr eindrucksvollstes Referenzprojekt hat einen Rechtschreibfehler – ausgerechnet beim Namen.“**
Schloss Sanssouci, eines der bekanntesten Bauwerke Deutschlands und UNESCO-Welterbe, wird auf der Startseite als „Sanssousi“ geführt. Das ist in zehn Sekunden zeigbar (Strg+F auf der Live-Seite) und wirkt gerade deshalb so stark, weil es exakt die Referenz betrifft, die am meisten Kompetenz und Prestige signalisieren soll. Ergänzend zeigbar: dieselbe Referenzkarte „Mittenwalde (Hochbau)“ taucht dreifach identisch auf, und der Wert „4.984 m²“ wiederholt sich bei drei völlig verschiedenen Projekten – das lässt sich als Muster („das ist kein Einzelfall, das ist System“) erzählen, nicht als Petitesse.

**3. „Ihr Kontaktbutton ‚Leistungsübersicht‘ tut nicht das, was er verspricht – und mehrere Standort-Links auf Google Maps führen zum falschen Ort.“**
Der Button „Zu unserer Leistungsübersicht“ verlinkt fälschlich direkt auf das Kontaktformular statt auf die Leistungsseite; die Maps-Links von mindestens vier Tochtergesellschaften sind entweder tot oder zeigen auf einen falschen Standort (u. a. Spree Gerüstbau: Mittenwalde statt Luckau; Elektrotechnik: toter Anker). Beides ist mit einem Klick im Termin vorführbar und macht sehr konkret erlebbar, was „fehlende technische/inhaltliche Qualitätssicherung“ für einen Bauherren oder Bewerber im Alltag bedeutet: Er findet den Ansprechpartner nicht, den er sucht.

---

*Erstellt für den Vertriebstermin am 15.07.2026. Ergänzungen aus `technical-head-analyse.md`, `referenzen.md`, `kontakt.md` und `ueber-uns.md` sollten nachgetragen werden, sobald diese Dateien vorliegen – insbesondere für Abschnitt 3 (Mobile-Bildvarianten) und Abschnitt 4 (Ladeverhalten/Font-Loading).*
