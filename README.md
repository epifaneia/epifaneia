# Daniel Martín · Epifaneia

**AI Engineer (Python) · Seville or remote · available now** · [CV (PDF)](https://epifaneia.dev/cv/Daniel_Martin_AI_Engineer_EN.pdf) · [epifaneia.dev](https://epifaneia.dev)

**AI carries risk. Code bounds it. The standard answers for what remains.**
*La IA tiene riesgos. El código los acota. La norma responde de lo que queda.*

I design AI solutions for regulated processes: documents that arrive dirty, requirements that must be checked against thousand-page manuals, files that a third-party system has to accept on the first attempt. Local models by default, measured numbers, written limitations.

Every AI application has five steps. Only one invokes a model; the other four are code.

```
 1 CLEANING      2 CONTEXT       3 INPUT GUARDRAIL   4 PROCESS        5 OUTPUT GUARDRAIL
 ■ code          ■ code          ■ code              ▲ model          ■ code
```

| Repository | What it does | Measured |
|---|---|---|
| [ctsm](https://github.com/epifaneia/ctsm) | Audits customer requirements (a Polarion ReqIF) against supplier manuals and returns the same file with the evidence and its exact page. The model never writes a location. Runs offline. | 9/9 vs ground truth with a local 14B model, zero false "compliant" · every quote checked literally against the manual |
| [reqif-extractor](https://github.com/epifaneia/reqif-extractor) | From a specification PDF to a ReqIF that Polarion imports on the first attempt: verbatim identifiers, document hierarchy, page order. | without the identifier policy the model invented 167 of 170 ids; with it, verbatim · ~1/20 of the vision cost |
| [ordena](https://github.com/epifaneia/ordena) | Messy orders (a half-written email, a WhatsApp voice note) into Business Central as unposted sales orders: customer, items and dates resolved by code against the ERP's master data, doubts flagged, a person validates. Local transcription and model. | end to end against Business Central (CRONUS demo data) · no duplicate on reprocessing |
| [toolkit](https://github.com/epifaneia/toolkit) | The reusable part of every pipeline: one tool per design step, generic guardrails, and the three integration wires a company connects to its own systems: identity, event ledger, sign-off. | 16 local tests, no network |
| [feasibility-study](https://github.com/epifaneia/feasibility-study) | Full stack: from a meeting form to an AI feasibility study in PDF. An autonomous research run across hundreds of pages, turned by code into a report with our narrative and our order, with cited sources. Human review before anything is sent. | QA warnings per lead · report reproducible from `extraccion.json` |
| [askhub](https://github.com/epifaneia/askhub) | Ask your whole workspace in plain language: Discord and Trello over their APIs, a single-file local index, minutes transcribed locally, and a bot that answers the state of every project on the spot. | 0 € to run · tests without network |
| [asimetrica](https://github.com/epifaneia/asimetrica) | A voice-first Android app for thinking out loud on a walk: you talk through a wired headset, a strong model takes its time and answers in your ear, the phone stays in your pocket. One model per stage, a library of your own work as canon, nothing lost when the network fails. [Install the APK](https://github.com/epifaneia/asimetrica#install-it-on-your-phone). | vs CrewAI on the same task: 9/10 with 10 model calls against 6/10 with 96 |
| [neuralib](https://github.com/epifaneia/neuralib) | My 2023 bootcamp Django library, rewritten: 300 public-domain books with search by meaning (pgvector) and a librarian that only recommends from the catalog, quoting the line that backs it; code checks the quote exists. [Try it](https://neuralib-m8q6.onrender.com) (the first visit may take a minute to wake up). | expected book in the top 5 for 34/34 hand-written questions · 81 tests in CI |
| [mildew](https://github.com/epifaneia/mildew) | My 2024 cherry leaf classifier (CNN in Keras), rescued: I found and closed two train/test leaks (1,393 duplicated images, augmentation before the split). Three notebooks saved with their outputs and a Streamlit app you can [try in the browser](https://mildew-8ygp4es5aitvvhp8buud32.streamlit.app). | 879/879 on a leak-free test set · near duplicates checked in the notebook |
| [cv](https://github.com/epifaneia/cv) | The CV as a pipeline: data, template, one-page PDF in Spanish and English. | one page, checked on every build |
| [nogum](https://github.com/epifaneia/nogum) | My tabletop role-playing game, years in the making: a compiler for a bilingual manual of more than 200 pages and the web app that configures a game from it. Deterministic gates stop the build when the book and the data stop saying the same thing. [Read it](https://epifaneia.dev/nogum/). | 189 design decisions traced · Appendix B: 56 rows, 0 discrepancies |

Every repository has a **Security & regulation** section. The AI pipelines (ctsm, reqif-extractor, feasibility-study, askhub and toolkit) also ship an integration contract, `docs/INTEGRATION.md`: who runs it, what gets recorded, who signs.

[epifaneia.dev](https://epifaneia.dev) · danielmartin@epifaneia.dev · [LinkedIn](https://www.linkedin.com/in/epifaneia/)
