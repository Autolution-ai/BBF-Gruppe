# Analyse-Dimension: SEO (Technik & Content) – bbf-gruppe.com

**Stand:** 15.07.2026 · Erstellt für Vertriebstermin (Webdesign-Agentur)

**Beleglage & Kennzeichnung:**
- **[direkt belegt]** = eigene Sichtung der gecrawlten Seiten (`daten/crawl/startseite.md`, `leistungen.md`, `leistungen_hochbau.md`) oder dokumentierte Recherche aus `daten/recherche/serp-wettbewerber.md`.
- **[indirekt ermittelt]** = bbf-gruppe.com war netzwerkseitig nicht direkt per curl/WebFetch abrufbar; Aussagen zu Meta-Daten, hreflang, URL-Struktur stammen aus indexierten SERP-Snippets und Title-Tags, nicht aus dem Quelltext selbst.
- **Wichtige Lücke:** `daten/crawl/technical-head-analyse.md` (Detailanalyse von Meta-Tags/Canonical/hreflang-Matrix/JSON-LD/robots.txt/Sitemap durch einen parallel arbeitenden Agenten), sowie `referenzen.md`, `kontakt.md` und `ueber-uns.md` lagen zum Zeitpunkt der Erstellung dieser Analyse **noch nicht vor** (geprüft, nicht vorhanden). Diese Dimension basiert daher auf den vier zugesicherten Kernquellen; alle technischen Aussagen zu Meta/hreflang/JSON-LD sind entsprechend als **indirekt ermittelt** gekennzeichnet und sollten vor dem Termin – sofern die Datei inzwischen erschienen ist – gegengeprüft werden.

---

## 1. SERP-Sichtbarkeit Status quo

**Kernbefund [direkt belegt, serp-wettbewerber.md Abschnitt 1]:** Bei **6 von 7 geschäftsrelevanten Such­begriffen** ist bbf-gruppe.com in den Top 10 nicht auffindbar:

| Keyword | Status | Wer dominiert stattdessen |
|---|---|---|
| Generalunternehmer Berlin | Nein | Wörpel Bau (Platz 1, nur ~30 MA), so-innenausbau.de, E.L.I.A., Z-Geschossbau, MBN, residir, BATEG, AMA BAU |
| Generalunternehmer Brandenburg | **Ja – einziger Treffer**, aber die **englische** Startseite `/en` (~Platz 4) | E.L.I.A. (Platz 1), extrageneralunternehmen.de, Z-Geschossbau mit dedizierter Brandenburg-Landingpage |
| Projektentwickler Berlin | Nein | Verzeichnisse (digitale.immobilien, listenchampion.de), Berliner Jungens, PRIMUS Immobilien |
| Bauunternehmen Berlin Brandenburg | Nein | Wörpel Bau (Platz 1), Katro Bau, Legio Bau, Gelbe Seiten |
| schlüsselfertig bauen Berlin | Nein | Elemente Spezialbau, Asmo Bau, Klinkerhaus, GGV Bau – auffällig viele dedizierte Leistungs-Landingpages |
| Hochbau Tiefbau Berlin | Nein (obwohl Kernleistung!) | Bleck & Söhne, TLB Bau, Wadhwa Estate, HTPS |
| BBF Gruppe (Brand) | **Ja, Platz 1 – aber die /en-Version** | Danach: LinkedIn, **bbfgruppe.de = Fahrzeugfolierer Karlsruhe (Platz 3!)**, Instagram, **bbf-gruppe.de = Immobiliengruppe Köln (Platz 5!)**, Scoredex-„Faktencheck" |

Zwei Muster stechen heraus:
1. **Sprachversions-Problem:** Die einzigen zwei Treffer überhaupt (generisches Keyword + Brand) laufen beide auf `/en` statt `/de` – ein klares hreflang-/Canonical-Signal, kein Long-Tail-Sichtbarkeitsproblem.
2. **Brand-Kaperung:** Bei der eigenen Firmennamen-Suche verdrängen zwei branchenfremde bzw. -ähnliche Namensvetter (Fahrzeugfolierer Karlsruhe, Immobilienfirma Köln) die BBF Gruppe von Platz 3 und 5 – ein Interessent, der „BBF Gruppe" googelt, landet mit hoher Wahrscheinlichkeit zuerst bei einem fremden Unternehmen.

