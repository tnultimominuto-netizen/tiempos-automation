# TIEMPOS Automation

Public zero-cost scheduler for TIEMPOS central learning.

This repository intentionally contains no TIEMPOS application source code and no credentials.

## Private source
At runtime the workflow downloads only the canonical private source from:
- `tnultimominuto-netizen/radar-de-suerte`
- branch `tiempos/current`

## Required Actions secrets
- `TIEMPOS_REPO_TOKEN`: fine-grained GitHub token with Contents: Read-only access to `radar-de-suerte` only.
- `FIREBASE_SERVICE_ACCOUNT_JSON`: Firebase service-account JSON for project `radar-de-suerte`.

## Costa Rica schedule
- 12:25 pre-draw midday
- 13:10 post-draw midday
- 15:55 pre-draw afternoon
- 16:45 post-draw afternoon
- 18:55 pre-draw night
- 19:45 post-draw night

## First test
Run the workflow manually with:
- mode: `healthcheck`
- period: `midday`

The healthcheck downloads the private source, validates the backend, authenticates only against `radar-de-suerte`, writes a temporary Firestore document, reads it back, and deletes it.
