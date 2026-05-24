# Timeless Compass Explorer 2.0

**An interactive digital research library and evidence exploration platform**
built for the Sri Sri Institute for Advanced Research (SSIAR).

> *"More than a publication database — a guided research compass helping users orient themselves within the evidence base, identify meaningful research patterns, and efficiently reach the precise studies they wish to explore in full."*

---

## Live Demo

🔗 **[timeless-compass-explorer-2.github.io](https://lakshmiganesan.github.io/timeless-compass-explorer-2/)**

---

## What is this?

Timeless Compass Explorer 2.0 is an interactive evidence map of published research on **Ancient Systems of Knowledge** — including yoga, meditation, pranayama, and Ayurveda. It connects ancient wisdom traditions with modern scientific inquiry through a layered, visual exploration interface.

The platform is designed for a broad audience:

- **Researchers and students** — navigating the evidence base in depth through database search, filtering, and direct access to published papers
- **Institutional leadership and policymakers** — understanding research scale, thematic strengths, geographic reach, and evidence trends at a strategic level
- **Partners and public audiences** — exploring the evidence landscape through an approachable, visually driven interface

The entire dashboard is a **single self-contained HTML file**. No build step, no framework, no server. Open it in a browser and it works.

---

## The Exploration Architecture

The interface follows a three-layer progressive exploration model — moving from strategic overview to individual study access:

```
📊  MACRO VIEW      Understand the research landscape and trends
        ↓
📋  MESO VIEW       Compare and navigate studies within the database
        ↓
🔬  MICRO VIEW      Preview key details of a selected study
        ↓
🔗  LINK TO PUBLISHED STUDY     Access the original publication
```

This architecture supports progressive disclosure — users can engage at whatever depth suits their purpose, from a high-level strategic overview to direct access to the original published source.

---

## Features

### 📊 Macro View — Evidence Landscape

The top layer provides a bird's-eye view of the evidence base:

| Component | Description |
|---|---|
| **7 Scorecards** | Selected studies · % of total · year range · countries · continents · independent research % · languages — all update dynamically with every filter |
| **Explore by Year** | Interactive bar chart of publication volume 1997–2026; click any bar to filter |
| **Explore by Topics & Subtopics** | Nested concentric chart — inner pie shows 3 major topic domains (MH / PH / SH), outer donut shows 19 subtopics; click any segment to filter |
| **Geo-distribution of Authors** | Proportional bubble world map (no choropleth); bubble size = publication count per country; click any bubble to filter |
| **Explore by Partnerships** | Horizontal bar chart across Independent, Collaborative, and Internal research; click to filter |
| **Active Filters strip** | All applied filters shown as removable chips, regardless of origin (search, dropdowns, or chart clicks) |

All four charts are interconnected — any interaction updates every other component simultaneously.

### 📋 Meso View — Database Exploration

The middle layer is the comparative database browsing layer:

- Sortable table: **#  ·  Type  ·  Title  ·  Citation  ·  Journal / Source**
- **Clickable titles** — when a published URL exists, hovering reveals an external link icon; clicking opens the paper directly in a new tab without leaving the Explorer
- Pagination with configurable rows per page (10 / 25 / 50)
- Fully responsive to all active filters
- Mobile: displayed as a scrollable list with a "Tap a row to preview the study" affordance

### 🔬 Micro View — Selected Study Panel

The right-hand panel (desktop) or bottom sheet (mobile) provides a focused preview of any selected study:

- Study title · Authors/Year · Journal · Study Design · Country · Intervention · Topics · Subtopics · Abstract
- **Link to Published Study** CTA — always pinned at the bottom of the panel, never hidden by scroll, acting as the gateway to the original source

### Search & Filter

- **Global search** — title, abstract, author, citation, journal, country, topics, subtopics, and interventions
- **Advanced Search** — compact dropdown panel with 8 structured filters: Topic · Subtopic · Population · Intervention · Partnership · Language · Year · Country
- **Reset Filters** — clears all filters and search in one click
- All filters are interconnected: any combination of search, dropdown filters, and chart interactions updates every component simultaneously

---

## Responsive Design

| Breakpoint | Layout |
|---|---|
| **Desktop** `≥ 1200px` | Full 4-column chart row · 7 scorecards · side-by-side Meso + Micro panels |
| **Tablet** `960–1200px` | 2-column charts · 4 scorecards · stacked panels |
| **Mobile** `< 960px` | Tab bar navigation (Macro / Meso / Micro / Filters) · selected study opens as bottom sheet · filter drawer slides in from left |
| **Small mobile** `< 640px` | 1-column charts · 2 scorecards · compact controls |

### Mobile Interaction Flow

```
Macro tab  →  Evidence overview (scorecards + charts)
    ↓
Meso tab   →  Database list (scrollable, tap-to-preview)
    ↓
Tap a row  →  Study bottom sheet slides up (Micro View)
    ↓
Link to Published Study  →  Opens original paper in new tab
    ↓
← Back to Database  →  Sheet closes, returns to database list
```

---

## Dataset

| Metric | Value |
|---|---|
| Total publications | **248** |
| Year range | **1997 – 2026** |
| Countries | **23** across 6 continents |
| Languages | English · Spanish · Tamil |
| Independent research | **75%** |
| Records with published URL | **248 / 248** |

### Research Domains

| Code | Topic | Subtopics |
|---|---|---|
| **MH** | Mental Health | Anxiety & Depression · Stress · Brain · Sleep · Happiness |
| **PH** | Physical Health | Breath / Lungs · Heart · Biomarkers · Immunity · Cancer · Gut Health · Cognition · Diabetes · Genes · Vagus Nerve · Women · Youth · At-Risk Communities |
| **SH** | Social Health | Environment |

### Interventions Covered

| Intervention | Abbreviation |
|---|---|
| Sudarshan Kriya Yoga | SKY |
| Sahaj Samadhi Meditation | SSM |
| Advanced Meditation Programme | AMP |
| The Intuition Programme | IP |
| Yoga | — |
| Ayurveda | — |
| Gut Health | — |
| Other | — |

### Partnership Categories

| Category | Meaning |
|---|---|
| **Independent** | Research conducted without institutional affiliation to SSIAR |
| **Collaborative** | Joint research with external institutions |
| **Internal** | SSIAR-led research |

### Reference Types

Research Article · Journal Article · Review Article · Conference Proceedings · Book Section · Study Protocol · Editorial · Letter · Report

### Geographic Coverage

**Countries (23):** Australia · Canada · Colombia · Finland · Hungary · India · Ireland · Italy · Japan · Mexico · Nepal · Netherlands · Norway · Poland · Portugal · South Africa · Sweden · Thailand · Turkey · Ukraine · United Arab Emirates · United Kingdom · United States

**Continents (6):** Africa · Asia · Europe · North America · Oceania · South America

---

## Technical Stack

| Component | Technology |
|---|---|
| Interface | Vanilla HTML + CSS + JavaScript (ES6+) |
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) |
| World Map | [D3.js 7.9](https://d3js.org/) + [TopoJSON 3.0](https://github.com/topojson/topojson) |
| Map Geodata | [world-atlas 2 (110m)](https://github.com/topojson/world-atlas) via jsDelivr CDN |
| Typography | [Spectral](https://fonts.google.com/specimen/Spectral) · [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) via Google Fonts |
| Data | Embedded JSON (generated from CSV via the SSIAR curation pipeline) |
| Hosting | GitHub Pages |

**Zero dependencies to install. Zero build step. One file.**

---

## Project Structure

```
timeless-compass-explorer-2/
│
├── index.html          # Complete self-contained dashboard (all data embedded)
├── README.md           # This file
└── data/
    └── TC_Explorer.csv # Source dataset (EndNote → structured CSV)
```

---

## Data Pipeline

The underlying research curation workflow is unchanged from Timeless Compass Explorer 1.0:

```
EndNote Export  →  Structured CSV  →  Timeless Compass Explorer 2.0
```

This means the backend research workflow and curation pipeline remain fully stable, while the frontend experience is dynamic and website-ready.

### Updating the Dataset

When a new CSV export is ready, run the following Python script to regenerate the embedded JSON:

```python
import pandas as pd
import json

TOPIC_MAP = {
    'MH': 'Mental Health',
    'PH': 'Physical Health',
    'SH': 'Social Health'
}

CONTINENT_MAP = {
    'India': 'Asia', 'United States': 'North America', 'Canada': 'North America',
    'United Kingdom': 'Europe', 'Italy': 'Europe', 'United Arab Emirates': 'Asia',
    'Poland': 'Europe', 'Norway': 'Europe', 'Ireland': 'Europe', 'Nepal': 'Asia',
    'Sweden': 'Europe', 'Finland': 'Europe', 'Portugal': 'Europe',
    'Netherlands': 'Europe', 'Thailand': 'Asia', 'Colombia': 'South America',
    'Hungary': 'Europe', 'Japan': 'Asia', 'South Africa': 'Africa',
    'Mexico': 'North America', 'Turkey': 'Asia', 'Australia': 'Oceania',
    'Germany': 'Europe',
    # Add new countries here as needed
}

def clean(v):
    s = str(v).strip()
    return '' if s in ('', 'nan', 'NaN') else s

def parse_ts(val):
    if not val or str(val).strip() in ('', 'nan'):
        return []
    out = []
    for p in [p.strip() for p in str(val).split(',')]:
        if ' - ' in p:
            pre, sub = p.split(' - ', 1)
            out.append({
                'topic': TOPIC_MAP.get(pre.strip(), pre.strip()),
                'subtopic': sub.strip()
            })
    return out

df = pd.read_csv('data/TC_Explorer.csv')
records = []

for _, r in df.iterrows():
    ts       = parse_ts(r.get('Topic - Subtopic', ''))
    topics   = list(dict.fromkeys([x['topic'] for x in ts]))
    subtopics= list(dict.fromkeys([x['subtopic'] for x in ts]))
    ints     = [i.strip() for i in clean(r.get('Interventions','')).split(',') if i.strip()]
    pops     = [p.strip() for p in clean(r.get('Study Population','')).split(',') if p.strip()]
    year     = int(r['Year']) if not pd.isna(r.get('Year')) else None
    author   = clean(r.get('Author', ''))
    url      = clean(r.get('Link to Published Study', ''))

    records.append({
        'id':               int(r['Record Number']),
        'type':             clean(r.get('Type', '')),
        'author':           author,
        'year':             year,
        'citation':         f"{author}, {year}" if author and year else author or str(year or ''),
        'title':            clean(r.get('Title', '')),
        'journal':          clean(r.get('Journal / Source', '')),
        'url':              url if url.startswith('http') else '',
        'abstract':         clean(r.get('Abstract', '')),
        'study_design':     clean(r.get('Study Design', '')),
        'topic_subtopic_raw': clean(r.get('Topic - Subtopic', '')),
        'topics':           topics,
        'subtopics':        subtopics,
        'topic':            topics[0] if topics else '',
        'subtopic':         subtopics[0] if subtopics else '',
        'interventions':    ints,
        'intervention':     ints[0] if ints else '',
        'populations':      pops,
        'population':       pops[0] if pops else '',
        'partnership':      clean(r.get('Partnership', '')),
        'country':          clean(r.get('Country', '')),
        'continent':        CONTINENT_MAP.get(clean(r.get('Country', '')), 'Other'),
        'language':         clean(r.get('Language', '')),
        'affiliation':      clean(r.get('Author Affiliation', '')),
    })

with open('data.json', 'w', encoding='utf-8') as f:
    json.dump(records, f, ensure_ascii=False, separators=(',', ':'))

print(f"{len(records)} records written to data.json")
```

Then in `index.html`, find the line:

```js
const RAW = [...];
```

Replace the entire array with the contents of `data.json`. Commit and push — GitHub Pages deploys automatically.

---

## Design Language

The interface uses a **Research Observatory** visual theme:

| Element | Detail |
|---|---|
| Background | Warm ivory `#FDFAF3` — paper-like, calm, scholarly |
| Header | Deep indigo `#1A1840` with a subtle dot-grid texture and gold gradient hairline |
| Primary accent | Amber gold `#E8A020` — active states, highlights, CTA border, filter pills |
| Secondary accent | Jade green `#0D9E7A` — map bubbles, Collaborative bars |
| Display typeface | *Spectral* (serif) — titles, scorecards, study headings |
| Body typeface | *Plus Jakarta Sans* (geometric sans) — controls, data, labels |

The interface is intentionally **calm, exploratory, and research-oriented** — closer to a scholarly atlas or evidence observatory than a conventional KPI dashboard.

---

## Version History

| Version | Platform | Description |
|---|---|---|
| **1.0** | Google Looker Studio | Research dashboard and searchable publication index |
| **2.0** | Native HTML | Multi-layer evidence exploration platform with Macro / Meso / Micro architecture, interactive charts, world bubble map, full responsiveness, and direct website integration |

### Key Improvements in 2.0

| Area | 1.0 | 2.0 |
|---|---|---|
| Technology | Google Looker Studio | Native HTML — no dependencies |
| Website integration | Embedded dashboard | Direct native integration |
| User experience | Database-centric | Layered exploration flow |
| Strategic overview | Limited | Dedicated Macro View |
| Topic visualisation | Standard charts | Nested topic-subtopic concentric chart |
| Geographic view | Basic | Interactive global bubble map |
| Study inspection | Minimal | Dedicated Micro View with pinned CTA |
| Mobile | Limited | Fully responsive with tab navigation |
| Scalability | Dashboard-oriented | Future-ready research intelligence architecture |

---

## About SSIAR

The **Sri Sri Institute for Advanced Research (SSIAR)** is the research arm of the Art of Living Foundation. SSIAR curates and publishes scientific evidence on Ancient Systems of Knowledge — bridging classical wisdom traditions with modern scientific inquiry.

🔗 [research.artofliving.org](https://research.artofliving.org)

---

## License

The interface code is released under the **MIT License**.
The dataset is shared under **CC BY 4.0** — free to use and adapt with attribution.

© 2026 Sri Sri Institute for Advanced Research (SSIAR)
