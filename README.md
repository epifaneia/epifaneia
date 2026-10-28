# Daniel Martín · Epifaneia

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
| [cv](https://github.com/epifaneia/cv) | The CV as a pipeline: data, template, one-page PDF in Spanish and English. | one page, checked on every build |

Every repository ships with a **Security & regulation** section and an integration contract: who runs it, what gets recorded, who signs. See `docs/INTEGRATION.md` in any of them.

[epifaneia.dev](https://epifaneia.dev) · danielmartin@epifaneia.dev · [LinkedIn](https://www.linkedin.com/in/epifaneia/)
