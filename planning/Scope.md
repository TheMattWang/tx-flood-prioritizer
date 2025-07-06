### Scoping the Build Challenge to **South Texas**

Below is a crisp scope definition you can reference while building—tight enough to finish in ~11 days, but rich enough to impress Palantir reviewers.

|Dimension|Scope Decision|Rationale|
|---|---|---|
|**Geography**|**Six high-risk counties:** Harris, Fort Bend, Brazoria, Galveston, Nueces, and Hidalgo|Concentrates on the coastal / river-delta counties hit hardest by the 2025 floods; keeps data volumes manageable.|
|**Time Horizon**|**0-, 6-, 12-hour predictions**|Short enough to be actionable for first responders; achievable with public forecast APIs.|
|**Hazard**|**Fresh-water flooding** (flash + riverine)|Matches recent disaster; easier data (radar rainfall, river gauges). Storm-surge modeling is optional stretch.|
|**Data Layers**|1. NOAA Stage-IV radar rainfall (5 min) ↔ 2. USGS river gauges ↔ 3. USGS 1-m LiDAR elevation ↔ 4. HUD HIFLD critical-infrastructure shapefiles ↔ 5. 2020 census block-level population|All freely available, no paywalls; can ingest via REST or static S3.|
|**Output Unit**|**250 m hex-cells** (H3 resolution 8)|Good balance between spatial detail and compute cost; locks to Palantir’s H3-friendly ecosystem.|
|**Priority Score (“Impact Index”)**|`FloodDepth(mm) × PopDensity × CriticalInfraWeight`|Simple, explainable metric that blends hazard + exposure.|
|**MVP Deliverables** (P0)|• ETL pipeline → feature store (Parquet)  <br>• LightGBM or simple CNN flood-depth predictor  <br>• FastAPI endpoint: `/risk?time=6h` returns top 100 hex-cells  <br>• Foundry-style map mock-up (e.g., Kepler.gl screenshot)|Covers ingest, model, API, visualization—end-to-end story.|
|**Stretch (P1)**|• Text-alert prototype (Twilio)  <br>• Dashboard auto-refresh every 5 min  <br>• Add storm-surge layer for coastal cells|Only if time allows—makes demo sizzle.|