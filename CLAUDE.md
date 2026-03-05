# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Projekt

Statische One-Pager Website für **Brinkmann Solutions** (brinkmann-solutions.de).
Consulting-Website für Julio Benjamin Brinkmann – Data Analytics, Power BI, Microsoft Fabric, Dynamics 365, KI-Beratung.

## Wichtige Regeln

- **Sprache:** Deutsch, Sie-Ansprache
- **Keine Build-Tools:** Reines HTML/CSS/JS, kein npm, kein Framework
- **Hauptdatei:** `index.html` (CSS und JS inline). Zusätzlich existieren `impressum.html`, `agb.html`, `datenschutz.html` als separate Unterseiten.
- **Hosting:** GitHub Pages – keine serverseitigen Features verwenden
- **Design:** Cool Corporate (Navy/Steel) – KEIN generisches AI-Template-Design. Details in `DESIGN.md`

## Architektur der index.html

Die Hauptseite `index.html` (~1632 Zeilen) enthält drei Inline-Blöcke:

1. **`<style>`** (Zeile ~100–1202): CSS mit Custom Properties in `:root`, Sektions-Styles, Animationen, Responsive Breakpoints
2. **HTML-Body** (Zeile ~1204–1468): Sektionen in Reihenfolge: Nav → Hero → Marquee → Leistungen → Über mich → Referenzen → Kontakt → Footer
3. **`<script>`** (Zeile ~1470–1629): Vanilla JS für Nav-Scroll-Verhalten, Mobile-Menü, IntersectionObserver (Scroll-Reveal), Zahlen-Counter-Animation, E-Mail-Obfuscation

### CSS-Architektur
- Custom Properties in `:root` für alle Farben (z.B. `--copper`, `--charcoal`, `--cream`)
- Responsive: Mobile-first mit Breakpoints bei `1024px` und `640px`
- Animationsklassen: `.reveal` + `.visible` (per IntersectionObserver), `.reveal-delay-1` bis `-3` für Stagger
- Nav wechselt Stil via `.compact`-Klasse nach Scroll über Hero hinaus

### JavaScript-Verhalten
- **Nav-Compact:** Wechselt zu hellem Nav-Hintergrund wenn Scroll-Position > Hero-Höhe
- **Scroll-Reveal:** IntersectionObserver mit `threshold: 0.08` fügt `.visible` hinzu (Service-Rows sliden von links, Testimonials skalieren hoch)
- **Counter-Animation:** Eigener IntersectionObserver mit `threshold: 0.5` für die Zahlen im Über-mich-Bereich (14+, 4) – `MUC` hat Klasse `.no-counter`

## Design-System

Vollständige Dokumentation in `DESIGN.md` (Farben, Typografie, Historie, Anforderungen).

### Kurzreferenz (aktiv: Cool Corporate)
- Farben: Navy/Slate-Palette (`--black: #0A0E1A`, `--charcoal: #111827`, `--copper: #0D9488`)
- Headlines: `Cormorant Garamond` (Google Fonts)
- Body: `Inter` (Google Fonts)
- Animationen: Scroll-Reveal, Counter, Marquee, Grain-Overlay – dezent und professionell

## Kontaktdaten auf der Seite

- E-Mail: jb@brinkmann-solutions.de
- Standort: München, Deutschland
- Inhaber: Julio Benjamin Brinkmann

## Firma / Rechtliche Angaben

Brinkmann Solutions ist eine Marke/Tätigkeit von Julio Brinkmann. Die Abrechnung der IT-Beratung erfolgt über seine Firma:

- **Firma:** sueco UG (haftungsbeschränkt)
- **Adresse:** Schleißheimer Straße 23, 80333 München
- **Geschäftsführer:** Julio Brinkmann
- **Registergericht:** Amtsgericht München
- **Handelsregisternummer:** HRB 201489
- **USt-IdNr:** DE285741287
- **Telefon:** 089 / 443 823 73
- **E-Mail (Firma):** info@sueco.de

Diese Angaben sind für Impressum und AGB der Website zu verwenden.

## Aufgaben-Tracking

Offene Aufgaben und Projektfortschritt werden in `STATUS.md` gepflegt. Bei jeder erledigten Aufgabe dort den Status aktualisieren.

## Hinweise für Änderungen

- Testimonials: Platzhalter-Texte in `.testimonial` Karten durch echte Kundenstimmen ersetzen
- Google Fonts sollten langfristig lokal gehostet werden (DSGVO)
- Favicon erstellen und einbinden
- Neue Sektionen bekommen fortlaufende Nummern (aktuell 01–04 in `section-num`)
