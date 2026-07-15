# Analyse-Dimension: Verkaufspsychologie & Conversion – bbf-gruppe.com

**Kunde:** BBF Gruppe (Berlin Brandenburg Firmen Gruppe) – Projektentwickler & Generalunternehmer, ~350 Mitarbeiter, 7–8 Standorte Berlin/Brandenburg
**Stand:** 15.07.2026 · Erstellt für Vertriebstermin Webdesign-Agentur
**Datenbasis:** `daten/crawl/startseite.md`, `daten/crawl/leistungen.md`, `daten/crawl/leistungen_hochbau.md`, `daten/recherche/serp-wettbewerber.md`, `daten/recherche/reputation-lokal-marke.md`

**Wichtiger Hinweis zur Datenlage:** Die Dateien `daten/crawl/referenzen.md`, `daten/crawl/kontakt.md` und `daten/crawl/ueber-uns.md` lagen zum Zeitpunkt dieser Analyse **noch nicht vor** (paralleler Crawl-Agent). Aussagen zu Referenzen-Detailseiten, dem eigentlichen Kontaktformular (Felder, Response-Time-Versprechen, Pflichtangaben) und der Über-uns-Seite stützen sich daher nur auf indirekte Erwähnungen in den SERP-/Reputations-Recherchen sowie auf die Rohbefunde der Startseite. Diese Lücken sind unten explizit gekennzeichnet und sollten vor einer finalen Kundenpräsentation nachgezogen werden, sobald die Dateien verfügbar sind.

---

## 1. Value Proposition & Botschaft

Die Startseite transportiert die Kernbotschaft über vier Hero-Slides: „Wir bauen Zukunft", „Über 30 Jahre Erfahrung in der Projektentwicklung", „Ihr Generalunternehmer für Berlin & Brandenburg", „Ganzheitliche Lösungen von der Planung bis zur Schlüsselübergabe". Im Fließtext wird das Angebot sachlich korrekt beschrieben: Projektentwicklung und Baukompetenz „aus einer Hand" entlang der gesamten Wertschöpfungskette (Ankauf, Planung, Bau/Sanierung, Verkauf/Vermietung), mit Kennzahlen wie ca. 5 Mio. m² entwickelt in 10 Jahren und >45.000 m² realisierte Wohn-/Gewerbefläche.

**Klarheit des Angebots:** Grundsätzlich verständlich, aber generisch. „Wir bauen Zukunft" ist ein austauschbarer Claim ohne Differenzierung; erst die zweite Zeile („Ihr Projektentwickler und Generalunternehmer aus Berlin & Brandenburg") liefert das eigentliche Nutzenversprechen. Die Leistungen-Seite (`leistungen.md`) formuliert es klarer: „Unser Leistungsspektrum richtet sich an private, gewerbliche und kommunale Auftraggeber […] alle Leistungen zuverlässig und kompetent inhouse aus einer Hand."

**Zielgruppendifferenzierung (privat/gewerblich/öffentlich):** Wird explizit benannt (Startseite: „für private, gewerbliche und öffentliche Auftraggeber"; Leistungen-FAQ: „private Bauherren, gewerbliche Unternehmen, Investoren sowie kommunale und öffentliche Auftraggeber"), aber **nirgends inhaltlich getrennt bespielt**. Es gibt keine eigenen Landingpages, Content-Pfade oder auch nur unterschiedliche Formulierungen je Zielgruppe – ein privater Bauherr mit Einfamilienhaus-Sanierung und eine Kommune mit Schulneubau-Ausschreibung landen auf identischem Content und identischem CTA. Das ist verschenktes Potenzial, weil die drei Zielgruppen fundamental unterschiedliche Entscheidungslogiken haben (privat: Vertrauen/Emotion; gewerblich/öffentlich: Referenzen, Fristen, Ausschreibungsfähigkeit).

