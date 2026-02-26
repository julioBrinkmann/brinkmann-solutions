# Brinkmann Solutions – Website

**Domain:** [www.brinkmann-solutions.de](https://www.brinkmann-solutions.de)
**Hosting:** GitHub Pages
**Typ:** Statischer One-Pager (einzelne HTML-Datei)

---

## Über das Projekt

Professionelle Consulting-Website für Julio Benjamin Brinkmann, getrennt vom bestehenden Manufaktur-Geschäft (sueco UG / sueco.de). Die Seite positioniert Brinkmann Solutions als Partner für kleine Firmen und Mittelständler im Bereich Data Analytics, Digitalisierung und KI-Beratung.

## Zielgruppe

- Kleine und mittelständische Unternehmen (KMU) in Deutschland
- Geschäftsführer und Entscheider, die Digitalisierung, Automatisierung oder BI-Lösungen suchen
- Ansprache: **Sie-Form**, seriös aber nahbar

## Leistungsbereiche

1. **Power BI & Datenanalyse** – Dashboards, Reports, Datenmodellierung
2. **Microsoft Fabric & Datenplattform** – Skalierbare Dateninfrastruktur
3. **Dynamics 365 & CRM** – Kundenmanagement, Vertriebsautomatisierung
4. **KI-Beratung & Automatisierung** – Workflows, n8n, intelligente Automatisierung

## Design-Entscheidungen

- **Stil:** Editorial Minimalism – asymmetrische Layouts, Kupfer-Akzente, warme Farbwelt
- **Farbpalette:**
  - Schwarz/Charcoal: `#0C0C0C` / `#1A1A1A`
  - Kupfer (Akzent): `#B8784E` / `#D4956A`
  - Cream/Warm White: `#F5F0EB` / `#FAF8F5`
- **Typografie:** Instrument Serif (Headlines) + Manrope (Body)
- **Sprache:** Nur Deutsch
- **Animationen:** Gezielt eingesetzt – Scroll-Reveal bei Leistungen und Über-mich, Zahlen-Counter, Marquee-Laufband

## Seitenstruktur (Sektionen)

1. **Hero** – Headline, Subline, CTA, Foto-Platzhalter
2. **Marquee-Laufband** – Keywords in Kupfer
3. **Leistungen** – 4 Service-Zeilen mit Hover-Effekt
4. **Über mich** – Werdegang + Kennzahlen (14+ Jahre, 4 Kompetenzfelder, MUC)
5. **Referenzen** – 2 Platzhalter für Kundenstimmen
6. **Kontakt** – E-Mail-Link, Standort München
7. **Footer** – Copyright, Impressum, Datenschutz (Links noch leer)

## Offene Punkte / TODOs

- [ ] **Foto einfügen** – Professionelles Foto im Hero-Bereich ersetzen
- [ ] **Kundenstimmen einfügen** – Platzhalter-Testimonials mit echten Zitaten ersetzen
- [ ] **Impressum erstellen** – Pflichtangaben nach § 5 TMG (Name, Adresse, Kontakt, USt-IdNr.)
- [ ] **Datenschutzerklärung erstellen** – DSGVO-konform, insb. Google Fonts extern eingebunden
- [ ] **Custom Domain verbinden** – CNAME-Eintrag bei Domain-Anbieter auf GitHub Pages zeigen
- [ ] **E-Mail-Alias einrichten** – julio@brinkmann-solutions.de als Alias im M365 Tenant
- [ ] **Favicon erstellen** – Passendes Icon für Browser-Tab
- [ ] **Open Graph Meta-Tags** – Für WhatsApp/LinkedIn-Vorschau beim Teilen
- [ ] **Google Fonts lokal hosten** – Für DSGVO-Konformität (aktuell extern von Google geladen)

## E-Mail-Konzept

- **Primäre Adresse:** julio@brinkmann-solutions.de
- **Einbindung:** Als Alias im bestehenden Microsoft 365 Tenant
- **Separate Signatur** für Brinkmann Solutions im Outlook

## GitHub Pages Setup

```bash
# Im Projektordner:
git init
git add .
git commit -m "Initial commit: Brinkmann Solutions website"
gh repo create brinkmann-solutions --public --source=. --push

# Dann auf github.com:
# Settings → Pages → Branch: main → Save
# Settings → Pages → Custom domain: www.brinkmann-solutions.de

# Beim Domain-Anbieter:
# CNAME-Eintrag: www → deinusername.github.io
# Oder A-Records für Apex-Domain:
# 185.199.108.153
# 185.199.109.153
# 185.199.110.153
# 185.199.111.153
```

## Technische Details

- **Keine Dependencies** – Reines HTML/CSS/JS, keine Build-Tools
- **Externe Ressource:** Google Fonts (Instrument Serif, Manrope)
- **Responsive:** Mobile-first, Breakpoints bei 640px und 1024px
- **Performance:** Einzelne Datei, < 50 KB, keine Bilder (außer Foto)
