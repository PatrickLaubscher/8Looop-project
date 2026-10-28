# 8Looop

> A web application for self-exploration, built around a model of consciousness in eight circuits. Currently in **closed beta**: [8looop.com](https://www.8looop.com)

This repository is a **project presentation**. The source code is private.

---

## What it does

- **Explore**: an interactive diagram of the eight circuits, free and public.
- **Self-assess**: a questionnaire drawn from a question bank, followed by a written synthesis of the user's results, with a headline and three keywords as a starting point for reading.
- **Compare over time**: a new synthesis can be compared with the user's previous one, to show what has moved between two sessions.
- **Follow-up** (optional): reminder emails after a synthesis, and, in a planned paid plan, follow-up by a practitioner. Both are **opt-in and revocable at any time** from the user's settings.
- **Bilingual**: French and English.

---

## Engineering principles

1. **Numbers are computed in code, never by the LLM.** Every value is calculated deterministically in Java. The language model receives structured input that is already computed and only writes the text.
2. **LLM output is treated as untrusted input.** Each generated text is validated by code (structure, length, wording rules). On failure it is retried once, then falls back safely. Nothing unvalidated reaches the user.
3. **Consent comes first.** Optional processing is opt-in, can be withdrawn at any time, and is visible to the user.
4. **Abuse protection built in**: per-endpoint rate limiting, session-based authentication, access restricted to the data's owner.
5. **Reproducible environments**: versioned database migrations, no secrets in the repository, separate `dev`, `preprod` and `main` environments.

---

## Stack

| Layer | Technology |
|---|---|
| Back end | Java 21, Spring Boot 4.1, Spring Data JPA, Spring Security |
| Front end | React, TypeScript, Vite, Tailwind CSS v4, i18next |
| Database | PostgreSQL, schema versioned with Flyway |
| LLM | Claude API, used for text generation only |
| CI/CD | GitLab CI (build and tests) |
| Hosting | VPS (OVH) |

---

## Status

Closed beta with a small group of testers. Features are released in small versions (`0.x-beta`) with a public-facing changelog in the app.

---

## About

Built by **Patrick Laubscher**, full-stack developer (RNCP Level 6).

The project comes from a long-standing interest in NLP and personal development.

- LinkedIn: [linkedin.com/in/patrick-laubscher](https://www.linkedin.com/in/patrick-laubscher)
- Portfolio: [patricklaubscherdev.com](https://www.patricklaubscherdev.com)
- Project: [8looop.com](https://www.8looop.com)

---

© 2026 Patrick Laubscher. All rights reserved. The 8Looop name, brand, texts and source code are protected and may not be reused without written permission.
