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

© 2026 Dr Oscar Harrison, trading as Medrics. All rights reserved — see
LICENSE. This is not open-source software.
