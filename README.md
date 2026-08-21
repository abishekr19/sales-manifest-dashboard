# Sales Manifest Dashboard

An interactive sales analytics dashboard for exploring e-commerce order data — built with React and styled around a distinctive "freight manifest / packing-slip" visual theme rather than a generic admin-panel look.

![Status](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Made with React](https://img.shields.io/badge/made%20with-React-61DAFB?logo=react&logoColor=white)

## Overview

Sales Manifest Dashboard turns a large set of e-commerce orders into a single-page operations view. It combines revenue trend analysis, category breakdowns, a US regional tile-map, and a full sortable/filterable order ledger — all driven by a reactive filter bar so every chart, map, and table stays in sync with the current selection.

## Features

- **KPI summary** — total revenue, order count, average order value, and VIP customer share, recalculated live as filters change
- **Monthly revenue trend** — area chart showing seasonality across a 12-month window
- **Revenue by category** — horizontal bar breakdown across product categories
- **Regional performance tile-map** — a stylized US state grid, color-coded by revenue, clickable to filter the whole dashboard down to a single state
- **Order ledger** — a sortable, paginated, searchable table of individual orders (order ID, date, state, category, channel, segment, quantity, revenue)
- **Unified filtering** — a month-range scrubber, category/channel chips, and a search box that all filter every view simultaneously, with a one-click reset

## Tech Stack

- **React** (hooks: `useState`, `useMemo`)
- **Recharts** — area and bar charts
- **lucide-react** — icon set
- **Vite** — build tooling and dev server

## Getting Started

### Prerequisites
- Node.js 18+
- npm

### Installation

```bash
git clone https://github.com/abishekr19/sales-manifest-dashboard.git
cd sales-manifest-dashboard
npm install
```

### Run locally

```bash
npm run dev
```

The app will be available at `http://localhost:5173` (default Vite port).

### Build for production

```bash
npm run build
```

## Project Structure

```
sales-manifest-dashboard/
├── src/                  # Application source (dashboard component, styles)
├── index.html            # HTML entry point
├── vite.config.js        # Vite configuration
├── package.json
└── package-lock.json
```

## Data

The dashboard currently runs on a seeded, synthetically generated dataset (~7,500 orders spanning 12 months, multiple categories, channels, and US states) so it's fully self-contained and requires no backend or API keys to explore. The generation logic uses a deterministic seeded random number generator, so the same dataset loads on every run.

To connect it to real data, replace the `generateOrders()` function in the dashboard component with a fetch/import of your own order records, keeping the same field shape (`state`, `category`, `channel`, `segment`, `qty`, `revenue`, `monthIdx`, etc.).

## Roadmap

- [ ] Connect to a live data source / CSV import
- [ ] Export filtered results to CSV
- [ ] Add year-over-year comparison view
- [ ] Dark mode toggle

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

**Abishek R** — [GitHub](https://github.com/abishekr19)