**Vergleich zur Wettbewerber-Positionierung (aus `serp-wettbewerber.md`):**
- **E.L.I.A. Bau & Projektmanagement** führt „Generalunternehmer Berlin & Brandenburg" wörtlich als Meta-Title der Startseite – exaktes Keyword-Match zur Suchintention und Grund, warum E.L.I.A. bei „Generalunternehmer Brandenburg" auf Platz 1 rankt, während BBF dort nur mit der **englischen** Seite auf Platz ~4 auftaucht.
- **Z-Geschossbau** positioniert sich schlanker: „Ihr Partner im Schlüsselfertigbau" plus dedizierte Regional-Landingpages je Bundesland.
- **Wörpel Bau** (nur ~30 MA) positioniert sich über Beweis statt Behauptung: „über 5.000 Bauvorhaben seit 1997".
- **BATEG** (~100 MA) kombiniert Mittelstands-Nahbarkeit mit Konzern-Leistungsfähigkeit: „Flexibilität des Mittelstands mit der Leistungskraft eines Großkonzerns."

Im Ergebnis ist BBFs Botschaft inhaltlich nicht schwächer als die der Wettbewerber – aber deutlich weniger zugespitzt und nicht keyword-scharf positioniert, während kleinere Wettbewerber mit prägnanteren, SEO-tauglicheren Claims die Sichtbarkeit gewinnen (siehe `serp-wettbewerber.md`: 6 von 7 Geschäfts-Keywords ohne BBF in Top 10).

---

## 2. CTA-Analyse

**Befund aus den Rohdaten (`startseite.md`):** Auf der Startseite erscheint der Button **„Jetzt kontaktieren" → /kontakt fünfmal** – im Hero (4× über die Slides) sowie ein weiteres Mal in der Sektion „Ihr starker Baupartner in der Region". Es gibt **keine einzige CTA-Differenzierung** nach Zielgruppe (privat/gewerblich/öffentlich), Funnel-Stufe (Erstinformation vs. Angebot vs. Bewerbung) oder Anliegen.

**Kritischer Bug:** Der Button „Zu unserer Leistungsübersicht" in der Leistungs-Sektion der Startseite verlinkt fälschlich auf **/kontakt statt /leistungen** (`startseite.md`, Zeile 79). Ein Nutzer, der sich zunächst nur informieren will („Was bietet BBF im Bereich Gerüstbau/Vermessung/Planung an?"), wird stattdessen direkt vor ein Kontaktformular gesetzt. Verkaufspsychologisch ist das ein doppeltes Problem:
1. Nutzer, die noch nicht kontaktbereit sind, brechen ab (verlorener Besucher, der bei funktionierendem Link vermutlich weiter im Funnel geblieben wäre).
2. Nutzer, die trotzdem weiterklicken, landen unqualifiziert und ohne Leistungsverständnis im Formular – schlechtere Lead-Qualität für den Vertrieb.

