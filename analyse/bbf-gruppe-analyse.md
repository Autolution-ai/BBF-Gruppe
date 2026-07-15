# bbf-gruppe.com – Punkte für das Vorgespräch

**Zweck:** Interne Vorbereitung für den Vertriebsleiter – konkrete, selbst nachprüfbare Beobachtungen und Verbesserungsvorschläge.

**Stand:** 15.07.2026

---

## Teil 1 — Überblick & Verbesserungspotenzial

### Kleine, schnell behebbare Fehler

- **Rechtschreibfehler beim wichtigsten Referenzprojekt:** Schloss Sanssouci wird sowohl auf der Startseite als auch als eigener Seitentitel auf `/referenzen` als „Sanssousi" geführt. Die zugehörige Bilddatei im Hintergrund heißt korrekt „Sanssouci" – der Fehler ist von Hand eingetippt.
- **Toter Link:** Auf `/leistungen` führt der „Mehr erfahren"-Button bei „Planung" auf `plant-plant.de` – eine praktisch leere Seite ohne Inhalt (nur Logo, ein Link).
- **Falscher Call-to-Action:** Der Startseiten-Button „Zu unserer Leistungsübersicht" verlinkt auf das Kontaktformular statt auf die Leistungsseite.
- **Vier fehlerhafte Google-Maps-Verlinkungen** bei Tochtergesellschaften: BBF Elektrotechnik (toter Anker), BBF Spree Gerüstbau (zeigt auf Mittenwalde statt Luckau), BBF Herold GaLaBau und JoMi Gartenbau (beide zeigen auf Grünheide statt auf die angegebene Adresse Soldiner Str. 53, Berlin).
- **Rohe GPS-Koordinaten als sichtbarer Text:** Auf `/referenzen` stehen bei jeder Projektkarte zwei nackte Zahlen (Breiten-/Längengrad) unformatiert im Content – wirkt wie ein technischer Konfigurationsfehler.
- **Widersprüchliche Kennzahlen** zwischen Unterseiten: mal 7, mal 8 Standorte; mal 200, mal 350 Mitarbeiter; mal 25, mal 30 Jahre Erfahrung (z. B. deutsche Startseite vs. englische Version).

### Größere Verbesserungsvorschläge

- **Google-Bewertungen sichtbar machen:** Es existiert bereits ein Google-Unternehmensprofil (bei direkter Google-Suche nach dem Unternehmen sichtbar) – wird aber auf der eigenen Website an keiner Stelle genutzt. Ein eingebundenes Bewertungs-Widget würde echte Kundenstimmen zeigen, Vertrauen schaffen und zusätzlich die lokale SEO-Sichtbarkeit stärken (Google gewichtet eingebundene, aktuelle Bewertungen positiv). Das ergänzt das bereits vorhandene, starke Referenzportfolio (81 Projekte inkl. Schloss Sanssouci, Pergamonmuseum, Flughafen Tempelhof) um die fehlende Kundenperspektive.
- **Moderneres, konsistenteres Design:** Mehrere technische Indizien sprechen für eine in die Jahre gekommene Umsetzung – ein Platzhalter-Icon statt eines echten Fotos im Hero-Bereich der Startseite, mehrere Leistungen (Gerüstbau, Vermessung, Planung) ohne eigene vollwertige Unterseite, und eine im Quellcode doppelt vorhandene Sektion (separate Desktop-/Mobil-Blöcke statt einer sauber responsiven Umsetzung).
- **SEO-Sichtbarkeit verbessern:** Bei zentralen Suchbegriffen wie „Generalunternehmer Berlin" oder „Bauunternehmen Berlin Brandenburg" ist die Website aktuell schwer auffindbar – selbst am eigenen Firmensitz Mittenwalde. Lässt sich im Termin per Inkognito-Suche selbst gegenprüfen.
- **Ladezeiten prüfen und optimieren:** Eine echte Messung war technisch nicht möglich (Zugriff war in unserer Testumgebung gesperrt), aber sichtbare Hinweise sprechen für ein Risiko: großformatige, unkomprimiert wirkende Fotos direkt aus dem CDN, besonders in der umfangreichen Referenzgalerie, ohne erkennbare Optimierung. Empfehlung: vor einem Angebot mit einem echten Test (z. B. PageSpeed Insights) untermauern.

---

## Teil 2 — Live im Termin zeigbar

Diese Punkte lassen sich in wenigen Klicks direkt auf der Live-Website demonstrieren.

| Was zeigen | Wie |
|---|---|
| **CTA-Bug** | Startseite öffnen → Button „Zu unserer Leistungsübersicht" anklicken → landet im Kontaktformular statt auf der Leistungsseite |
| **Toter Link „Planung"** | `/leistungen` öffnen → bei „Planung" auf „Mehr erfahren" klicken → leere Seite auf plant-plant.de (nur Logo) |
| **Falsche Maps-Links** | Startseite oder `/kontakt` → „Wegbeschreibung" bei BBF Spree Gerüstbau anklicken → führt nach Mittenwalde statt Luckau |
| **GPS-Koordinaten im Klartext** | `/referenzen` öffnen → erste Karte „Tiefbauarbeiten in der Konrad-Wolf-Straße, Berlin" → zwischen Bild und Kategorie-Label stehen die Zahlen `52.53958463322082` und `13.48193231141988` |
| **Tippfehler „Sanssousi"** | Auf der Startseite oder `/referenzen` mit Strg+F nach „Sanssousi" suchen |
| **Widersprüchliche Kennzahlen** | Deutsche Startseite und englische Version (`/en`) nebeneinander öffnen – unterschiedliche Standort-/Mitarbeiterzahlen |

---

## Verzeichnis der Detail-Dokumente

- `analyse/dimension-seo.md`
- `analyse/dimension-geo-lokal.md`
- `analyse/dimension-verkaufspsychologie.md`
- `analyse/dimension-design-ux.md`
- `daten/recherche/serp-wettbewerber.md`, `daten/recherche/reputation-lokal-marke.md`
- `daten/crawl/*.md` – gecrawlter Originalinhalt der Seiten