**Einordnung:** Alle sechs unsichtbaren Keywords werden von Wettbewerbern dominiert, die BBF an Substanz (Mitarbeiterzahl, Standorte, Referenzportfolio wie Sanssouci/Pergamonmuseum/Flughafen Tempelhof laut startseite.md) unterlegen sind – z. B. Wörpel Bau mit nur ca. 30 Mitarbeitenden gegen BBFs ~350. Das Problem ist nicht mangelnde Substanz, sondern fehlende SEO-Architektur (siehe Abschnitt 4).

---

## 2. Technische SEO-Befunde

**Hinweis:** `technical-head-analyse.md` lag nicht vor (geprüft, s. o.). Die folgenden Befunde sind daher **indirekt ermittelt** aus SERP-Snippets/Title-Tags (`serp-wettbewerber.md` Abschnitt 3) sowie **direkt belegt** aus den strukturellen Auffälligkeiten der gecrawlten Seiten selbst.

### 2.1 hreflang / Internationalisierung [indirekt ermittelt]
- Deutsche Suchanfragen liefern die **englische** Startseite (`/en`, Title „Project Developer & General Contractor in Berlin and Brandenburg") statt der deutschen (`/`, Title „Projektentwickler & Generalunternehmen in Berlin und Brandenburg"). Das ist ein starkes Indiz für fehlendes oder fehlerhaftes `hreflang`/`x-default` bzw. eine falsche kanonische Zuordnung.
- **Sprachmix-URLs:** `/en/leistungen/building-construction`, `/en/leistungen/civil-engineering`, `/en/leistungen/garden-landscape-construction`, `/en/leistungen/scaffolding` – deutscher Ordnername „leistungen" kombiniert mit englischen Slugs. `/en/firmenuebernahme` nutzt sogar einen komplett deutschen Slug unter `/en`. Das erschwert Suchmaschinen die eindeutige Sprachzuordnung zusätzlich.
- **Doppelte Karriereseiten:** `/en/karriere` (Title „Career") **und** `/en/career/` (Title „Mach Karriere bei der BBF Gruppe" – deutscher Titel unter der englischen URL) sind beide indexiert. Klassischer Duplicate-Content-Kandidat ohne erkennbare Canonical-Steuerung.

### 2.2 Paginierung & URL-Hygiene [indirekt ermittelt]
- `/en/aktuelles?dc9752be_page=3` ist mit Parameter indexiert – ein typischer Webflow-CMS-Paginierungsparameter. Ohne `rel=canonical` auf die Basis-URL oder Parameter-Handling in der Search Console entstehen hier potenziell viele near-duplicate Indexeinträge im News-Bereich.
- **Umlaut-Transliteration inkonsistent:** `/referenzen/grunheide-locknitztal` verwendet „grunheide" statt „gruenheide" – uneinheitliche URL-Konventionen deuten auf fehlende Slug-Governance beim CMS-Setup hin.

### 2.3 Duplicate Content durch Relaunch-Altlasten [direkt belegt aus serp-wettbewerber.md]
Die alte Seitenstruktur `/unternehmensgruppe/bbf-bau-gmbh/…` ist **parallel** zur neuen `/leistungen/…`-Struktur indexiert – identische Themen, zwei URLs:

| Alt-URL (indexiert) | Neue URL (heute aktiv, laut leistungen.md) |
|---|---|
| `/unternehmensgruppe/bbf-bau-gmbh/tiefbau/` | `/leistungen/tiefbau` |
| `/unternehmensgruppe/bbf-bau-gmbh/hochbau/` | `/leistungen/hochbau` |
| `/unternehmensgruppe/bbf-bau-gmbh/gebaeudetechnik/elektro/` | `/leistungen/gebaeudetechnik-elektro` |

Ohne 301-Redirect oder Canonical-Tag konkurrieren beide URL-Familien um dieselben Rankingsignale – ein klassischer Relaunch-Fehler, der Linkkraft und Crawl-Budget verwässert.

