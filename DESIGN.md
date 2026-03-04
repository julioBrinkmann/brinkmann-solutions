# Design-System: Brinkmann Solutions

Lebendiges Design-Dokument für brinkmann-solutions.de.
Enthält das aktuelle Design-System, die Design-Historie, Erkenntnisse und Anforderungen für die Weiterentwicklung.

---

## 1. Aktives Design-System (Cool Corporate)

Aktiv seit Commit `ddd451a`.

### Farben

| Variable         | Wert                         | Beschreibung        | Verwendung                          |
|------------------|------------------------------|---------------------|-------------------------------------|
| `--black`        | `#0A0E1A`                    | Navy-Schwarz        | Text, dunkle Flächen                |
| `--charcoal`     | `#111827`                    | Dunkles Navy        | Nav-Hintergrund, Hero               |
| `--warm-dark`    | `#1E293B`                    | Slate-Dunkel        | Kontakt-Sektion, Footer             |
| `--copper`       | `#64748B`                    | Steel (Akzent)      | Akzentfarbe, Buttons, Links         |
| `--copper-light` | `#94A3B8`                    | Helles Steel        | Hover-States, sekundäre Akzente     |
| `--cream`        | `#F1F5F9`                    | Kühles Hellgrau     | Wechsel-Hintergrund (Sektionen)     |
| `--warm-white`   | `#F8FAFC`                    | Kühles Weiß         | Haupt-Hintergrund (Body)            |
| `--warm-gray`    | `#94A3B8`                    | Slate-Grau          | Untertitel, Meta-Text               |
| `--mid-gray`     | `#64748B`                    | Mittleres Slate     | Fließtext in dunklen Sektionen      |
| `--light-line`   | `rgba(15, 23, 42, 0.08)`     | Subtile Linien      | Trennlinien, Borders                |
| `--white`        | `#FFFFFF`                    | Weiß                | Text auf dunklem Grund              |

### Typografie

| Rolle       | Schriftart          | Gewichte          | Quelle       |
|-------------|---------------------|-------------------|--------------|
| Headlines   | Cormorant Garamond  | 400, 500, 600     | Google Fonts |
| Body-Text   | Inter               | 300–700           | Google Fonts |

### Visuelles Konzept
- Kühle, professionelle Navy/Slate-Palette
- Elegante Serif-Headlines + moderne Sans-Serif Body
- Grain-Overlay (SVG-Noise) auf `body::after` für subtile Textur
- Kein generisches AI-Template-Gefühl – reduziertes, editorials Layout

### Animationen
- Scroll-Reveal (IntersectionObserver) an Leistungen, Über mich, Referenzen
- Zahlen-Counter-Animation im Über-mich-Bereich
- Marquee-Laufband nach Hero (duplizierte Items für nahtlose Schleife)
- Nav-Transition: dunkel (transparent) → hell (compact) nach Hero-Scroll
- Alles dezent und professionell – keine übertriebenen Effekte

### Responsive Breakpoints
- Desktop: > 1024px
- Tablet: 641px – 1024px
- Mobile: ≤ 640px

---

## 2. Design-Prinzipien & Anforderungen

### Grundsätze
- **Kein generisches AI-Design:** Website muss sich von typischen Template-Seiten abheben
- **Weniger ist mehr:** Reduziertes Layout, viel Weißraum, klare Hierarchie
- **Professionell, nicht steril:** Cool Corporate heißt nicht kalt – Eleganz durch Typografie und Spacing
- **Konsistenz:** Alle Unterseiten (Impressum, AGB, Datenschutz) folgen dem gleichen Design-System

### Sprache & Ton
- Deutsch, Sie-Ansprache
- Professionell aber nahbar
- Keine Marketing-Floskeln

### Technische Anforderungen
- Reines HTML/CSS/JS – keine Build-Tools, keine Frameworks
- GitHub Pages kompatibel (statisch)
- DSGVO-konform (Google Fonts langfristig lokal hosten)
- Performant: Minimale externe Abhängigkeiten

