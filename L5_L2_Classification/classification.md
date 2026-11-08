# L5 Narrow / L2 General Classification — L_OPENWEBRX
**Platform:** Anticloud | **Tier:** TIER_8_RF_MESH_DEFENSE | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
L_OPENWEBRX deploys OpenWebRX for Anticloud RF spectrum monitoring: browser-based spectrum waterfall, digital mode decoding (WSPR, FT8, AIS), and PAX 27B anomaly detection on the spectrum. Narrow scope: Anticloud passive RF monitoring.

## L2 General
L2 General: L_OPENWEBRX provides RF situational awareness for any Anticloud tier requiring spectrum monitoring. TIER_8 tactical deployments use it to detect interference and unauthorized transmissions.

## PAX 27B Integration
PAX 27B analyzes RF spectrum for anomalies: 'Unknown narrowband emission at 433.2MHz, -70dBm — not matching ISM device database. Possible unauthorized transmitter. Log and alert.'

## AIOSS Audit Chain
Every spectrum event (frequency hash + signal characteristics hash + modulation type + PAX anomaly assessment) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
FCC Part 15 (passive receive). ITU-R (spectrum monitoring). Passive only.
