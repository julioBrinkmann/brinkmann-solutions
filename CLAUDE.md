# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Projekt

Statische One-Pager Website für **Brinkmann Solutions** (brinkmann-solutions.de).
Consulting-Website für Julio Benjamin Brinkmann – Data Analytics, Power BI, Microsoft Fabric, Dynamics 365, KI-Beratung.

## Wichtige Regeln

- **Sprache:** Deutsch, Sie-Ansprache
- **Keine Build-Tools:** Reines HTML/CSS/JS, kein npm, kein Framework
- **Einzelne Datei:** Alles in `index.html` (CSS und JS inline)
- **Hosting:** GitHub Pages – keine serverseitigen Features verwenden
- **Design:** Editorial Minimalism – KEIN generisches AI-Template-Design

## Architektur der index.html

Die gesamte Website lebt in einer einzigen `index.html` (~1280 Zeilen) mit drei Inline-Blöcken:

1. **`<style>`** (Zeile ~11–980): CSS mit Custom Properties in `:root`, Sektions-Styles, Animationen, Responsive Breakpoints
2. **HTML-Body** (Zeile ~982–1205): Sektionen in Reihenfolge: Nav → Hero → Marquee → Leistungen → Über mich → Referenzen → Kontakt → Footer
3. **`<script>`** (Zeile ~1207–1274): Vanilla JS für Nav-Scroll-Verhalten, Mobile-Menü, IntersectionObserver (Scroll-Reveal), Zahlen-Counter-Animation

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

### Farben
- Schwarz: `#0C0C0C`, Charcoal: `#1A1A1A`
- Kupfer (Akzent): `#B8784E`, Kupfer hell: `#D4956A`
- Cream: `#F5F0EB`, Warm White: `#FAF8F5`
- Grautöne: `#A39E97`, `#6B6660`

### Typografie
- Headlines: `Instrument Serif` (Google Fonts)
- Body: `Manrope` (Google Fonts)

### Animationen
- Scroll-Reveal nur an gezielten Stellen (Leistungen, Über mich, Referenzen)
- Zahlen-Counter im Über-mich-Bereich
- Marquee-Laufband nach Hero (duplizierte Items für nahtlose Schleife)
- Grain-Overlay via SVG-Noise auf `body::after`
- Keine übertriebenen Animationen – dezent und professionell

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

- Foto-Platzhalter im Hero: `.hero-photo-placeholder` ersetzen durch `<img>` Tag
- Testimonials: Platzhalter-Texte in `.testimonial` Karten ersetzen
- Impressum/Datenschutz: Separate HTML-Seiten erstellen und Footer-Links aktualisieren (`<a href="#">` noch leer)
- Google Fonts sollten langfristig lokal gehostet werden (DSGVO)
- Footer zeigt noch `© 2025` – ggf. aktualisieren
- Neue Sektionen bekommen fortlaufende Nummern (aktuell 01–04 in `section-num`)