**Funnel-Logik – fehlende Stufen:** Aus der FAQ auf `leistungen.md` geht hervor, dass BBF selbst zwischen **kostenfreier Erstberatung** und späterer, kostenpflichtiger **Angebotserstellung** unterscheidet („Die Erstberatung ist selbstverständlich kostenfrei. Eine Angebotserstellung erfolgt erst nach Klärung der Rahmenbedingungen"). Diese naheliegende Zwei-Stufen-Logik (niedrigschwelliger Erstkontakt vs. verbindliche Anfrage) wird auf der Website **an keiner Stelle im CTA-Text abgebildet** – es gibt nur den einen generischen Button „Jetzt kontaktieren", der weder die Kostenfreiheit noch die geringe Verbindlichkeit kommuniziert. Das ist eine leicht behebbare, aber conversion-relevante Lücke: „Kostenloses Erstgespräch vereinbaren" senkt die Einstiegshürde nachweislich stärker als ein unspezifisches „Jetzt kontaktieren".

Ebenso fehlt eine erkennbare **Karriere-CTA** auf der Startseite, obwohl BBF laut `leistungen_hochbau.md`-FAQ aktiv nach Auszubildenden sucht und laut `reputation-lokal-marke.md` mehrere Personio-Jobportale und eine eigene Karriere-Domain (karriere-bbf-online.com) betreibt – auf der Startseite selbst taucht „Karriere" im gecrawlten Content nicht als CTA auf.

**Weitere Funnel-Reibung (`leistungen.md`):** Die „Mehr erfahren"-Buttons der Leistungsbereiche **Planung** und **Vermessung** verlinken nicht auf interne BBF-Unterseiten, sondern auf externe Tochterdomains (`plant-plant.de`, `plan3d-berlin.de`, Zeilen 76 und 96). Der Nutzer verlässt damit die eigentliche bbf-gruppe.com-Domain und den dort etablierten Kontakt-Funnel vollständig, ohne garantierten Rückweg – ein klassisches Conversion-Leck, das sich mit der in `serp-wettbewerber.md` beschriebenen Domain-Zersplitterung deckt (mind. 4–6 Parallel-Domains der Unternehmensgruppe).

---

## 3. Vertrauenssignale (Cialdini-Rahmen)

**Social Proof – kritische Lücke.** Laut `reputation-lokal-marke.md` existieren **praktisch keine Kundenbewertungen**: keine auffindbaren Google-Rezensionen für „BBF Gruppe", „BBF Bau GmbH" oder „BBF Projekt GmbH", kein Knowledge-Panel mit Sternebewertung. Der einzige prominent rankende „Bewertungs"-Inhalt ist ein fremdgesteuerter Scoredex-Faktencheck, der Interessenten explizit zur Vorsicht rät („vor Vertragsabschluss Leistungsumfang, Gewährleistung, Sicherheiten, Referenzen klären"). Arbeitgeberbewertungen (kununu) sind mit 2–4 Bewertungen statistisch nicht belastbar. Für eine Generalunternehmer-Entscheidung – hohes Investitionsvolumen, lange Bindungsdauer, hohes wahrgenommenes Risiko – ist das Fehlen von Social Proof der gravierendste Vertrauens-Gap dieser Analyse.

**Autorität – vorhanden, aber unvollständig genutzt.** Die Startseite liefert starke quantitative Autoritätssignale: „1 Gruppe · 8 Standorte · >30 Jahre Erfahrung · 350 Mitarbeiter" sowie „ca. 5 Millionen Quadratmeter entwickelt" in 10 Jahren. Das ist deutlich mehr Substanz als bei den meisten SERP-Wettbewerbern (Wörpel ~30 MA, E.L.I.A./Z-Geschossbau ohne vergleichbare Größenangaben). Es fehlen jedoch **Zertifikate, Gütesiegel oder Verbandsmitgliedschaften** (z. B. Handwerkskammer-Meisterbetrieb, RAL-Gütezeichen, ISO-Zertifizierung, Bau-Berufsgenossenschaft) – die Startseite zeigt lediglich Partner-Logos (Dr. Klein, 1. FC Union Berlin, Berlin Brandenburg International School, ADAC, ein weiteres Logo ohne Alt-Text). Partnerschaften sind ein schwächeres Autoritätssignal als geprüfte Zertifikate, insbesondere gegenüber gewerblichen/öffentlichen Auftraggebern, die in Ausschreibungen typischerweise Zertifikate abfragen.

**Konsistenz – aktiv geschwächt.** Die Kennzahlen widersprechen sich zwischen Sprachversionen und Unterseiten: „7 Standorte/200 MA/25 Jahre" (EN-Version bzw. ältere Quellen) vs. „8 Standorte/350 MA/30 Jahre" (aktuelle DE-Startseite) – dokumentiert sowohl im Rohbefund der Startseite als auch in `serp-wettbewerber.md` (Abschnitt 3.3) und `reputation-lokal-marke.md` (Abschnitt 1.4/4.2, dort sogar mit Varianten „30/90/150/350" Mitarbeiter je nach Quelle). Das ist verkaufspsychologisch besonders problematisch, weil es exakt die Kernbotschaft „Verlässlichkeit" (im Hero-Text: „Ihr Generalunternehmer … zuverlässig, leistungsstark und termingerecht") untergräbt – ein Unternehmen, das sich nicht einmal bei den eigenen Basisfakten einig ist, wirkt weniger glaubwürdig, gerade bei einem Vertrauensgut wie einer mehrjährigen Bauleistung.

**Sympathie – positiver Ansatz, mit Bruch.** Die Startseite enthält persönliche Zitate der geschäftsführenden Gesellschafter Raúl Comesaña M. (BBF Bau GmbH, Verantwortung für Projekte/Mitarbeiter/Region) und Jesús Comesaña M. (BBF Projekt GmbH, Zusammenhalt als gelebte Praxis) – ein guter Ansatz für Nahbarkeit und Familienunternehmen-Glaubwürdigkeit. Geschwächt wird dieser Effekt jedoch dadurch, dass Raúl Comesaña M. laut Standorte-Tabelle als Ansprechpartner für **fünf verschiedene Gesellschaften** gleichzeitig auftritt, dabei aber mit **drei unterschiedlichen Portraitfotos** verwendet wird – ein Detail, das bei genauerem Hinsehen (oder auf Zoom-Ebene) Unstimmigkeit statt Authentizität signalisiert.

**Knappheit/Dringlichkeit – fehlt vollständig.** Es gibt keinerlei Kapazitäts-, Saison- oder Terminsignale („begrenzte Kapazitäten für 2026", „Projektstart nur noch ab Q3 möglich" o. ä.), obwohl Bauunternehmen real kapazitätsbeschränkt arbeiten und ein glaubwürdiges Dringlichkeitsargument (z. B. Vorlaufzeiten für Planung/Genehmigung) hätten. In Kombination mit dem undifferenzierten CTA fehlt damit jeder Anreiz zur zeitnahen Kontaktaufnahme.

---

## 4. Referenzen als Verkaufsinstrument

Laut Rohbefund der Startseite umfasst der Referenzen-Bereich einen Slider sowie **ca. 70 Referenzkarten** über die Sparten Tiefbau, Hochbau, Projektentwicklung, GaLaBau, Gerüstbau, Vermessung/3D-Laserscan und Planung. Die Detailansicht auf `leistungen_hochbau.md` bestätigt das Muster im Hochbau-Bereich: 22 Referenzkarten mit lediglich den Feldern „Grundstück:" und „Nutzfläche:", **viele davon leer** (z. B. „Stadthäuser im Zeuthener Winkel", „Sanierung eines Mehrfamilienhauses in Eichwalde" – beide ohne jegliche Flächenangabe). Leere Werte werden dabei sichtbar mitgerendert statt ausgeblendet – ein technisches/redaktionelles Pflegeproblem, das unprofessionell wirkt.

**Fehlende Story-Struktur:** Keine der Referenzkarten folgt einem Herausforderung→Lösung→Ergebnis-Muster. Es gibt keine Kundenzitate zu einzelnen Projekten, keine Angaben zu Bauzeit, Budget oder besonderen Herausforderungen – nur Projektname, Ort und (unvollständig) zwei Flächenkennzahlen.

**Bug im Slider:** Der Referenzen-Slider auf der Startseite zeigt laut Rohbefund **dreimal identisch die Karte „MITTENWALDE (HOCHBAU)"** (Grundstück 4.984 m², Nutzfläche 966 m²) – der erste visuelle Eindruck im Referenzen-Bereich ist damit ein sichtbarer Duplikat-Fehler statt Vielfalt zu demonstrieren.

**Ungenutztes Prestige-Potenzial:** Unter den Referenzen finden sich hochkarätige Objekte – Schloss Sanssouci (dabei mit Tippfehler „Sanssousi"), Pergamonmuseum, Bauhaus Dessau, Flughafen Tempelhof, Europäisches Patentamt, Warner Music Group, ADAC Fahrsicherheitszentrum, Bötzow Brauerei, dstrct.berlin. Diese Namen sind für sich genommen starke Vertrauensanker – werden aber exakt wie jede andere Referenzkarte mit zwei Flächenzahlen abgehandelt, statt als Leuchtturm-Case-Study mit Bildern, Zitat und Kontext präsentiert.

**Vergleich zur Wettbewerber-Praxis (`serp-wettbewerber.md`):**
- **E.L.I.A.** liefert harte Projektdaten inkl. Adresse, m² und **Bauzeiten** (z. B. Otto-Franke-Str. 45 Adlershof: 8.432 m²; Fichtestr. 5 Ludwigsfelde: 3.327 m² Neubau + 1.208 m² Sanierung).
- **BATEG** strukturiert Referenzen nach Kategorien (Wohnungsbau, realisierte Projekte) und stellt Leuchtturm-Projekte wie die Museumsinsel Berlin heraus.
- **Wörpel Bau** verzichtet auf Einzelprojekt-Details, argumentiert stattdessen mit der aggregierten Zahl „über 5.000 Bauvorhaben seit 1997" plus benannten Bestandskunden (Berliner Tafel e.V.).

BBF hat in der reinen Masse und Prestige-Dichte der Referenzen mehr Substanz als alle vier verglichenen Wettbewerber – nutzt das aber informationsärmer als der direkte Konkurrent E.L.I.A. und schlechter strukturiert als BATEG.

**Hinweis zur Datenlücke:** Da `referenzen.md` noch nicht vorlag, konnte die eigentliche `/referenzen`-Übersichtsseite (jenseits der auf der Startseite und der Hochbau-Unterseite gezeigten Karten) nicht direkt geprüft werden. Aus `serp-wettbewerber.md` ist bekannt, dass mindestens eine Einzelreferenz-Unterseite (`/referenzen/grunheide-locknitztal`, 3,2 ha) sowie die EN-Version (`/en/referenzen/borsigturm`, 200 T€ Auftragsvolumen) detailliertere Angaben als die Homepage-Karten enthalten – das deutet auf uneinheitliche Informationstiefe zwischen den Seiten hin, konnte aber nicht abschließend verifiziert werden.

---

## 5. Kontaktfriktion

Da `kontakt.md` nicht vorlag, wird dieser Abschnitt aus den verfügbaren indirekten Daten abgeleitet – das eigentliche Kontaktformular (Pflichtfelder, Response-Time-Versprechen, Datenschutzhinweise) konnte nicht geprüft werden.

Aus der Standorte-Tabelle der Startseite lassen sich dennoch mehrere Reibungspunkte ableiten:

- **Zersplitterte Kontaktwege:** Für die 12 gelisteten Gesellschaften/Standorte existieren **elf verschiedene E-Mail-Adressen** (`info.projekt@`, `bau@`, `hochbau@`, `technik@`, `tiefbau@`, `info.galabau@`, plus vier Fremddomain-Adressen). Ein Interessent muss selbst herausfinden, welche Adresse zu seinem Anliegen passt – es gibt keine erkennbare zentrale „Ein Klick genügt"-Kontaktmöglichkeit auf der Startseite selbst, sondern nur den Verweis auf /kontakt.
- **Fremddomain-E-Mails brechen Konsistenz:** Vier Gesellschaften verwenden E-Mail-Adressen auf fremden Domains (`info@heroldgalabau.de`, `jomi@gartenbau-in-berlin.de`, `Info@plan3d-berlin.de`, `info@spreegeruestbau.de`) statt `@bbf-gruppe.com` – für einen Erstkontakt wirkt das wie ein Bruch in der Markenwahrnehmung und kann bei sicherheitsbewussten gewerblichen/öffentlichen Auftraggebern Rückfragen zur Seriosität auslösen.
- **Defekte/falsche Anfahrts-Links:** Mindestens vier Standorte haben fehlerhafte Google-Maps-Verlinkungen: BBF Elektrotechnik Luckau verlinkt auf „#" (toter Link), BBF Spree Gerüstbau zeigt auf Mittenwalde statt Luckau, sowohl Herold Ingenieurgesellschaft als auch JoMi Gartenbau (beide Soldiner Str. 53, Berlin) zeigen auf Grünheide. Wer den Standort real aufsuchen möchte, wird fehlgeleitet.
- **Vorzeitige Formular-Zwangsführung:** Der oben beschriebene Bug (Leistungsübersicht-Button → /kontakt) verstärkt die Kontaktfriktion zusätzlich, weil er einen eigentlich harmlosen Informations-Klick in eine (ungewollte) Kontaktaktion verwandelt.
- **Keine erkennbare Reaktionszeit-Zusage** im gecrawlten Content (z. B. „Antwort innerhalb 24h") – kann aber aufgrund der fehlenden `kontakt.md` nicht abschließend ausgeschlossen werden; explizit als Lücke markiert.

---

## 6. Findings-Tabelle

| # | Finding | Schweregrad | Beleg | Business-Impact |
|---|---|---|---|---|
| 1 | Bug: Button „Zu unserer Leistungsübersicht" verlinkt auf /kontakt statt /leistungen | **kritisch** | `startseite.md`, Z. 79 | Informationssuchende Nutzer werden vorzeitig zum Formular gezwungen → Absprung oder unqualifizierte Leads |
| 2 | Keine Kundenbewertungen auffindbar (0 Google-Rezensionen) | **kritisch** | `reputation-lokal-marke.md`, Abschnitt 1.2/2 | Wichtigster Vertrauensanker für hochpreisige GU-Entscheidung fehlt komplett |
| 3 | 5× identischer CTA „Jetzt kontaktieren" ohne Zielgruppen-/Funnel-Differenzierung | hoch | `startseite.md` Rohbefunde | Keine Segmentierung privat/gewerblich/öffentlich, keine Erstgespräch/Angebot-Unterscheidung trotz eigener FAQ-Logik |
| 4 | Fakten-Widersprüche (7 vs. 8 Standorte, 200 vs. 350 MA, 25 vs. 30 Jahre) | hoch | `startseite.md`; `serp-wettbewerber.md` 3.3; `reputation-lokal-marke.md` 1.4/4.2 | Untergräbt die Kernbotschaft „Verlässlichkeit"; Risiko fehlerhafter KI-/AI-Overview-Antworten |
| 5 | Referenzen ohne Story (Herausforderung→Lösung→Ergebnis), viele leere Flächenfelder | hoch | `startseite.md`; `leistungen_hochbau.md` | Prestigeprojekte (Sanssouci, Pergamonmuseum, Tempelhof) werden als Trust-Hebel verschenkt |
| 6 | „Mehr erfahren"-Links (Planung, Vermessung) führen auf externe Tochterdomains ohne Rückweg | hoch | `leistungen.md`, Z. 76, 96 | Conversion-Leck: Leads verlassen den bbf-gruppe.com-Funnel vollständig |
| 7 | Keine Zielgruppen-getrennte Ansprache trotz genannter 3 Zielgruppen | hoch | `startseite.md`; `leistungen.md` FAQ | Unterschiedliche Kaufentscheidungslogik (privat vs. gewerblich/öffentlich) wird nicht bedient |
| 8 | 3× identische Platzhalterkarte im Referenzen-Slider | mittel | `startseite.md` Rohbefunde | Erster Eindruck im wichtigsten Trust-Bereich ist ein sichtbarer Bug |
| 9 | Keine Zertifikate/Gütesiegel, nur Partner-Logos | mittel | `startseite.md` Rohbefunde | Schwächeres Autoritätssignal als Meisterbetrieb-/ISO-Siegel bei Wettbewerbern |
| 10 | Keine Knappheits-/Dringlichkeitssignale | mittel | Ableitung aus Rohbefunden | Kein Anreiz zur zeitnahen Kontaktaufnahme, senkt Conversion der ohnehin undifferenzierten CTAs |
| 11 | 11 verschiedene E-Mail-Adressen ohne klare Zuordnungshilfe, 4 davon auf Fremddomains | mittel | `startseite.md` Standorte-Tabelle | Interessent muss selbst herausfinden, wer zuständig ist; Fremddomains wirken inkonsistent |
| 12 | Defekte/falsche Google-Maps-Links an 4 Standorten | mittel | `startseite.md` Standorte-Tabelle | Erschwert physisches Aufsuchen, schlechte UX bei lokalen Anfragen |
| 13 | Gesellschafter-Sympathiefaktor (Zitate) durch Bild-Inkonsistenz geschwächt (1 Person, 5 Rollen, 3 Fotos) | niedrig | `startseite.md` Rohbefunde | Kleiner, aber sichtbarer Authentizitäts-Bruch bei sonst positivem Element |
| 14 | Datenlücke: `referenzen.md`, `kontakt.md`, `ueber-uns.md` nicht verfügbar | Lücke | – | Formular-UX, Reaktionszeitversprechen und vollständige Referenzdetails konnten nicht bewertet werden – vor Kundenpräsentation nachziehen |

---

## 7. Drei Killer-Argumente für den Vertriebstermin

1. **„Sie haben mehr Vertrauens-Kapital als jeder Wettbewerber – und verschenken es."** BBF referenziert Schloss Sanssouci, das Pergamonmuseum, den Flughafen Tempelhof und das Europäische Patentamt – rund 70 Referenzprojekte insgesamt. Kein einziger der vier analysierten Wettbewerber (Wörpel Bau, E.L.I.A., Z-Geschossbau, BATEG) hat vergleichbar prominente Referenzen vorzuweisen. Trotzdem werden diese Projekte als bloße Flächenkärtchen dargestellt – teils mit leeren Feldern, teils (im Slider) als dreifach identische Platzhalterkarte. Der direkte Wettbewerber E.L.I.A. gewinnt mit Adresse, m² und Bauzeit pro Projekt strukturell mehr Vertrauen aus schwächerer Substanz.

2. **„0 Google-Bewertungen bei 350 Mitarbeitern und 8 Standorten."** Für ein Unternehmen dieser Größenordnung ist die Kundenbewertungslage praktisch nicht vorhanden – während der einzige Drittanbieter-Inhalt, der bei der Marken-Suche rankt, ein Scoredex-„Faktencheck" ist, der Interessenten explizit zur Vorsicht vor Vertragsabschluss rät. Bei einer Investitionsentscheidung dieser Größenordnung (Generalunternehmer-Beauftragung) ist Social Proof der stärkste Hebel, den die Website aktuell komplett ungenutzt lässt.

3. **„Der eigene 'Leistungsübersicht'-Button beweist das Problem in einem Klick."** Der Button „Zu unserer Leistungsübersicht" verlinkt fälschlich auf das Kontaktformular statt auf die Leistungsseite – ein sofort nachvollziehbarer, konkreter Beweis dafür, dass der Funnel nicht durchdacht ist. Kombiniert mit fünf identischen „Jetzt kontaktieren"-Buttons ohne jede Unterscheidung zwischen privatem Bauherrn, gewerblichem Investor und öffentlichem Auftraggeber lässt sich in der Präsentation live zeigen, wie viel Conversion-Potenzial durch simple Funnel-Logik gehoben werden kann – unabhängig von Traffic-Wachstum.

---

## Zusammenfassung (5 Punkte)

1. **Größter Hebel – Social Proof fehlt komplett:** Bei ~350 Mitarbeitern und 8 Standorten gibt es keine auffindbaren Kundenbewertungen; der einzige prominente Drittinhalt rät zur Vorsicht vor Vertragsabschluss. Für eine GU-Entscheidung mit hohem Investitionsvolumen ist das der kritischste Trust-Gap.
2. **CTA-Funnel ist undifferenziert und teils defekt:** Fünf identische „Jetzt kontaktieren"-Buttons ohne Zielgruppen-/Funnel-Logik, plus ein konkreter Bug (Leistungsübersicht-Button verlinkt auf Kontakt statt Leistungen) und Conversion-Lecks über externe „Mehr erfahren"-Links zu Tochterdomains.
3. **Referenzen sind das ungenutzteste Asset:** ~70 Projekte inklusive Weltklasse-Namen (Sanssouci, Pergamonmuseum, Tempelhof) werden als reine Flächenkärtchen ohne Story, Kundenzitat oder Ergebnis präsentiert – teils mit leeren Feldern und einer dreifach duplizierten Platzhalterkarte im Slider.
4. **Autorität vorhanden, aber durch Inkonsistenz geschwächt:** Starke Kennzahlen (30 Jahre, 8 Standorte, 350 MA) verlieren an Glaubwürdigkeit, weil sich Standort-, Mitarbeiter- und Jahreszahlen je nach Unterseite widersprechen – ein direkter Widerspruch zur eigenen Botschaft „Verlässlichkeit".
5. **Kontaktaufnahme ist unnötig reibungsbehaftet:** Elf verschiedene E-Mail-Adressen (teils auf Fremddomains), defekte Maps-Links an vier Standorten und der fehlende CTA-Zwischenschritt „kostenloses Erstgespräch" erschweren den ersten Schritt – Formular-UX selbst konnte mangels `kontakt.md` nicht geprüft werden und sollte vor der Endpräsentation nachgezogen werden.
