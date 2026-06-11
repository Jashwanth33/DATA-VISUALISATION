# Data Visualization Dashboard

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://javascript.com)
[![D3.js](https://img.shields.io/badge/D3.js-7+-F9A03C?style=for-the-badge&logo=d3.js&logoColor=white)](https://d3js.org)
[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

> Interactive data visualization dashboard with real-time analytics and beautiful charts.

## Architecture

`mermaid
graph TB
    subgraph "Frontend"
        D3[D3.js Charts]
        Plotly[Plotly.js]
        Chart[Chart.js]
        Dashboard[Dashboard UI]
    end

    subgraph "Backend"
        Flask[Flask Server]
        DataProcessor[Data Processor]
        Cache[Redis Cache]
    end

    subgraph "Data Sources"
        CSV[CSV Files]
        API[REST APIs]
        DB[(Database)]
    end

    Dashboard --> D3
    Dashboard --> Plotly
    Dashboard --> Chart
    D3 --> Flask
    Plotly --> Flask
    Chart --> Flask
    Flask --> DataProcessor
    DataProcessor --> CSV
    DataProcessor --> API
    DataProcessor --> DB
    Flask --> Cache
`

## Data Flow

`mermaid
flowchart TD
    A[User Uploads Data] --> B{Data Format}
    B -->|CSV| C[CSV Parser]
    B -->|JSON| D[JSON Parser]
    B -->|API| E[API Fetcher]
    
    C --> F[Data Validation]
    D --> F
    E --> F
    
    F --> G[Data Transformation]
    G --> H[Statistics Calculator]
    G --> I[Aggregation Engine]
    
    H --> J[Chart Generator]
    I --> J
    
    J --> K{Visualization Type}
    K -->|Bar| L[Bar Chart]
    K -->|Line| M[Line Chart]
    K -->|Pie| N[Pie Chart]
    K -->|Scatter| O[Scatter Plot]
    K -->|Heatmap| P[Heatmap]
    
    L --> Q[Interactive Dashboard]
    M --> Q
    N --> Q
    O --> Q
    P --> Q
`

## Chart Types

`mermaid
pie title Chart Distribution
    "Bar Charts" : 25
    "Line Charts" : 30
    "Pie Charts" : 15
    "Scatter Plots" : 15
    "Heatmaps" : 10
    "Other" : 5
`

## Project Structure

`
DATA-VISUALISATION/
├── app.py                      # Flask application
├── config.py                   # Configuration
├── requirements.txt            # Dependencies
│
├── static/
│   ├── css/
│   │   ├── dashboard.css       # Dashboard styles
│   │   └── charts.css          # Chart styles
│   ├── js/
│   │   ├── charts/
│   │   │   ├── barChart.js     # Bar chart component
│   │   │   ├── lineChart.js    # Line chart component
│   │   │   ├── pieChart.js     # Pie chart component
│   │   │   ├── scatterPlot.js  # Scatter plot component
│   │   │   └── heatmap.js      # Heatmap component
│   │   ├── dashboard.js        # Dashboard logic
│   │   ├── dataLoader.js       # Data loading
│   │   └── utils.js            # Utilities
│   └── images/
│
├── templates/
│   ├── base.html               # Base template
│   ├── dashboard.html          # Main dashboard
│   ├── upload.html             # Data upload page
│   └── charts.html             # Chart gallery
│
├── data/
│   ├── sample/                 # Sample datasets
│   └── uploads/                # User uploads
│
├── processors/
│   ├── __init__.py
│   ├── csv_processor.py        # CSV processing
│   ├── json_processor.py       # JSON processing
│   ├── data_transformer.py     # Data transformation
│   └── statistics.py           # Statistical calculations
│
├── generators/
│   ├── __init__.py
│   ├── chart_generator.py      # Chart generation
│   ├── report_generator.py     # Report generation
│   └── export.py               # Export functionality
│
├── tests/
│   ├── test_processors.py
│   └── test_charts.py
│
├── docs/
│   ├── API.md
│   ├── CHARTS.md
│   └── DEPLOYMENT.md
│
└── README.md
`

## Features

| Feature | Description | Technology |
|---------|-------------|------------|
| Interactive Charts | Zoom, pan, hover effects | D3.js |
| Real-time Updates | Live data streaming | WebSocket |
| Multiple Formats | CSV, JSON, API support | Flask |
| Export Options | PNG, SVG, PDF export | Plotly |
| Dark Mode | Theme switching | CSS Variables |
| Responsive | Mobile-friendly design | Bootstrap |

## Installation

`ash
git clone https://github.com/Jashwanth33/DATA-VISUALISATION.git
cd DATA-VISUALISATION

python -m venv venv
source venv/bin/activate

pip install -r requirements.txt
python app.py
`

## Usage

1. Open http://localhost:5000
2. Upload your dataset (CSV/JSON)
3. Select visualization type
4. Customize colors and labels
5. Export or share your charts

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | / | Dashboard home |
| POST | /upload | Upload dataset |
| GET | /api/data | Get processed data |
| GET | /api/charts/<type> | Generate chart |
| POST | /export | Export visualization |

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT License

## Author

**Jashwanth** - [GitHub](https://github.com/Jashwanth33)