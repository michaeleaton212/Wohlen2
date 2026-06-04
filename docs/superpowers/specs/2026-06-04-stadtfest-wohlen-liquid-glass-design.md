---
title: Stadtfest Wohlen 2027 — Liquid Glass Event Website
date: 2026-06-04
status: approved
---

# Stadtfest Wohlen 2027 — Liquid Glass Event Website

## Overview

A single `index.html` event website for the 150th anniversary Stadtfest Wohlen, 18–20 September 2027. Design language: Liquid Glass / Apple Vision Pro aesthetic — Glassmorphism as the primary design system with animated mesh-gradient background.

## Technical Architecture

- **File:** Single `index.html` (all CSS and JS inline)
- **No build tool, no framework**
- **Fonts:** Google Fonts — Outfit (headlines), DM Sans (body)
- **Language:** German (Swiss style — no "ß")

## Colour System

| Token | Value | Use |
|---|---|---|
| Accent Red | `#CC1A2E` | Wohlen brand, CTAs, highlights |
| Ice Blue | `#A8D8EA` | Glow accents, badges |
| Gold | `#F5C842` | Highlight badges, star items |
| Glass BG | `rgba(255,255,255,0.08–0.15)` | All glass surfaces |
| Glass Border | `rgba(255,255,255,0.2)` | Card/nav borders |
| Mesh base | Midnight blue → Indigo → Violet | Animated background |

## Glassmorphism Design System

All interactive surfaces (cards, nav, modals, forms) use:
- `backdrop-filter: blur(24–40px)`
- `background: rgba(255,255,255,0.08–0.15)`
- `border: 1px solid rgba(255,255,255,0.18)`
- Inner glow: `box-shadow: inset 0 1px 0 rgba(255,255,255,0.2)`
- Outer glow on hover/focus

## Sections (in order)

### 1. Navigation
Sticky frosted-glass bar. Blur increases on scroll (JS scroll listener adds class). Links: Home, Programm, Aktivitäten, Anmeldung, Über uns, Kontakt. Mobile: hamburger menu → glassmorphic slide-in drawer.

### 2. Hero
Full-viewport. Glassmorphic container centred. Wohlen logo area (text-based). Tagline: "150 Jahre Geschichte — drei Tage gemeinsam feiern". Countdown timer (days/hours/minutes/seconds) rendered as glowing Liquid-Glass badges. Dates: 18.–20. September 2027. CTA buttons in Liquid Glass pill style.

### 3. Statistics
4 animated counter cards: 3 Festtage / 100+ Aktivitäten / 50+ Aussteller / 20 000+ Besucher. Scroll-triggered count-up animation.

### 4. Feature Cards
3 main feature cards: Konzerte & Musik / Sport & Bewegung / Kulinarik & Genuss. Multilayer glass, hover-lift with shimmer light reflection.

### 5. Festgelände Map
SVG-based venue map with glowing glassmorphic pins. Category filter pills (Musik, Gastronomie, Sport, Information, Sanitäre Anlagen). Clicking a pin opens a glassmorphic tooltip/modal with location info.

### 6. Festprogramm
Tab switcher: Freitag 18.9 / Samstag 19.9 / Sonntag 20.9. Each tab shows a timeline/list of events with time, title, location, category badge.

**Freitag 18.9 (5 events)**
- 17:00 Offizieller Festauftakt — Hauptbühne
- 18:30 Stadtlauf Wohlen — Festgelände
- 19:00 Konzert Lokalband — Bühne 2
- 20:00 Abendshow — Hauptbühne
- 22:00 Late Night DJ — Festzelt

**Samstag 19.9 (8 events)**
- 10:00 Familienfrühstück — Festplatz
- 11:00 Kinderparadies öffnet — Kinderzone
- 12:00 Marktbummel — Ausstellerzone
- 14:00 Sportturnier — Sportareal
- 15:30 Kulturprogramm — Kulturbühne
- 17:00 Konzert Regionalband — Hauptbühne
- 19:30 Galadiner — Festzelt
- 21:00 Grosses Abendkonzert — Hauptbühne

**Sonntag 20.9 (7 events)**
- 10:00 Ökumenischer Gottesdienst — Festgelände
- 11:30 Brunch & Markt — Ausstellerzone
- 13:00 Kindershow — Kulturbühne
- 14:30 Sportvorführungen — Sportareal
- 16:00 Festkonzert — Hauptbühne
- 17:30 Festansprache & Ehrungen — Hauptbühne
- 18:30 Abschlussfeuerwerk — Festgelände

### 7. Aktivitäten
Grid of activity cards with category filter. Categories: Musik & Bühne / Sport & Bewegung / Kulinarik & Genuss / Kinder & Familie / Kultur / Gala & Feier. Clicking a card opens a glassmorphic detail modal.

### 8. Anmeldeformular
Fields: Vorname*, Nachname*, E-Mail*, Telefon, Anzahl Personen (1–10 stepper), Altersgruppe (select), Interesse (checkboxes for categories), Bemerkungen (textarea). Submit shows success animation — no real backend.

### 9. Kontakt
Contact form: Name, E-Mail, Betreff (select: Allgemeine Anfrage / Sponsoring & Partnership / Medienanfrage / Aussteller & Stand / Programm & Aktivitäten), Nachricht. Contact details: info@stadtfest-wohlen.ch / +41 56 000 00 00 / Festbüro, Gemeindehaus, 5610 Wohlen AG / Di–Fr 09:00–12:00.

### 10. Über uns / Team
OK-Komitee Stadtfest Wohlen AG. President Hans Meier. History of Wohlen since 1877. Volunteer committee structure. Team member cards (glassmorphic avatars).

### 11. Footer
Sponsor logos: Raiffeisen Schweiz, Gemeinde Wohlen, Kanton Aargau. Social links: Facebook, Instagram. Links: Datenschutz, Impressum. Copyright 2027 Stadtfest Wohlen AG.

### 12. Cookie Banner
Bottom-fixed glassmorphic banner. "Akzeptieren" / "Nur notwendige" buttons. localStorage persistence. Disappears after choice.

### 13. Datenschutz Modal
Full-screen glassmorphic overlay. Complete Swiss-style privacy policy. Opened via footer link.

### 14. Impressum Modal
Full-screen glassmorphic overlay. Legal notice for Swiss event. Opened via footer link.

## Animations & Micro-interactions

- Animated mesh gradient background (slow, fluid CSS keyframe animation)
- Staggered page-load reveal (each section fades up with 100ms delay)
- Scroll-triggered fade-ins (IntersectionObserver)
- Countdown timer (JS setInterval, updates every second)
- Stat counter count-up (IntersectionObserver trigger)
- Navigation blur intensifies on scroll
- Button shimmer on hover
- Card hover: translateY(-8px) + increased blur + shimmer sweep
- Form input glow on focus
- Tab transitions: smooth opacity/transform cross-fade
- Filter pill transitions: smooth show/hide with scale animation
- Modal: scale-up + blur-in open; reverse close
- Success form submission: checkmark animation

## Responsive Strategy

Mobile-first. Breakpoints: 640px (sm), 768px (md), 1024px (lg), 1280px (xl). Navigation collapses to hamburger at <768px. Cards stack to 1-column at <640px. Map scales proportionally.
