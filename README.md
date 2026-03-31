# Hotel Booking Cancellation Dashboard

Interactive Streamlit dashboard for analyzing hotel booking cancellations.

## Quick Start

```bash
pip install -r requirements.txt
streamlit run hotel_dashboard.py
```

## Features

- 📈 **Univariate Analysis** - Individual variable distributions
- 🔄 **Bivariate Analysis** - Relationships between variables
- 🎯 **Multivariate Analysis** - Complex patterns and interactions
- 💡 **Key Insights** - Business recommendations
- 📋 **Data Summary** - Statistical overview

## Data

Place your `hotel_bookings.csv` in a `data/` folder:

```
project/
├── hotel_dashboard.py
├── requirements.txt
├── README.md
└── data/
    └── hotel_bookings.csv
```

If no CSV found, dashboard uses sample data.

## Required Columns

Your CSV should have:
- `is_canceled` (0/1)
- `lead_time` (integer)
- `adr` (room price)
- `total_nights` (integer)
- `total_guests` (integer)
- `hotel_type` (string)
- `market_segment` (string)
- `arrival_month` (string)
- `total_of_special_requests` (integer)

## Deploy

Push to GitHub and deploy on Streamlit Cloud for public link.

## Component 3

This dashboard fulfills all requirements for Project Component 3.
