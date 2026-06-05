# GTM Regulatory Outlook

Quarterly regional regulatory briefings for Chainalysis Account Executives.

**[Browse the archive →](https://jordan-wain.github.io/regulatory-outlook/)**

**[Internal dashboard →](https://jordan-wain.github.io/regulatory-outlook/internal/dashboard.html)**

## What is this?

The GTM Regulatory Outlook is an AI-generated quarterly briefing that translates policy events into sales-ready intelligence. Each edition covers:

- **Sub-regional breakdown** with country-specific regulatory developments
- **Regulator watch table** mapping regulators to product plays
- **Pipeline opportunities** with estimated deal sizes
- **90-day forward look** with key dates and actions

## Regions

| Region | Sub-regions | Coverage |
|--------|------------|----------|
| **APAC** | Northeast Asia, Southeast Asia, South Asia, Oceania | 13 countries, 12 regulators |
| **EMEA** | (coming soon) | UK, EU, MEA |
| **NAM** | — | USA, Canada |
| **Global** | — | Cross-regional synthesis |

## How it works

The [`gtm-regulatory-outlook`](https://dialog.chainalysis.com/workflows/gtm-regulatory-outlook) workflow:

1. Reads the **Policy Event Tracker** spreadsheet (primary data source)
2. Pulls intelligence from **media-monitor**, **competitor-intel-monitor**, and **natsec-media-monitor** workflows
3. Finds the previous quarter's edition for delta tracking
4. Generates **regional editions** with Claude (sub-region grouped for APAC)
5. Creates formatted **Google Docs**
6. Publishes to **Confluence**
7. Pushes structured data + HTML briefings to **this repo**
8. Distributes summary via **Slack**

## Repository structure

```
├── index.html                    # Archive browser (GitHub Pages)
├── data/
│   └── outlook-data.json         # Rolling edition metadata for the archive UI
├── editions/
│   ├── 2026-Q2-APAC.html        # Self-contained HTML briefing
│   ├── 2026-Q2-APAC.json        # Structured edition data
│   └── ...
└── internal/
    └── dashboard.html            # Cross-regional comparison dashboard
```

## Configuration

Regional configuration (countries, sub-regions, regulators, RSS feeds, Google News searches) is maintained in [`region_config.json`](https://dialog.chainalysis.com/workflows/gtm-regulatory-outlook) within the workflow package. To add a country or regulator, update the config — no code changes needed.

<!-- Pages build trigger: 2026-06-05T10:22:07.677703+00:00 -->
