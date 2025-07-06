## Launch Timeline (11‑day sprint)

|                  |                        |                                                                                                  |                  |
| ---------------- | ---------------------- | ------------------------------------------------------------------------------------------------ | ---------------- |
| Day              | Focus                  | Key Deliverables                                                                                 | Buffer / Travel  |
| **D0 (Today)**   | Kick‑off               | Finalize scope, data sources, success metric; set up repo & Kanban                               | 2 h planning     |
| **D1**           | Data Ingest            | Connect to NOAA radar API & USGS river gauges; stub local CSVs for elevation + population layers |                  |
| **D2**           | ETL Pipeline           | Normalize geospatial layers → parquet; Dockerize an Airflow DAG                                  |                  |
| **D3**           | Core Flood Model       | Implement Hydrology ☰ ML hybrid; output 6‑ & 12‑h flood depth raster                             | Travel (evening) |
| **D4**           | Infrastructure Overlay | Join substations, hospitals, census tracts → compute damage proxy $                              | Travel buffer    |
| **D5**           | Risk Ranking API       | FastAPI endpoint: `POST /rank` returns top‑N hex‑cells w/ risk score                             |                  |
| **D6**           | Front‑end Map          | Leaflet + Deck.gl map; hex‑cell heat layer; asset pop‑ups                                        |                  |
| **D7**           | Validation             | Back‑test on Apr 2025 Texas floods; hit ≥80 % hotspot recall                                     |                  |
| **D8**           | Slide Deck             | Storyboard problem, data, demo screenshots; draft 10‑slide deck                                  | 3 h              |
| **D9**           | Record Demo            | 3‑min Loom / OBS walkthrough; upload to Drive                                                    |                  |
| **D10 (Submit)** | QA & Submission        | Double‑check links; submit Build Challenge                                                       | 4 h contingency  |