### 2.4 Strukturierte Daten (JSON-LD) [indirekt ermittelt, geringe Konfidenz]
- Direkter Quelltext-Check war nicht möglich. Indiz: In keinem der SERP-Snippets aus `serp-wettbewerber.md` sind Rich-Result-Elemente sichtbar (keine Sternebewertungen, keine FAQ-Akkordeon-Snippets, kein Sitelinks-Suchfeld, kein Knowledge Panel – letzteres auch beim Brand-Keyword nicht, obwohl BBF dort Platz 1 belegt).
- Die `/leistungen`- und `/leistungen/hochbau`-Seiten enthalten inhaltlich ein FAQ-Format (Akkordeon mit 6–7 Fragen je Seite, siehe Abschnitt 3) – **ideales Rohmaterial für FAQPage-Schema**, das aber offenbar nicht in Rich Results resultiert. Ob das Markup fehlt oder nur nicht ausgespielt wird, kann ohne Quelltext nicht abschließend geklärt werden – **klare Prüf-Empfehlung für die technische Nachanalyse**.
- Ebenso kein erkennbares `Organization`/`LocalBusiness`-Schema ableitbar (kein Knowledge Panel bei „BBF Gruppe" trotz Platz-1-Ranking der eigenen Domain – ungewöhnlich, wenn Entity-Markup vorhanden wäre).

### 2.5 robots.txt / Sitemap [keine Aussage möglich]
Ohne `technical-head-analyse.md` und ohne direkten Zugriff liegen **keine verifizierbaren Daten** zu robots.txt-Regeln oder XML-Sitemap-Abdeckung vor. Aus der Tatsache, dass sowohl `/en/*`- als auch `/unternehmensgruppe/*`-Altlasten indexiert sind, lässt sich indirekt schließen, dass die Sitemap (falls vorhanden) diese Alt-URLs entweder noch listet oder dass kein Deindexierungsprozess (noindex/410/301) für obsolete Pfade existiert. **Als Lücke vermerkt – vor dem Termin idealerweise nachreichen, sobald die technische Analyse vorliegt.**

### 2.6 On-Page-Markenschreibweise [direkt belegt]
Title-Tags mischen „BBF Gruppe" und „BBF-Gruppe" (z. B. `leistungen.md`: „Leistungen | **BBF-Gruppe**" vs. Homepage-Snippet „… | **BBF Gruppe**"). Kleinigkeit, aber ein Signal für fehlende Content-Governance, das sich durch alle Dimensionen zieht (vgl. auch die Fakten-Inkonsistenzen in Abschnitt 5).

---

## 3. Content-Tiefe & Struktur

### 3.1 `/leistungen` – Übersichtsseite [direkt belegt]
- Title: „Leistungen | BBF-Gruppe"; Meta-Description nennt „Hochbau, Tiefbau, GaLa Bau, Gerüstbau, Gebäudetechnik" und „seit 30 Jahren in der Region Berlin und Brandenburg" – solide Grundausstattung für eine Übersichtsseite.
- **Struktur:** 9 Leistungsblöcke (Planung, Vermessung, Projektentwicklung, Tiefbau, Hochbau, Elektrotechnik, Gebäudetechnik, GaLaBau, Gerüstbau) als Anker-Sprungmarken auf **einer einzigen URL** (`/leistungen#tiefbau` etc.), je Block ~40–90 Wörter Fließtext plus teils Bullet-Liste.
- **Kritischer Befund – externe Linkleaks:** Von den 9 „Mehr erfahren"-Buttons verlinken **zwei auf fremde Domains statt auf eigene Unterseiten**: Planung → `https://www.plant-plant.de/` (Tochterfirma plant Hey Dahlke Meurer Planungsgesellschaft mbH), Vermessung → `https://www.plan3d-berlin.de/` (Tochterfirma Plan3D Laserscan+Modell GmbH). Das bedeutet: **Für zwei von neun Kernleistungen existiert überhaupt keine indexierbare, keyword-optimierte Seite auf bbf-gruppe.com selbst** – Sucht­interesse zu „Bauplanung Berlin" oder „Vermessung Berlin" kann die Hauptdomain gar nicht bedienen, und der Linkjuice fließt aktiv nach außen ab (deckt sich mit der in `serp-wettbewerber.md` beschriebenen Domain-Zersplitterung).
- Die übrigen 7 Leistungen verlinken korrekt intern (`/bbf-projekt`, `/leistungen/tiefbau`, `/leistungen/hochbau`, `/leistungen/gebaeudetechnik-elektro`, `/leistungen/gebaeudetechnik-hls`, `/leistungen/garten-und-landschaftsbau`, `/leistungen/geruestbau`).
- **Widerspruch zur Startseiten-Navigation:** Laut `startseite.md` verlinkt das Hauptmenü-Grid „Planen, bauen und betreuen" die Positionen 07 Gerüstbau, 08 Vermessung, 09 Planung nur pauschal auf `/leistungen` (keine Tiefenverlinkung), obwohl für Gerüstbau tatsächlich eine eigene Unterseite (`/leistungen/geruestbau`) existiert. Die interne Verlinkung von der Homepage – der stärksten Seite der Domain – zu dieser Unterseite fehlt also, was ihr PageRank-technisch schadet.
- **Bug mit SEO-Relevanz:** Der Button „Zu unserer Leistungsübersicht" auf der Startseite verlinkt fälschlich auf `/kontakt` statt auf `/leistungen` (laut `startseite.md`) – ein defekter interner Link an prominenter Stelle, der Crawlbarkeit und Nutzerführung zur wichtigsten Content-Hub-Seite behindert.
- FAQ-Akkordeon mit 6 Fragen vorhanden (gutes Rohmaterial für Featured Snippets/FAQPage-Schema, siehe 2.4).

### 3.2 `/leistungen/hochbau` – Beispiel Unterseite [direkt belegt]
- Title: „Hochbau | BBF Gruppe", H1 „Hochbau in Berlin & Brandenburg" (gutes, regional verankertes Haupt-Keyword im H1), Meta-Description mit Leistungsaufzählung – sauberes On-Page-Grundgerüst.
- **Struktur:** Intro-Absatz (~70 Wörter) → 8 „Fachgebiete"-Blöcke (Schlüsselfertiges Bauen, Rohbau, Innenausbau, Fenster, Fassaden, Dacharbeiten, Sanierung, Schlosserarbeiten; je 15–40 Wörter) → 5 USP-Kacheln → ca. 20 Referenzkarten (überwiegend nur Projektname + m²-Angaben, keine Fließtext-Story) → FAQ mit 7 Fragen.
- **Geschätzter unique Fließtext** (ohne Bildunterschriften/Referenzkarten-Labels): ca. 500–600 Wörter – für eine Kernleistungsseite eines 350-Mitarbeiter-Generalunternehmens **dünn** im Vergleich zur Wettbewerber-Blaupause (siehe 3.3).
- **Content-Qualitätsmangel:** Alle 8 „Fachgebiete"-Blöcke sind identisch mit „01" nummeriert statt fortlaufend „01–08" – ein Template-/CMS-Fehler, der auch semantisch (Accessibility, ggf. strukturierte Daten) unsauber ist.
- Referenzkarten wiederholen dieselbe „MITTENWALDE (HOCHBAU)"-Karte zweimal identisch direkt hintereinander (Platzhalter-Duplizierung, deckt sich mit dem auf der Startseite dokumentierten 3×-Slider-Duplikat).
- Positiv: Die Referenzliste selbst ist beeindruckend (Schloss Sanssouci, Pergamonmuseum, Bauhaus Dessau, Flughafen Tempelhof, Europäisches Patentamt, ADAC Fahrsicherheitszentrum) – **Substanz ist da, wird aber nicht suchmaschinen- oder nutzergerecht als Story aufbereitet** (keine „Herausforderung → Lösung"-Texte, viele Karten mit leeren „Grundstück:"/„Nutzfläche:"-Feldern).

### 3.3 Vergleich zur Wettbewerber-Blaupause [direkt belegt, serp-wettbewerber.md]
| Wettbewerber | SEO-Content-Muster | BBF-Gegenstück heute |
|---|---|---|
| **Z-Geschossbau** | Dedizierte Region-Landingpages (`/generalunternehmer-berlin`, `/generalunternehmer-brandenburg`, `/generalunternehmer-sachsen`) + Leistung×Region-Kombiseiten (`/leistungen/hallenbau/brandenburg`) – ranken beide in Top 10 | Keine einzige Regional-Landingpage; Standort-Inhalte laut serp-wettbewerber.md nur als News-Artikel (z. B. „Standort Mittenwalde") |
| **E.L.I.A.** | Keyword-exakte Title-Tags je Kernleistungsseite („Generalunternehmer für Neubauprojekte in Berlin & Brandenburg") | BBFs Titles sind funktional, aber teils inkonsistent geschrieben (BBF-Gruppe/BBF Gruppe) und nicht in gleicher Keyword-Schärfe |
| **Wörpel Bau** | Gewerke-Ebene-URLs (`/leistungen-generalunternehmen/heizung-sanitaer/`), „über 5.000 Bauvorhaben seit 1997" als Vertrauensbeweis | BBF hat Gebäudetechnik nur in zwei Blöcke (Elektro/HLS) gegliedert, keine tiefere Gewerke-Aufsplittung; keine vergleichbare Kennzahlen-Aussage auf Leistungsseiten |
| **BATEG** | Referenzen nach Kategorien strukturiert (Wohnungsbau, realisierte Projekte), eigene Ansprechpartner-Seite, News-Bereich | BBF-Referenzen sind eine unstrukturierte Kartenliste ohne Kategorien/Story; News-Bereich existiert und ist aktiv, aber laut serp-wettbewerber.md nicht als SEO-Hub ausgebaut |

**Fazit Abschnitt 3:** BBF hat auf den geprüften Seiten grundsätzlich sauberes, thematisch relevantes Basismaterial (funktionierende H1/Title/Meta, FAQ-Blöcke, starke Referenzliste), aber die Content-Tiefe pro Thema bleibt deutlich hinter der Wettbewerber-Blaupause zurück, und zwei von neun Kernleistungen (Planung, Vermessung) haben **auf der Hauptdomain gar keine eigene Seite**, sondern verweisen aktiv nach extern.

---

## 4. Fehlende Seitenarchitektur

Abgleich mit der offenen Wettbewerber-Blaupause (`serp-wettbewerber.md` Abschnitt 2/5) und den strukturellen Lücken aus `startseite.md`/`leistungen.md`:

1. **Keine Standort-/Regional-Landingpages** – laut `startseite.md` existieren 8 Standorte (Berlin-Adlershof, Berlin Soldiner Str., Mittenwalde, Grünheide, Luckau u. a.), aber keine einzige dedizierte, indexierbare Standortseite; Standort-Inhalte stecken nur in News-Artikeln (`/aktuelles/standort-mittenwalde` etc., laut serp-wettbewerber.md). Z-Geschossbau zeigt mit Region-Landingpages exakt das fehlende Format.
2. **Keine Leistung×Region-Kombinationsseiten** (z. B. „Hochbau Brandenburg", „Generalunternehmer Königs Wusterhausen") – das Z-Geschossbau-Muster (`/leistungen/hallenbau/brandenburg`) fehlt komplett; genau diese Longtail-Kombinationen würden helfen, bei den aktuell 6 unsichtbaren Keywords Fuß zu fassen.
3. **Gerüstbau, Vermessung, Planung ohne vollwertige eigene Präsenz auf der Hauptdomain** – Homepage-Navigation verlinkt diese drei laut `startseite.md` nur auf `/leistungen` statt auf Tiefenseiten; und wie in Abschnitt 3.1 gezeigt, leiten „Planung" und „Vermessung" sogar aktiv auf externe Tochter-Domains (plant-plant.de, plan3d-berlin.de) weiter – dort existiert also keinerlei SEO-Fußabdruck für bbf-gruppe.com zu diesen Suchintentionen.
4. **Keine Gewerke-Ebene-Seiten** (Wörpel-Modell) – Gebäudetechnik ist nur zweistufig (Elektro/HLS) aufgeteilt, ohne weitere Unter-Landingpages (z. B. Smart Home, Blitzschutz, Heizungstechnik einzeln), obwohl die Stichpunktlisten auf `/leistungen/gebaeudetechnik-elektro`/`-hls` dafür bereits thematisches Rohmaterial liefern.
5. **Keine kategorisierten/erzählenden Referenzseiten** (BATEG-Modell) – Referenzen erscheinen laut `startseite.md` und `leistungen_hochbau.md` als reine Kartenliste ohne Kategorien, ohne Story („Herausforderung → Lösung"), teils mit leeren Datenfeldern.
6. **Keine dedizierte Karriere-Landingpage-Struktur auf der Hauptdomain** – laut serp-wettbewerber.md läuft Karriere-Traffic über mindestens 4 Domains/Subsysteme (`/karriere/jobs-bbf-bau`, `/en/karriere`, `/en/career/`, `bbf-online.com`, `karriere-bbf-online.com`, 2× Personio-Subdomains) statt über eine konsolidierte, SEO-starke Sektion.

---

## 5. Duplicate Content & Relaunch-Altlasten

- **Alte URL-Struktur `/unternehmensgruppe/bbf-bau-gmbh/…` ist weiterhin indexiert und inhaltlich deckungsgleich mit der neuen `/leistungen/…`-Struktur** [direkt belegt, serp-wettbewerber.md Abschnitt 3.1]: `/unternehmensgruppe/bbf-bau-gmbh/tiefbau/` vs. `/leistungen/tiefbau`, `/unternehmensgruppe/bbf-bau-gmbh/hochbau/` vs. `/leistungen/hochbau`, `/unternehmensgruppe/bbf-bau-gmbh/gebaeudetechnik/elektro/` vs. `/leistungen/gebaeudetechnik-elektro`.
- Ohne erkennbare 301-Redirects konkurrieren beide Versionen um dieselben Rankingsignale (Linkkraft-Verwässerung, Crawl-Budget-Verschwendung, Risiko von Google-eigener „bester Kandidat"-Auswahl, die nicht zwingend die gewünschte neue URL trifft).
- Zusätzlich doppelte Karriereseiten (`/en/karriere` vs. `/en/career/`, siehe 2.1) als weiteres Duplicate-Content-Muster aus demselben Relaunch.
- **Business-Kontext:** Dies ist typisch für einen CMS-Wechsel (die Bild-URLs in `leistungen.md`/`leistungen_hochbau.md` zeigen `cdn.prod.website-files.com` – d. h. **Webflow** als aktuelles CMS) ohne sauberes Redirect-Mapping der Altstruktur.

---

## 6. Findings-Tabelle

| # | Finding | Schweregrad | Beleg | Business-Impact |
|---|---|---|---|---|
| 1 | Bei 6 von 7 Kern-Keywords nicht in Top 10 – deutlich kleinere Wettbewerber (Wörpel Bau ~30 MA) dominieren trotz BBFs ~350 MA und starkem Referenzportfolio | **kritisch** | serp-wettbewerber.md Abschnitt 1 [direkt belegt] | Organische Leadgenerierung läuft praktisch komplett an BBF vorbei |
| 2 | Englische Startseite (`/en`) rankt statt der deutschen bei deutschen Suchanfragen (Brand + „Generalunternehmer Brandenburg") | **kritisch** | serp-wettbewerber.md Abschnitt 1/3 [direkt belegt/indirekt ermittelt] | Deutschsprachige Interessenten sehen einen englischen Titel/Snippet – Vertrauensverlust im ersten Suchergebnis-Moment |
| 3 | Brand-SERP fremdbesetzt: Fahrzeugfolierer Karlsruhe (Platz 3) und Immobilienfirma Köln (Platz 5) ranken bei „BBF Gruppe" vor eigenen Unterseiten | **kritisch** | serp-wettbewerber.md Abschnitt 1 [direkt belegt] | Eigene Firmennamen-Suche führt Interessenten zu fremden Unternehmen |
| 4 | Für 2 von 9 Kernleistungen (Planung, Vermessung) existiert keine eigene Seite auf bbf-gruppe.com; „Mehr erfahren" verlinkt aktiv auf externe Tochter-Domains (plant-plant.de, plan3d-berlin.de) | **hoch** | leistungen.md [direkt belegt] | Keine Rankingchance für „Bauplanung"/„Vermessung Berlin"-Suchen auf der Hauptdomain; Linkjuice fließt ab |
| 5 | Alte `/unternehmensgruppe/bbf-bau-gmbh/…`-Struktur parallel zu `/leistungen/…` indexiert (Duplicate Content, kein erkennbarer Redirect) | **hoch** | serp-wettbewerber.md Abschnitt 3.1 [direkt belegt] | Verwässerte Rankingsignale, Crawl-Budget-Verschwendung, Risiko falscher Google-Kanonisierung |
| 6 | Doppelte Karriereseiten (`/en/karriere` + `/en/career/`) sowie indexierte Paginierungs-Parameter (`?dc9752be_page=3`) ohne erkennbare Kanonisierung | **mittel** | serp-wettbewerber.md Abschnitt 3.1 [indirekt ermittelt] | Weitere Duplicate-Content-/Indexqualitäts-Probleme, typisch für ungepflegtes Webflow-CMS |
| 7 | Sprachmix-URLs (`/en/leistungen/building-construction`, `/en/firmenuebernahme`) erschweren Sprachzuordnung zusätzlich zum hreflang-Problem | **mittel** | serp-wettbewerber.md Abschnitt 3.1 [indirekt ermittelt] | Verstärkt das Grundproblem aus Finding 2 strukturell |
| 8 | Homepage-Navigation verlinkt Gerüstbau/Vermessung/Planung nur pauschal auf `/leistungen`, nicht auf Tiefenseiten; zusätzlich verlinkt der Button „Zu unserer Leistungsübersicht" fälschlich auf `/kontakt` statt `/leistungen` | **hoch** | startseite.md [direkt belegt] | Schwache interne Verlinkung von der stärksten Seite der Domain zu Leistungsseiten – verschenktes internes PageRank-Potenzial, dazu ein defekter CTA-Link |
| 9 | Content-Tiefe pro Leistungsseite dünn (~500–600 Wörter unique Text auf `/leistungen/hochbau`) im Vergleich zur Wettbewerber-Blaupause (Gewerke-Ebene-Seiten, Region-Landingpages) | **hoch** | leistungen_hochbau.md vs. serp-wettbewerber.md Abschnitt 2 [direkt belegt] | Zu wenig Content-Substanz, um gegen spezialisierte Wettbewerber-Landingpages zu ranken |
| 10 | Keine Standort-/Regional-Landingpages und keine Leistung×Region-Kombiseiten (Z-Geschossbau-Blaupause fehlt komplett) | **kritisch** | serp-wettbewerber.md Abschnitt 2.3 [direkt belegt] | Größte einzelne Sichtbarkeitslücke – genau das Format, das bei Wettbewerbern in Top 10 rankt |
| 11 | Referenzen als unstrukturierte Kartenliste ohne Kategorien/Story, teils leere Datenfelder, dupliziertes Platzhalter-Beispiel | **mittel** | leistungen_hochbau.md, startseite.md [direkt belegt] | Starke Projektsubstanz (Sanssouci, Pergamonmuseum etc.) wird content-seitig verschenkt |
| 12 | Keine erkennbaren Rich Results (keine FAQ-Snippets trotz vorhandener FAQ-Blöcke, kein Knowledge Panel trotz Platz-1-Brand-Ranking) | **mittel** | serp-wettbewerber.md-Snippets [indirekt ermittelt, geringe Konfidenz] | Deutet auf fehlendes/unvollständiges strukturiertes Daten-Markup hin – vor Termin technisch nachprüfen |
| 13 | Inkonsistente Markenschreibweise „BBF Gruppe" vs. „BBF-Gruppe" in Title-Tags; Umlaut-Transliteration uneinheitlich (`grunheide` statt `gruenheide`) | **mittel** | leistungen.md, serp-wettbewerber.md [direkt belegt] | Kleines, aber sichtbares Signal für fehlende Content-Governance |
| 14 | robots.txt/Sitemap-Status nicht verifizierbar; Altlasten (Punkt 5) deuten auf fehlendes Deindexierungs-Management hin | **hoch** | keine Primärquelle vorhanden [Lücke – ohne technical-head-analyse.md nicht abschließend belegbar] | Unklar, ob Google überhaupt korrekt gesteuert wird – zentrale offene Frage für die technische Tiefenprüfung |

---

## 7. Priorisierte SEO-Roadmap

### Phase 1 – Technische Quick Wins (Aufwand S, Wochen 1–4)
1. **Broken-CTA-Fix:** Button „Zu unserer Leistungsübersicht" von `/kontakt` auf `/leistungen` korrigieren (Finding 8) – **S**
2. **hreflang/x-default korrekt setzen**, damit deutsche Suchanfragen die deutsche Startseite ausspielen (Finding 2) – **S–M**
3. **301-Redirects der Altstruktur:** `/unternehmensgruppe/bbf-bau-gmbh/*` auf die passenden `/leistungen/*`-URLs umleiten (Finding 5) – **S–M**
4. **Karriereseiten konsolidieren:** `/en/karriere` vs. `/en/career/` zusammenführen oder redirecten (Finding 6) – **S**
5. **Paginierungs-Parameter kanonisieren/deindexieren** (`?dc9752be_page=3`) (Finding 6) – **S**
6. **Markenschreibweise vereinheitlichen** („BBF Gruppe" konsequent) und Umlaut-Slugs korrigieren (Finding 13) – **S**

### Phase 2 – Content- & Architektur-Ausbau (Aufwand M, Monate 2–4)
7. **Eigene Landingpages für Planung und Vermessung** auf bbf-gruppe.com statt externer Weiterleitung zu plant-plant.de/plan3d-berlin.de bauen; interne Verlinkung von der Homepage auf alle 9 Leistungen inkl. Gerüstbau vervollständigen (Finding 4, 8) – **M**
8. **Content-Tiefe je Leistungsseite erhöhen** (Gewerke-Unterseiten nach Wörpel-Vorbild, mehr Fließtext, Kennzahlen-Beweise wie „X Projekte seit Y Jahren") (Finding 9) – **M**
9. **Referenzen neu strukturieren:** Kategorien (Hochbau/Tiefbau/GaLaBau/…) + Story-Format „Herausforderung → Lösung → Ergebnis" statt reiner Kartenliste, leere Datenfelder auffüllen (Finding 11) – **M**
10. **FAQ-Content in FAQPage-Schema überführen** (JSON-LD), sobald technisch verifiziert ist, dass es fehlt (Finding 12) – **S–M**

### Phase 3 – Strategische SEO-Architektur (Aufwand L, Monate 3–8)
11. **Standort-/Regional-Landingpages** je Standort (Berlin, Mittenwalde, Grünheide, Luckau, Königs Wusterhausen-Region etc.) nach Z-Geschossbau-Vorbild aufbauen (Finding 10) – **L** *(überschneidet sich mit Maßnahme „Standort-Landingpages" aus der GEO/Lokal-Dimension – gemeinsam umsetzbar)*
12. **Leistung×Region-Kombinationsseiten** programmatisch anlegen (z. B. „Hochbau Brandenburg", „Generalunternehmer Königs Wusterhausen") (Finding 10) – **L**
13. **Technische Vollprüfung nachholen**, sobald verfügbar: robots.txt, XML-Sitemap-Abdeckung, vollständige hreflang-Matrix, JSON-LD-Audit (Finding 12, 14) – **M–L**, aber **Voraussetzung**, um Phase-1-Maßnahmen zu validieren

---

## 8. Drei Killer-Argumente für den Vertriebstermin

1. **„Sie sind der substanzstärkste Anbieter der Region – aber bei 6 von 7 wichtigen Suchbegriffen unsichtbar."** Ein Wettbewerber mit nur ca. 30 Mitarbeitenden (Wörpel Bau) belegt Platz 1 bei „Generalunternehmer Berlin", während BBF mit ~350 Mitarbeitenden, 8 Standorten und Referenzen wie Schloss Sanssouci, Pergamonmuseum und dem Flughafen Tempelhof dort komplett fehlt. Das ist kein Substanzproblem, sondern ein reines Architektur- und Sichtbarkeitsproblem – und genau deshalb lösbar.

2. **„Ihre eigene Website zeigt deutschen Kunden die englische Startseite.“** Bei der Suche nach dem eigenen Firmennamen „BBF Gruppe" UND beim einzigen relevanten Sichtbarkeits-Treffer „Generalunternehmer Brandenburg" rankt jeweils `bbf-gruppe.com/en` mit englischem Titel – nicht die deutsche Seite. Das lässt sich mit einer sauberen hreflang-Konfiguration technisch schnell beheben (Quick Win mit kurzfristig sichtbarem Effekt) und ist ein greifbarer, leicht demonstrierbarer Beweis dafür, wie viel ungenutztes Potenzial bereits im Bestand steckt.

3. **„Wer heute ‚BBF Gruppe' googelt, landet eher bei einem Fahrzeugfolierer aus Karlsruhe oder einer Immobilienfirma aus Köln als bei Ihnen.“** Zwei namensfremde bzw. -ähnliche Unternehmen belegen die Plätze 3 und 5 der eigenen Markensuche – noch vor mehreren eigenen Unterseiten. Kombiniert mit fehlendem Knowledge Panel und fehlenden strukturierten Daten zeigt das: Selbst der einfachste Suchvorgang – der eigene Firmenname – ist heute nicht unter Kontrolle. Genau hier lässt sich mit überschaubarem Aufwand (Redirects, Konsolidierung, Schema-Markup) schnell sichtbarer Fortschritt erzielen.

---

## Offene Punkte für die technische Nachanalyse

Sobald `daten/crawl/technical-head-analyse.md` (und ergänzend `referenzen.md`, `kontakt.md`, `ueber-uns.md`) vorliegen, sollten insbesondere folgende in dieser Analyse nur indirekt belegte Punkte verifiziert werden: vollständige hreflang-Matrix, Canonical-Tags auf den Altlasten-URLs, tatsächliches Vorhandensein/Fehlen von JSON-LD (Organization/LocalBusiness/FAQPage), robots.txt-Regeln und XML-Sitemap-Abdeckung (Finding 12, 14).
