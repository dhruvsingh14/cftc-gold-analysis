# CFTC Commitments of Traders (COT) API Demo - Net Positioning
# Case: Gold Futures

## Overview:
This project analyzes **CFTC Commitments of Traders (COT)** data for **Gold futures**, focusing on how different trader categories - Money Managers, Swap Dealers, Producer / Merchants - position themselves over time.

### Why this matters:
COT positioning is widely used by macro investors, commodity traders, quantitative researchers. Net positioning helps identify speculative crowding, hedging pressure, structural shifts in market participation.

## Data
- U.S. Commodity Futures Trading Commission (CFTC)
- Commitments of Traders - Disaggregated Futures Only Report via the Socrata API
  - url: `https://publicreporting.cftc.gov/`

## Methods


This project uses the CFTC public API (Socrata / SODA) to retrieve weekly Commitments of Traders data from the *Disaggregated Futures Only* report. The analysis focuses on Gold futures as an exaple, cleaning and structuring the data to compute net positions (long − short) by trader category and visualize positioning trends over time.

- Retrieve regulatory futures data via unauthenticated API requests  
- Filter to Gold futures contracts  
- Clean and preprocess weekly positioning data  
- Engineer net exposure metrics for:
  - Producer / Merchant  
  - Swap Dealers  
  - Managed Money  
- Visualize net positioning and open interest through time

## Results

When Managed Money net positioning rises sharply, Producers and Swap Dealers often take the other side.

![Gold net positioning](assets/gold_net_positions.png)


## Repository structure
```text
.
├── notebooks/
│ └── cftc_api_demo.ipynb # analysis
├── data/
│ └── cftc_gold_cache.csv # cached data
├── assets/
│ └── gold_net_positions.png
├── README.md
└── LICENSE
```

## Limitations and Next Steps

Future extensions:
- Parameterize commodity selection (any CFTC contract) using user input.
- Normalize positioning by open interest
- Add z-score / percentile-based positioning signals


