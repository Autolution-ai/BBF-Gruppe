# bbf-gruppe.com – Tiefenanalyse für den Vertriebstermin

**Kunde:** BBF Gruppe (Berlin Brandenburg Firmen Gruppe) – Projektentwickler & Generalunternehmer, ca. 350 Mitarbeiter, 7–8 Standorte Berlin/Brandenburg
**Erstellt:** 15.07.2026 · Webdesign-Agentur, Vorbereitung Settingtermin
**Dimensionen:** Design & UX · Verkaufspsychologie & Conversion · SEO (Technik & Content) · GEO & Lokale Sichtbarkeit

**Methodik-Hinweis:** Direkter Live-Zugriff auf bbf-gruppe.com war in der Analyseumgebung netzwerkseitig gesperrt. Alle Inhaltsbefunde basieren auf vollständig über Apify gecrawltem Seiteninhalt (Startseite, Leistungsübersicht, Hochbau, Referenzen, Kontakt, Über uns), ergänzt um umfangreiche SERP-/Wettbewerber- und Reputations-Recherche. Screenshots und Lighthouse-Messungen (Ladezeiten, Core Web Vitals) waren nicht möglich – die Design-Analyse ist code-/inhaltsbasiert, keine visuelle Prüfung. Jede Aussage in diesem Report ist in den vier Detail-Dokumenten (`analyse/dimension-*.md`) mit Quelle belegt.

---

## Executive Summary

BBF Gruppe hat mehr **Substanz** als jeder in der Recherche gefundene Wettbewerber: ~350 Mitarbeiter, 8 Standorte, über 70 Referenzprojekte – darunter Schloss Sanssouci, das Pergamonmuseum, den Flughafen Tempelhof und das Europäische Patentamt. Trotzdem ist die Website bei **6 von 7 zentralen Suchbegriffen unsichtbar**, während Wettbewerber mit nur einem Bruchteil der Mitarbeiterzahl (z. B. Wörpel Bau, ~30 MA) die Suchergebnisse dominieren. Dieses **Substanz-Sichtbarkeits-Paradox** ist die zentrale Storyline für den Termin: Es geht nicht darum, der BBF Gruppe fehlende Kompetenz zu attestieren, sondern aufzuzeigen, dass eine überdurchschnittlich starke Firma online systematisch unter Wert verkauft wird.

**Ein roter Faden zieht sich durch alle vier Dimensionen:** widersprüchliche Basisfakten (mal 7, mal 8 Standorte; mal 200, mal 350 Mitarbeiter; mal 25, mal 30 Jahre Erfahrung) tauchen in der SEO-Analyse, der GEO-Analyse und der Verkaufspsychologie-Analyse unabhängig voneinander als Problem auf. Das ist kein Zufall, sondern ein strukturelles Content-Governance-Problem, das die Kernbotschaft „Verlässlichkeit" direkt untergräbt – und das sich mit einer „Single Source of Truth" vergleichsweise günstig beheben lässt.

**Zweiter roter Faden:** konkrete, in Sekunden im Termin vorführbare Bugs – ein Button, der Interessenten versehentlich ins Kontaktformular statt zur Leistungsübersicht schickt; zwei „Mehr erfahren"-Links, die Besucher komplett von der eigenen Website wegführen; ein Tippfehler ausgerechnet beim prestigeträchtigsten Referenzprojekt (Schloss „Sanssousi"); vier fehlerhafte Google-Maps-Standortlinks. Diese Befunde sind live demonstrierbar und machen abstrakte Aussagen wie „mangelnde Qualitätssicherung" konkret erlebbar.

---

## Scorecard je Dimension

| Dimension | Status | Kernbefund |
|---|:---:|---|
| **SEO (Technik & Content)** | 🔴 Kritisch | 6/7 Kern-Keywords unsichtbar; englische Seite rankt statt deutscher; massive Duplicate-Content-Altlast aus altem Relaunch |
| **GEO & Lokale Sichtbarkeit** | 🔴 Kritisch | Kein Standort organisch auffindbar (auch nicht der eigene Firmensitz Mittenwalde); KI-Anfragen liefern fremde Faktenchecks statt eigener Antworten |
| **Verkaufspsychologie & Conversion** | 🟠 Hoch | Kompletter Ausfall von Social Proof (0 Kundenbewertungen bei 350 MA); undifferenzierter, teils defekter CTA-Funnel |
| **Design & UX** | 🟠 Hoch | Solide Grundstruktur, aber durchgängige Sorgfaltsmängel (Tippfehler, Duplikate, tote Links, fehlende Alt-Texte) untergraben den professionellen Eindruck |

