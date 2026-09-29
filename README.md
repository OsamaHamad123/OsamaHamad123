# Hi, I'm Osama Hamad 👋

**Software Engineer** — mobile, backend and microservices  
🎓 B.Sc. Software Engineering, Islamic University of Gaza (2025) · M.Sc. Artificial Intelligence (in progress)

📄 **[Download my CV (PDF)](https://github.com/OsamaHamad123/OsamaHamad123/blob/main/Osama-Hamad-CV.pdf)**

I build production software end to end: Flutter apps shipped to the App Store and Google Play, Laravel and Next.js backends, microservices, and Python automation pipelines. Most of what I ship is Arabic/RTL-first, works offline, and is backed by thousands of automated tests and CI gates. I'm currently pursuing a Master's degree in Artificial Intelligence.

---

## What I bring

- 📱 **Mobile** — Flutter & Dart for Android and iOS · GetX, Bloc, Riverpod · Clean Architecture · offline-first sync · MyFatoorah, Apple Pay, Google Pay · Google Maps, Mapbox · Firebase
- 🌐 **Backend & web** — Laravel 10/11 (Livewire, Sanctum, RBAC, Redis queues) · Next.js 16 + TypeScript + PostgreSQL/Drizzle · REST APIs · MySQL
- 🧩 **Microservices** — independent services talking over REST · Celery/Redis workers on isolated queues · Docker
- 🤖 **AI & automation** — Python (FastAPI, Celery) · Gemini text & vision · OpenCV image processing · Google Sheets/Drive pipelines
- 🔐 **Security** — certificate pinning, Firebase App Check, step-up MFA, Postgres Row Level Security, end-to-end encryption (Argon2id, XChaCha20-Poly1305, X25519)
- ✅ **Quality & delivery** — unit, widget, golden, integration and e2e tests · GitHub Actions & Codemagic pipelines · Fastlane releases · Firebase App Distribution
- 🌍 **Arabic & English** — RTL-first UX and full localization

---

## Featured work

### 🛍️ Boulevard Super App · Flutter · 2024 – present
A production super app for the UAE, live on the App Store and Google Play.
- About 13 verticals in one app (grocery, restaurants, retail, beauty, medical, hotel & flight booking, motors, real estate, insurance, laundry and more), with a shared cart, memberships and MyFatoorah payments.
- 1,500+ Dart files, about 4,900 tests and 70+ custom CI guard scripts (secret leaks, dependency direction, startup budget, untranslated strings). Releases go to both stores through Codemagic and Fastlane.
- The cart mutation queue survives the app being killed. Security includes certificate pinning and Firebase App Check. JSON is parsed off the main thread, and p95 startup and frame times are tracked against budgets.

`Flutter` `GetX` `Bloc` `Firebase` `MyFatoorah` `Google Maps` `UAE Pass` `Mixpanel` `Codemagic`

### 🏠 Real-Estate Marketplace (UAE) · Flutter · 2026 · 🔒 private
An Arabic-first property marketplace: map search, listings, off-plan reservations, short stays, a price index, agency subscriptions and an AI assistant.
- Clean Architecture, with the layering rules enforced as architecture tests in CI.
- About 1,800 tests, including golden, RTL and accessibility tests, behind a 70% coverage gate. The Widgetbook design system has 15 catalogs.
- MyFatoorah card entry with Apple Pay and Google Pay, Mapbox clustering and Firebase phone auth.

`Flutter` `Bloc` `go_router` `GetIt/Injectable` `freezed` `Dio` `Mapbox` `Widgetbook`

### 🤝 Charity Operations Platform (UK) · Laravel · 2025 – 2026 · 🔒 private
A bilingual AR/EN platform that runs a charity's day-to-day work: beneficiaries and case management, events with QR check-in, a school (attendance, assessments, certificates), volunteers and a public form builder.
- 130 models, 180+ controllers and 258 migrations. The code is layered into actions, DTOs, repositories and services, with CQRS-style domain modules.
- 320+ PHPUnit test files. CI runs critical-path gates on every change and the full suite nightly.
- Security includes RBAC, step-up MFA (TOTP/SMS), break-glass access, CSP headers, rate limiting and file encryption.

`Laravel 10` `Livewire 3` `MySQL` `Redis` `Tailwind` `Spatie Permission`

### 🔑 Argon Lock · Flutter + TypeScript · 2026 · 🔒 private
A zero-knowledge password manager with a Chrome/Edge extension. It is pre-release. I designed the architecture and the security model.
- Argon2id key derivation, XChaCha20-Poly1305 encryption, device linking over X25519, and end-to-end encrypted sync on Supabase with forced RLS.
- Passkeys, TOTP, Android autofill, breach checks against HIBP using k-anonymity, and duress/decoy vaults.
- The Dart app and the TypeScript extension are checked against the same crypto test vectors. There are about 950 tests, including tamper and timing tests.

`Flutter` `Drift` `cryptography` `Supabase` `TypeScript` `Manifest V3` `Playwright`

### 📋 [Benaa — Offline-First Field App](https://github.com/OsamaHamad123/benaa_offline_app) · Flutter + PHP · 2025 – 2026
A field app for a relief organisation. Staff register families, log home visits, and manage sponsorships, partner associations and reports without a connection.
- All field work is captured offline in a local Drift/SQLite store with versioned migrations. Changed records are tracked per row and pushed to the server in paged two-way sync.
- I built both sides. The PHP/MySQL API has hashed bearer tokens, login lockout, and a transactional delta-sync endpoint with tombstones for deletes.
- Offline sign-in against a PBKDF2 hash in secure storage, Arabic name search with spelling normalisation over a large reference database, and PDF/Excel reports.
- 480+ tests. CI builds Android and iOS and ships to Firebase App Distribution.

`Flutter` `Riverpod` `Drift` `GoRouter` `PHP` `MySQL` `GitHub Actions`

### 🏫 [Education Center](https://github.com/OsamaHamad123/education-center) · Next.js · 2026
A management system for a multi-branch tutoring centre (Arabic, RTL, mobile-first): classes, timetables, attendance, fees, payroll, and teacher and parent portals.
- A modular monolith of 16 modules, with boundaries enforced by ESLint. Every mutation passes through one pipeline: auth → permission → Zod → tenant → audit.
- Each branch's data is isolated twice: in the app layer and by 76 Postgres Row Level Security policies. Database constraints make overlapping timetable slots impossible.
- Unit tests, integration tests on real Postgres and Playwright e2e tests. Deployed with Docker and Caddy, with encrypted backups.

`Next.js 16` `React 19` `TypeScript` `PostgreSQL` `Drizzle` `Better Auth` `Playwright`

### 🖼️ [Product Image Automation Pipeline](https://github.com/OsamaHamad123/product-image-automation-pipeline) · Python microservices · 2026
Automates catalogue images for a grocery store. The pipeline reads SKUs from Google Sheets, searches for images, verifies them with Gemini Vision, removes backgrounds, normalises to 800×800, removes duplicates, uploads to Cloudinary and writes the results back to the sheet. A Laravel dashboard lets staff curate the picks.
- Microservices architecture: the Laravel dashboard calls independent FastAPI services over REST, and Celery workers run on separate queues (crawling, GPU enhancement, embeddings, de-duplication) so each one scales on its own.
- Live progress streamed to the dashboard with server-sent events.
- Near-duplicate detection with pHash and a BK-tree, hybrid search with Reciprocal Rank Fusion, and an image proxy that blocks internal-network requests (SSRF).

`Python` `FastAPI` `Celery` `Redis` `Gemini` `OpenCV` `Laravel 11`

---

## Education

- 🎓 **M.Sc. Artificial Intelligence**, in progress
- 🎓 **B.Sc. Software Engineering**, Islamic University of Gaza, 2025

## Languages

🗣️ **Arabic**, native · **English**, good

---

## Tech stack

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Codemagic](https://img.shields.io/badge/Codemagic-F45E3F?style=flat-square&logo=codemagic&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)

---

## Get in touch

[![Email](https://img.shields.io/badge/Email-osamahamad665%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:osamahamad665@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-OsamaHamad123-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/OsamaHamad123)
