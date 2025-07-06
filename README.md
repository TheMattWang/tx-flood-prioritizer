# Texas Flood Prioritizer

> Real-time impact prioritization system for climate-driven disasters, starting with flood prediction in South Texas.

## Problem Statement

Extreme weather events are accelerating, yet response teams still rely on static maps, disjoint dashboards, and intuition. This project aims to fuse live hazard forecasts with infrastructure and population layers to rank impact zones in minutes—starting with floods in South Texas.

## Geographic Scope

The initial implementation focuses on six high-risk Texas counties:
- Harris
- Fort Bend
- Brazoria
- Galveston
- Nueces
- Hidalgo

## Core Features

- **Real-time Data Integration**: 
  - NOAA Stage-IV radar rainfall (5 min updates)
  - USGS river gauges
  - USGS 1-m LiDAR elevation
  - HUD HIFLD critical-infrastructure shapefiles
  - 2020 census block-level population

- **Predictive Modeling**:
  - 0-, 6-, and 12-hour flood predictions
  - 250m hex-cell resolution (H3 resolution 8)
  - Impact Index calculation: `FloodDepth(mm) × PopDensity × CriticalInfraWeight`

- **API & Visualization**:
  - FastAPI endpoint for risk assessment
  - Interactive map interface with hex-cell heat layers
  - Critical infrastructure overlays
  - Real-time updates every 5 minutes

## Success Metrics

| Metric | Target |
|--------|---------|
| High-Damage Hit Rate | ≥80% identified 6h ahead |
| Mean Lead Time | ≥6 hours |
| Pipeline Latency | <5 minutes |
| Data Join Success Rate | >99% |

## Primary Beneficiaries

- Emergency Operations Centers (city, county, national)
- Utilities & telecoms
- Insurers & reinsurers
- NGOs & mutual-aid networks
- Residents & businesses in climate-vulnerable corridors

## Technical Stack

- **Backend**:
  - FastAPI for REST endpoints
  - LightGBM/CNN for flood prediction
  - Airflow for ETL pipelines
  - Parquet for data storage

- **Frontend**:
  - Leaflet + Deck.gl for mapping
  - Real-time visualization layers

## Future Extensions

- Storm surge modeling for coastal areas
- Text-alert system integration (Twilio)
- Dashboard auto-refresh capabilities
- Extension to other disaster types (wildfire, hurricane winds, extreme heat)

## Development Timeline

11-day sprint plan covering:
1. Data ingestion
2. ETL pipeline development
3. Core flood modeling
4. Infrastructure overlay integration
5. API development
6. Frontend implementation
7. Validation and testing
8. Documentation and demo

## Getting Started

[Coming soon - Development setup instructions]

## Contributing

[Coming soon - Contribution guidelines]

## License

[Coming soon - License information] 