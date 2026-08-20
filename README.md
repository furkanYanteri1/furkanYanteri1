# Furkan Yanteri

**Founder of ObliqueX Global. Product manager and full stack engineer.**

I build B2B products end to end: strategy, architecture, code, release, and the client conversations in between. Five years of that in global enterprise environments, now running my own software studio alongside product work.

[![Website](https://img.shields.io/badge/ObliqueX-obliquex.com-111111?style=flat-square)](https://www.obliquex.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-furkan--yanteri-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/furkan-yanteri)
[![Email](https://img.shields.io/badge/Email-furkanyanteri@gmail.com-333333?style=flat-square&logo=gmail&logoColor=white)](mailto:furkanyanteri@gmail.com)

Computer Engineering graduate, based in Turkey, working with distributed teams across Europe, the UK, the Middle East and Australia. English at full professional proficiency.

---

## ObliqueX Global

My software studio. It does two things at once: it builds and operates its own products, and it delivers custom software for companies that need something specific built properly. I own the whole line, from the first client call to the production deploy and whatever breaks after it.

Active markets: Germany, United Kingdom, United Arab Emirates, Australia, Turkey.

| Product | What it is | Status |
|---|---|---|
| [GoalT](https://goalt.org) | Open source goal graph engine for prioritization, shipped as a Claude Code plugin | Published on PyPI, Apache 2.0 |
| [Furkan Interior](https://furkaninterior.com) | Booking and operations platform for a commercial cleaning and renovation business | Live, serving real customers |
| Video Speeder | Canva app that speeds up video beyond the platform's native limit, up to 50x | In Canva app review |
| [Otopact](https://otopact.com) | Two sided platform connecting vehicle owners with authorized service providers | In development, first markets targeted for Q1 2027 |
| KelimeYap | iOS and Android word game family, React Native and Expo on Supabase | In development |

Client work covers web and mobile platforms, AI driven business automation, digital signage systems, and internal planning and workflow software.

---

## Open source: GoalT

Most prioritization tools assume a clean hierarchy. One goal breaks into sub goals, those break down further, and the shape stays a tree. Real work does not behave that way. A single fix often serves three different initiatives for three different reasons, and a tree cannot express that.

GoalT models goals as a directed acyclic graph. Every parent distributes exactly 1.0 of value across its children, and a goal with multiple parents accumulates value from each of them. Work that genuinely matters to more parts of a project rises to the top on its own, without anyone assigning it a priority number by hand.

[![PyPI](https://img.shields.io/pypi/v/goaltree?style=flat-square&label=pypi%20goaltree&color=3775A9)](https://pypi.org/project/goaltree/)
[![Python](https://img.shields.io/pypi/pyversions/goaltree.svg?style=flat-square)](https://pypi.org/project/goaltree/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue?style=flat-square)](https://github.com/GOAL-T/goaltree/blob/main/LICENSE)

- Published on PyPI: `pip install goaltree`
- Listed in the official Model Context Protocol registry as `io.github.furkanYanteri1/goaltree`
- Ships as a Claude Code plugin: an MCP server plus a live dashboard that shows which goal the agent is working on right now
- Value redistribution is pluggable. The default split is deterministic and needs no API key. An LLM can decide the weights instead, and whatever it returns is validated and renormalized, so the graph stays mathematically consistent even when the model returns something odd
- Apache 2.0, with tests covering the engine, the MCP server and the dashboard
- Runnable Colab notebook, so it can be tried without installing anything

Repository: **[GOAL-T/goaltree](https://github.com/GOAL-T/goaltree)**

---

## Selected work

### Video Speeder, a Canva app

Canva caps video playback speed at 2x. Video Speeder lets a user pick a video already sitting on their canvas, speed it up to 50x, and get the processed result back in place. Built solo, full stack: React and TypeScript on Canva's Apps SDK and App UI Kit, a Node.js and Express backend running native FFmpeg, containerized with Docker.

The interesting parts were the constraints:

- Canva's content security policy blocks Web Workers outright, which rules out in browser processing with ffmpeg.wasm. That finding forced a full architecture pivot to server side processing.
- Output files have to fit inside platform storage limits, so the backend derives the bitrate from clip duration and target speed and guarantees the size before encoding starts, rather than encoding first and hoping.
- Canva's asset API could return a `blob:` reference that looks valid but is not yet usable, because the video was still being registered on their backend. That race showed up as a confusing failure, so it is now a retry with real feedback to the user.
- Encoding parameters were tuned to finish reliably inside free tier compute limits, which is what stopped larger files from timing out.
- Internationalized with Canva's app i18n kit and react-intl.

Currently in Canva's review queue, at the design review stage.

### Furkan Interior

A production web platform for a commercial cleaning and renovation business in Ankara: service catalog, booking flow, customer content and an admin side, in Turkish. React and TypeScript with Supabase behind it, plus Three.js and an LLM integration on the content side. Around 480 commits, live at [furkaninterior.com](https://furkaninterior.com) and used by real customers rather than sitting in a portfolio.

### KelimeYap

A word game family for iOS and Android, React Native and Expo on Supabase, monetized through ads plus an ad free subscription. Roughly 900 files and 370 commits so far. In development, English release planned.

---

## Background

### Cloudit
**Software Product Manager. January 2025 to present. London, United Kingdom.**

Managing end to end development of a software product with three sub products, from ideation to MVP. Market research, stakeholder alignment, roadmap and delivery, staying close to QA, UAT and API testing rather than handing specs over the wall. Prioritizing under real ambiguity while keeping delivery velocity intact. Day to day across BlackBoard, Miro, Notion, Jira, Figma, Mixpanel and SurveyMonkey on the product side, and Vue.js, Pinia, MongoDB, Node.js, Express, Firebase, S3, JWT, WebSockets, Elasticsearch and GitHub Actions on the technical side.

### Pitcher AG
**Frontend Developer, then Software Engineer and Technical Project Manager. June 2021 to June 2024. Ankara, Turkey.**

Pitcher is a global sales enablement platform used by enterprise clients including Johnson & Johnson and Novartis. I spent three years there and moved into technical project management in 2024 without leaving the codebase behind.

*Engineering:* built user interfaces and backend systems across Vue.js, JavaScript and ES6, PHP, MySQL and SQLite. Built reusable component libraries on Vuetify and internal design systems. Maintained REST and GraphQL integrations, including Salesforce. Cut load times by up to 40 percent through frontend and data layer work. Refactored legacy jQuery and vanilla JS that was still carrying production traffic. Ran zero downtime releases and set up CI/CD on GitHub Actions.

*Project and product:* ran sprint planning, backlog refinement and stakeholder reviews. Acted as escalation point for Tier 2 and Tier 3 production incidents, owning root cause analysis and SLA response. Led API driven implementation projects with third party developers, coordinated releases across distributed teams, and ran A/B tests to settle product arguments with data instead of opinion.

### BITES Defence and Aerospace Technologies
**Intern Computer Engineer. 2020. Ankara, Turkey.**

Applied deep learning to image classification and object detection.

---

## How I work

**Product management.** Roadmaps that survive contact with engineering. Discovery and scoping with the people who will actually use the thing. Backlog prioritization when everything is urgent. Agile ceremonies that produce decisions rather than status updates. A/B testing and experiment design. Enterprise stakeholder management, briefings and demos. Delivery ownership through release and post launch iteration.

**Engineering.** Frontend, backend, APIs, databases and cloud infrastructure, with production ownership attached. Integration heavy systems where reliability and security are requirements rather than aspirations. Native and cross platform mobile. The willingness to open the container logs at midnight instead of filing a ticket.

**AI product work.** Designing AI driven products and automation workflows on modern model APIs, orchestration layers and MCP tooling. Prompt orchestration and evaluation flows. Building agent facing infrastructure, which is exactly what GoalT is.

---

## Tech

| Area | Tools |
|---|---|
| Frontend | Vue.js, React, Next.js, TypeScript, JavaScript, Vuetify, Tailwind, Sass |
| Backend and APIs | Node.js, Express, PHP, Python, REST, GraphQL, WebSockets, JWT, OAuth2 |
| Data | PostgreSQL, Supabase, MongoDB, MySQL, SQLite, Elasticsearch |
| Mobile | React Native, Expo, iOS (Swift, SwiftUI), Android (Java) |
| AI and automation | Claude API, OpenAI API, Model Context Protocol, deep learning with Keras and TensorFlow, n8n, Zapier |
| DevOps and quality | Git, GitHub Actions, CI/CD, Docker, AWS, Vercel, Render, ESLint, Prettier, Jest, Vitest |
| Product and delivery | Agile and Scrum, Jira, Confluence, Notion, Figma, Miro, Mixpanel, roadmapping, A/B testing |

---

## Education

**Sakarya University**, Bachelor of Engineering, Computer Engineering.
**Gebze Technical University**, Computer Engineering.

---

## Certifications

Every entry below links to its issuer's verification page.

**Product, project and business**

| Certificate | Issuer | Issued |
|---|---|---|
| [Foundations of Project Management](https://www.coursera.org/account/accomplishments/verify/AUXFV5W9MSOQ) | Google | Jul 2026 |
| [Foundations of Account Management](https://www.coursera.org/account/accomplishments/verify/G827L3CDUN9N) | Microsoft | May 2026 |
| [Grow as a Manager](https://www.coursera.org/account/accomplishments/verify/TB7KPNJHAH4U) | Google | Jul 2026 |
| [Create a High Performing Team](https://www.coursera.org/account/accomplishments/verify/C5G52ZG7GC2M) | Google | Jul 2026 |
| [Set and Achieve Team Goals](https://www.coursera.org/account/accomplishments/verify/2679KOD5EQT2) | Google | Jul 2026 |
| [Support Individual Growth and Development](https://www.coursera.org/account/accomplishments/verify/3L8LX9ECJSYT) | Google | Jul 2026 |
| Google People Management Essentials | Google | Jul 2026 |
| [Advanced Business Analysis, CBAP](https://www.udemy.com/certificate/UC-2df57136-be4d-4be5-bdf9-4b78bde610fc/) | Udemy, Igor Arkhipov | Oct 2024 |
| [Product Management Masterclass](https://www.udemy.com/certificate/UC-6389f01d-6f45-4062-9754-126b0eb5851f/) | Udemy | Oct 2024 |
| [Product Management by a Big Tech PM](https://www.udemy.com/certificate/UC-235bb739-ad8b-44e9-af56-1860209cd4a9/) | Udemy, Dr Bart Jaworski | Oct 2024 |
| [Product Strategy](https://www.udemy.com/certificate/UC-f1d0d075-10e2-4c2b-84c2-fe61f3c3a609/) | Udemy, Todd Birzer | Oct 2024 |

**Engineering, data and AI**

| Certificate | Issuer | Issued |
|---|---|---|
| [SQL Foundations](https://www.coursera.org/account/accomplishments/verify/D2OLJBDPE0TX) | Microsoft | Aug 2026 |
| [Introduction to Artificial Intelligence](https://www.coursera.org/account/accomplishments/verify/1H2WOFIHLDOP) | IBM | Jul 2026 |
| [Complete iOS 16 Development with SwiftUI](https://www.udemy.com/certificate/UC-88106e34-77e0-4cde-b44e-22e22deba4a4/) | Udemy | May 2025 |
| [Machine Learning with Python](https://www.udemy.com/certificate/UC-d1472294-8283-4077-9274-2960eec38a7f/) | Udemy | Jan 2022 |
| [Android Development with Java](https://www.udemy.com/certificate/UC-9598144a-a133-4e52-bd8a-b844f6790c53/) | Udemy | Jun 2021 |
| [Deep Learning with Keras and TensorFlow](https://www.coursera.org/account/accomplishments/verify/EDLMK92DY4NK) | IBM | Feb 2021 |
| [End to End Data Science with KNIME](https://www.udemy.com/certificate/UC-8df52b6a-5b1b-4ab2-ac78-e63ab98467a8/) | Udemy | Sep 2020 |
| [Java EE Patterns and Architecture](https://www.udemy.com/certificate/UC-aafb52c9-40d3-4114-90be-f8177fd66ee8/) | Udemy | Jan 2020 |

---

## Contact

Open to conversations about B2B product work, AI product management, and anything built on the Model Context Protocol.

- **Web:** [obliquex.com](https://www.obliquex.com)
- **LinkedIn:** [furkan-yanteri](https://linkedin.com/in/furkan-yanteri)
- **Email:** [furkanyanteri@gmail.com](mailto:furkanyanteri@gmail.com)
- **Instagram:** [@devtriessomeshit](https://instagram.com/devtriessomeshit)