---

## 3. Erkenntnisse & Entscheidungen

### CSS-Variablennamen beibehalten
Die Variablennamen (z.B. `--copper`, `--warm-dark`) stammen vom Original-Design und beschreiben die aktuellen Farben nicht mehr korrekt. Bewusst beibehalten, um keine Referenzen im gesamten CSS zu brechen. Bei einem größeren Refactoring könnten sie umbenannt werden (z.B. `--accent`, `--dark`).

### Unterseiten-Konsistenz
Impressum, AGB und Datenschutz verwenden ein einheitliches Layout: gleiche Nav, gleicher Footer, gleiche Farben und Schriften. Neue Unterseiten sollten diesem Muster folgen.

### Google Fonts (DSGVO-Thema)
Aktuell werden Cormorant Garamond und Inter extern von Google Fonts geladen. Für vollständige DSGVO-Konformität sollten die Fonts lokal gehostet werden. Bis dahin wird in der Datenschutzerklärung darauf hingewiesen.

---

## 4. Ideen & Wünsche für die Weiterentwicklung

_Hier neue Ideen und Anforderungen eintragen:_

- [ ] ...
- [ ] ...

---

## 5. Design-Historie

### V1: Editorial Minimalism (Warm/Kupfer)

Aktiv von Projektstart bis Commit `06d2f41`.

#### Farben

| Variable         | Wert                        | Beschreibung        |
|------------------|-----------------------------|---------------------|
| `--black`        | `#0C0C0C`                   | Fast-Schwarz        |
| `--charcoal`     | `#1A1A1A`                   | Dunkles Grau        |
| `--warm-dark`    | `#2C2824`                   | Warmes Dunkelbraun  |
| `--copper`       | `#B8784E`                   | Kupfer (Akzent)     |
| `--copper-light` | `#D4956A`                   | Helles Kupfer       |
| `--cream`        | `#F5F0EB`                   | Creme               |
| `--warm-white`   | `#FAF8F5`                   | Warmes Weiß (BG)    |
| `--warm-gray`    | `#A39E97`                   | Warmes Grau         |
| `--mid-gray`     | `#6B6660`                   | Mittleres Grau      |
| `--light-line`   | `rgba(12, 12, 12, 0.08)`    | Subtile Linien      |
| `--white`        | `#FFFFFF`                    | Weiß                |

#### Typografie

| Rolle       | Schriftart         | Quelle       |
|-------------|--------------------|--------------|
| Headlines   | Instrument Serif   | Google Fonts |
| Body-Text   | Manrope            | Google Fonts |

#### Charakteristik
- Warme, erdige Farbpalette mit Kupfer als Akzentfarbe
- Creme- und Warmweiß-Töne für eine einladende Atmosphäre
- Instrument Serif für einen editorialen, hochwertigen Look
- Manrope als geometrisch-runde Body-Schrift

### V1 → V2: Vergleich

| Eigenschaft  | V1 (Warm)                 | V2 (Cool Corporate)       | Richtung           |
|--------------|---------------------------|----------------------------|--------------------|
| Grundton     | Braun/Kupfer-Palette      | Navy/Slate-Palette         | Warm → Kühl        |
| Akzent       | `#B8784E` Kupfer          | `#64748B` Steel            | Orange → Blaugrau  |
| Hintergrund  | `#FAF8F5` Cremig-Warm     | `#F8FAFC` Kühl-Neutral     | Gelbstich → Blaustich |
| Dunkel-Töne  | `#1A1A1A` Neutral-Schwarz | `#111827` Navy-Schwarz     | Neutral → Bläulich |
| Headlines    | Instrument Serif          | Cormorant Garamond         | Modern → Klassisch |
| Body         | Manrope                   | Inter                      | Rund → Clean       |