**Einordnung:** Keine der vier Dimensionen ist strukturell „kaputt" – überall ist gutes Grundmaterial vorhanden (Content, Referenzen, Kennzahlen, technische Basis). Das eigentliche Problem ist durchgängig **mangelnde Pflege und fehlende strategische Architektur**, nicht fehlende Substanz. Das ist verkaufsstrategisch der ideale Ausgangspunkt: die Agentur muss nichts neu erfinden, sondern vorhandenes Potenzial heben.

---

## Die 7 wichtigsten Findings (dimensionsübergreifend, nach Business-Impact)

| # | Finding | Dimension(en) | Live demonstrierbar? |
|---|---|---|:---:|
| 1 | **6 von 7 Geschäfts-Keywords unsichtbar** – ein 30-Mitarbeiter-Wettbewerber (Wörpel Bau) schlägt BBF bei „Generalunternehmer Berlin"; auch am eigenen Firmensitz Mittenwalde 0 Treffer | SEO, GEO | Ja (Google-Suche live) |
| 2 | **Null Kundenbewertungen** bei ~350 Mitarbeitern/8 Standorten; einziger prominenter Drittinhalt (Scoredex) rät zur Vorsicht vor Vertragsabschluss – und KI-Zusammenfassungen übernehmen genau dieses Narrativ | Verkaufspsychologie, GEO | Ja (Google-Suche „BBF Gruppe Erfahrungen") |
| 3 | **Markenverwechslung:** Zwei fremde Firmen (Immobilien Köln, Fahrzeugfolierer Karlsruhe) belegen Platz 3 und 5 bei der Suche nach dem eigenen Firmennamen | GEO, SEO | Ja (Google-Suche „BBF Gruppe") |
| 4 | **Zwei von neun Leistungs-Buttons** („Planung", „Vermessung") führen Besucher komplett von bbf-gruppe.com weg auf fremde Tochterdomains, ohne Rückweg | Verkaufspsychologie, SEO, Design | Ja (ein Klick im Termin) |
| 5 | **Fakten-Widersprüche** ziehen sich durch alle Unterseiten (7 vs. 8 Standorte, 200 vs. 350 MA, 25 vs. 30 Jahre) – untergräbt „Verlässlichkeit" als Kernbotschaft und produziert falsche KI-Firmenporträts | Alle vier | Ja (zwei Unterseiten nebeneinander zeigen) |
| 6 | **CTA-Bug:** Button „Zu unserer Leistungsübersicht" verlinkt fälschlich auf /kontakt statt /leistungen | Verkaufspsychologie, Design | Ja (ein Klick) |
| 7 | **Prestige-Referenz mit Tippfehler – auf zwei Seiten identisch:** Schloss Sanssouci wird als „Sanssousi" geführt (Startseite UND eigener Referenz-Seitentitel), die zugehörige Bilddatei heißt korrekt „Sanssouci" – der Fehler ist also menschlich eingetippt, nicht systemisch | Design, Verkaufspsychologie | Ja (Strg+F auf Live-Seite) |
| 8 | **Rohe GPS-Koordinaten als sichtbarer Text:** Auf allen 81 geprüften Referenzkarten der `/referenzen`-Seite stehen nackte Zahlen wie „52.5395…/13.4819…" mitten im Content – dazu ausnahmslos jedes Bild ohne Alt-Text und jeder Projekt-Link ohne Linktext | Design | Ja (Seite öffnen, jede Karte zeigt es) |

Alle Detail-Findings mit vollständigen Belegen, Schweregraden und Business-Impact-Bewertung stehen in den vier Dimension-Dokumenten (`analyse/dimension-seo.md`, `dimension-geo-lokal.md`, `dimension-verkaufspsychologie.md`, `dimension-design-ux.md`) – insgesamt 58 einzeln belegte Befunde.

---

## Priorisierte Quick Wins (Projektvorschlag-Grundlage)

### Sofort umsetzbar (Tage, Aufwand S)
- CTA-Bug „Leistungsübersicht" → /kontakt korrigieren
- Tippfehler bereinigen (Sanssouci, Chausseestraße, Oranienburg u. a.)
- Vier defekte/falsche Google-Maps-Links korrigieren
- Duplizierte Platzhalter-Referenzkarte im Slider entfernen
- „Single Source of Truth" für Kernfakten (Standorte, MA-Zahl, Gründungsjahr) definieren und auf allen Seiten synchronisieren

### Kurzfristig (4–6 Wochen, Aufwand S–M)
- hreflang/Canonical korrigieren, damit die deutsche Seite bei deutschen Suchen rankt
- Google-Business-Profile für alle Standorte anlegen/bereinigen
- NAP-Konsistenz in Branchenverzeichnissen herstellen (Alt-Firmierungen entfernen)
- Eigene interne Seiten für „Planung" und „Vermessung" statt externer Weiterleitung
- CTA-Differenzierung nach Zielgruppe (privat/gewerblich/öffentlich) und Funnel-Stufe („Kostenloses Erstgespräch" statt generischem „Jetzt kontaktieren")
- Alte `/unternehmensgruppe/*`-URLs per 301 auf die neue Struktur umleiten

### Mittelfristig (2–4 Monate, Aufwand M)
- Referenzen neu strukturieren: Kategorien + Story-Format statt reiner Kartenliste, leere Datenfelder auffüllen
- Standort-Landingpages für alle 7–8 Standorte (aktuell nur News-Artikel)
- schema.org-Markup (Organization/LocalBusiness/subOrganization mit sameAs)
- Content-Tiefe der Leistungsseiten erhöhen (Gewerke-Ebene, Kennzahlen-Beweise)
- Bewertungsstrategie starten (systematisch Google-Rezensionen nach Projektabschluss einholen)

### Langfristig (4–12 Monate, Aufwand L)
- Standort×Leistung-Landingpages nach Wettbewerber-Blaupause (Z-Geschossbau-Vorbild)
- Domain-Konsolidierung (5–6 Satelliten-Domains auf bbf-gruppe.com zusammenführen)
- llms.txt und KI-Zitierfähigkeit systematisch ausbauen
- Vollständige technische SEO-Tiefenprüfung (robots.txt, Sitemap, JSON-LD-Audit)

---

## Gesprächsleitfaden für den Vertriebstermin

### Eröffnung: Das Substanz-Sichtbarkeits-Paradox
Eröffne mit der Kernbotschaft der Executive Summary: „Sie sind wahrscheinlich der substanzstärkste Anbieter Ihrer Region – aber online praktisch unsichtbar." Das ist positiv formuliert (keine Kompetenzkritik), schafft aber sofort Handlungsdruck. Zeige, falls möglich, live eine Google-Suche nach „Generalunternehmer Berlin" – BBF taucht nicht auf.

### Schmerzpunkt → Lösung → Nutzen

**1. Schmerzpunkt: „Kein Standort ist online auffindbar – nicht mal Ihr eigener Firmensitz."**
- Beleg: Stichprobe „Bauunternehmen Mittenwalde" (14.07.2026) – 0 Treffer für BBF, Kleinbetriebe dominieren.
- Lösung: Google-Business-Profile + Standort-Landingpages je Niederlassung.
- Nutzen: Lokale Auftraggeber und Investoren finden BBF überhaupt erst, wenn sie danach suchen. Das ist die Grundvoraussetzung für jede weitere Maßnahme.

**2. Schmerzpunkt: „Ihre Website hat keinen einzigen Kundenbeweis."**
- Beleg: 0 Google-Bewertungen bei ~350 Mitarbeitern; einziger prominenter Drittinhalt rät zur Vorsicht.
- Lösung: Bewertungsstrategie + strukturierte Story-Referenzen statt Kartenliste.
- Nutzen: Bei einer Generalunternehmer-Beauftragung (hohes Investitionsvolumen, lange Bindung) ist Social Proof der stärkste Vertrauenshebel – aktuell komplett ungenutzt, obwohl das Rohmaterial (Sanssouci, Pergamonmuseum, Tempelhof) besser ist als bei jedem Wettbewerber.

**3. Schmerzpunkt: „Wer Ihren Firmennamen googelt, landet bei einer fremden Firma."**
- Beleg: Zwei branchennahe Namensvetter (Köln, Karlsruhe) auf Platz 3 und 5 der Brand-Suche.
- Lösung: schema.org-Markup, konsolidierte Domain-Strategie, aktiver Aufbau eines eigenen Knowledge-Panel-Ankers.
- Nutzen: Kontrolle über die eigene Markenwahrnehmung zurückgewinnen – besonders relevant, weil KI-gestützte Suchen diese Verwechslung ungefiltert übernehmen.

**4. Schmerzpunkt: „Ihre Website schickt Interessenten aktiv zur Konkurrenz oder ins Leere."**
- Beleg: CTA-Bug (Leistungsübersicht → Kontakt), zwei External-Links ohne Rückweg, vier tote Maps-Links.
- Lösung: Technisches Audit + Funnel-Überarbeitung mit klaren, zielgruppenspezifischen CTAs.
- Nutzen: Sofort messbare Conversion-Verbesserung, unabhängig von zusätzlichem Traffic – der schnellste ROI-Nachweis im gesamten Projekt.

### Mögliche Einwände & Antworten

- **„Wir haben doch gerade erst relaunched."** → Genau das erklärt die Befunde: Duplicate Content aus der alten URL-Struktur, doppelte Karriereseiten und Sprachversions-Fehler sind klassische, unvollständig abgeschlossene Relaunch-Altlasten. Das ist normal, aber unbehoben – und günstig zu fixen, solange die Substanz (Content, Referenzen) bereits da ist.
- **„Unsere Größe/Bekanntheit reicht doch."** → Der Wörpel-Bau-Vergleich widerlegt das direkt: 30 Mitarbeiter schlagen 350 bei der wichtigsten Suche. Größe ersetzt keine SEO-Architektur.
- **„Bewertungen kann man doch nicht erzwingen."** → Stimmt, aber der Prozess (aktives Nachfragen nach Projektabschluss) lässt sich systematisieren; aktuell gibt es nicht mal 5 Bewertungen insgesamt – schon 10–15 echte Rezensionen wären ein sichtbarer Unterschied.
- **„Das sind doch nur Kleinigkeiten (Tippfehler etc.).“** → Zeige das Muster: Kleinigkeit + Kleinigkeit + Kleinigkeit ergibt in der Summe einen Eindruck von mangelnder Sorgfalt – ausgerechnet bei einem Unternehmen, dessen Kernversprechen „Qualität und Verlässlichkeit" ist (O-Ton Startseite).

### Projektpakete (Vorschlag zur Strukturierung)

- **Paket S – „Sofort-Fixes":** Die Quick-Wins der Kategorie „Sofort" + „Kurzfristig" (CTA-Bug, Tippfehler, tote Links, Faktenkonsistenz, GBP-Grundaufbau, hreflang-Fix). Schneller, klar abgegrenzter Auftrag mit sofort sichtbarem Ergebnis – guter Einstiegspunkt.
- **Paket M – „Sichtbarkeit & Vertrauen":** Zusätzlich Referenzen-Relaunch, Standort-Landingpages, CTA-/Funnel-Überarbeitung, schema.org, Start der Bewertungsstrategie.
- **Paket L – „Marktführerschaft":** Vollständige Umsetzung inkl. Standort×Leistung-Seiten, Domain-Konsolidierung, laufende SEO-/GEO-Betreuung, Content-Ausbau. Positionierung: „BBF online so stark aufstellen, wie das Unternehmen real ist."

---

## Verzeichnis der Detail-Dokumente

- `daten/recherche/serp-wettbewerber.md` – SERP-Analyse, Wettbewerber-Profile, Seitenstruktur-Recherche
- `daten/recherche/reputation-lokal-marke.md` – Bewertungen, Social-Media-Präsenz, Markenverwechslungsanalyse
- `daten/crawl/*.md` – Vollständiger gecrawlter Seiteninhalt (Startseite, Leistungen, Hochbau, Referenzen, Kontakt, Über uns)
- `analyse/dimension-seo.md` – SEO-Detailanalyse mit 14 Findings und Roadmap
- `analyse/dimension-geo-lokal.md` – GEO/Lokal-Detailanalyse mit 11 Findings und Roadmap
- `analyse/dimension-verkaufspsychologie.md` – Verkaufspsychologie-Detailanalyse mit 14 Findings
- `analyse/dimension-design-ux.md` – Design/UX-Detailanalyse mit 19 Findings (inkl. Methodik-Disclaimer zur fehlenden visuellen Prüfung)

**Offene Nachprüfung:** Eine technische Tiefenanalyse (vollständige hreflang-Matrix, JSON-LD-Audit, robots.txt/Sitemap-Abdeckung) konnte in der verfügbaren Zeit nicht abgeschlossen werden und basiert in den Dimension-Dokumenten auf indirekt aus SERP-Daten abgeleiteten Indizien. Empfehlung: vor einem finalen Angebot per Browser-Zugriff gegenprüfen.
