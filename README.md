# Patient Information QR

A clinician searches, ticks leaflets, and shows a QR code; the patient scans it
and gets links to their trust's own published patient information plus national
NHS.uk content. No login, no patient data — the tool never knows who the
patient is.

This repository contains only what the web pages serve: the two pages, the
published data files, and the QR library. The quality pipeline that keeps the
data fresh and verified (scrapers, fact checking against cited sources,
link and review-date monitoring, coverage audits) runs on Medrics
infrastructure and is not published here.

## Intended purpose

This tool **finds and hands over published patient information**. It performs
no diagnosis, no risk scoring, and no patient-specific recommendation of any
kind: nothing about an individual patient is ever entered, known, or processed.
Every suggestion (search ranking, "often given together", specialty ranking) is
generic content-to-content curation, identical for every patient.

## Repository map

Machine-readable versions of this map: [`llms.txt`](llms.txt) (plain-text index
for AI assistants) and [`knowledge.jsonld`](knowledge.jsonld) (schema.org
JSON-LD describing every page and data file). `*.min.json` files are minified
twins of their `.json` source — the pages fetch the minified copy.

| File | What it is |
|---|---|
| `picker.html` | Clinician page: search, tick leaflets, generate the QR code |
| `index.html` | Patient landing page the QR opens — lists the selected links |
| `trusts.json` | Registry of trusts served (id, name, ODS code, where data lives) — start here |
| `leaflets.json` | Gloucestershire Hospitals' leaflet library (title, url, slug); at the root so pre-multi-trust QR codes still resolve |
| `trusts/<id>/leaflets.json` | Every other live trust's library, same shape (some with a `reviews.json`) |
| `reviews.json` | Per-leaflet review-date status, keyed by slug |
| `medicines.json` | NHS.uk medicine pages, searchable alongside leaflets |
| `nhs_resources.json` | National NHS.uk pages + official GOV.UK/CAA advice pages (type `gov`) |
| `services.json` | Trust service/department pages |
| `local_advice.json` | Locally authored advice pages rendered by the landing page |
| `related_bundles.json` | "Often given together" bundles (generic, identical for every patient) |
| `specialty_profiles.json` | Specialty ranking profiles for search ordering |
| `manual_overrides.json` | Hand-set URL corrections, each with a note |
| `qrcode.min.js` | Third-party QR rendering library |

© 2026 Dr Oscar Harrison, trading as Medrics. All rights reserved — see
LICENSE. This is not open-source software.
