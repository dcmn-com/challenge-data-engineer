# AI Data Engineering Challenge

## Context

You are a data engineer at a media agency that runs TV advertising campaigns for multiple clients across different European markets. Campaign data arrives from various sales houses and broadcasters, each using their own export format.

Your task is to design a **canonical data model** that could serve as the unified storage layer for spot airing data from any provider. We are looking for simple and pragmatic solutions.

## Data

You have been provided with three spot airing export files, each from a different provider:

| File | Provider type | Market |
|------|--------------|--------|
| `spot-airings-provider-a.csv` | Sales house export (English columns) | DE |
| `spot-airings-provider-b.csv` | Sales house export (German columns) | CH |
| `spot-airings-provider-c.edi` | Broadcaster transmission plan (EDI format) | DE |

For the EDI format, refer to the specification in `docs/170509 EDI Format_21b.pdf`.

## Task 1 — Canonical data model

Study all three files and produce a **canonical data model** as a Markdown document.

Your model should include:

- Table/entity names
- Field names with data types
- Short notes on non-obvious design decisions — especially where you considered an alternative and chose not to use it

There is no single correct answer. We are interested in how you think about the problem and what trade-offs you make.

### What we expect

A flat, readable model. A short written rationale for key decisions is more valuable than a complete schema with no explanation.

---

## Task 2 — Ingestion script

Write a Python script (standard library only — no pandas, no third-party packages) that reads all three source files and writes the data to stdout as a CSV.

Each output row should map to a single spot airing and include the columns from the `spot_airing` table you designed in Task 1.

### What we expect

A single script that handles all three files and produces correct output for every row. Flat and readable — no unnecessary abstraction. The conversion logic for each provider can live in a separate function.

Please also include the actual output of your script — a CSV file containing all consolidated rows — alongside your submission.

---

## Task 3 — Stakeholder slide

Prepare **one slide** (PowerPoint or PDF) that explains one design decision from your model to a non-technical campaign manager. Assume they understand TV advertising but have no knowledge of data engineering or SQL.

The slide should make clear:
- what the decision is
- why it matters for their work

### What we expect

A single slide. We are looking for judgment — which decision did you choose to explain, and can you explain it without jargon?

---

## Submission

Create a **private GitHub repository** with your solution and add the following accounts as collaborators:

- [@dron22](https://github.com/dron22)
- [@nomeshkumar](https://github.com/nomeshkumar)

---

You are welcome to use AI tools. If you do, briefly note where and how in your submission.

Expected time: **1–3 hours total** (all three tasks combined).
