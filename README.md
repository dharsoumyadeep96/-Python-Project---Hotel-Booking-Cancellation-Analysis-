# 🏨 Hotel Booking Cancellations Analysis

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Data Analysis](https://img.shields.io/badge/Analysis-Pandas-green.svg)](https://pandas.pydata.org/)
[![Visualization](https://img.shields.io/badge/Viz-Matplotlib-orange.svg)](https://matplotlib.org/)

> **End-to-End Python Data Analysis Project**  
> Analyzing hotel booking cancellations to reduce revenue leakage and optimize operational efficiency in the hospitality domain.


## Video Presetation :- https://youtu.be/uXmJi6ssP6w?si=NaANEiJArl1v7Oti

## 📊 Project Overview

This project addresses the critical business problem of high cancellation rates affecting both City Hotels (41.7%) and Resort Hotels (27.8%). Through comprehensive data analysis of 118,897 booking records, we identify key drivers of cancellations and provide actionable strategic recommendations.

### Key Findings

- **Overall Cancellation Rate**: 37.1% (44,224 cancelled bookings)
- **Revenue at Risk**: Cancelled bookings average $109 ADR vs. $97 for retained bookings (12% premium)
- **Critical Risk Factor**: Bookings made >90 days in advance have >50% cancellation rate
- **Channel Dependency**: 47.4% of bookings come through OTAs (high-risk channel)
- **Market Concentration**: 70% of cancellations originate from Portugal

### Business Impact

- **Projected Revenue Recovery**: $1.5M annually
- **Target Cancellation Rate**: Reduce from 37.1% to ~29%
- **Direct Booking Goal**: Increase from 11.7% to 20%

## 🎯 Strategic Solutions

### 1. Risk-Based Deposit Policies (Priority: HIGH)
- Require non-refundable deposits for bookings >90 days in advance
- Stricter cancellation windows for City Hotels (41.7% fail rate)
- **Expected Impact**: 85% reduction in high-risk cancellations

### 2. Dynamic Pricing Engine (Priority: HIGH)
- Risk-adjusted ADR: 5-8% rate reductions for high-risk profiles
- Last-minute packages (7-14 days out) to refill cancelled inventory
- Peak season value-add bundles instead of discounting

### 3. Channel & Loyalty Optimization (Priority: MEDIUM)
- Grow direct bookings from 11.7% to 20% in 12 months
- Launch loyalty program targeting 96.8% first-time guest base
- Reduce OTA dependency (currently 47.4%)

## 📁 Project Structure

```
hotel-booking-analysis/
│
├── data/
│   ├── raw/                    # Original hotel booking data
│   ├── processed/              # Cleaned and transformed data
│   └── README.md               # Data dictionary and sources
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_eda_analysis.ipynb
│   ├── 04_statistical_testing.ipynb
│   └── 05_visualizations.ipynb
│
├── src/
│   ├── __init__.py
│   ├── data_processing.py      # Data cleaning and preprocessing
│   ├── analysis.py             # Statistical analysis functions
│   ├── visualization.py        # Plotting and charting functions
│   └── utils.py                # Helper functions
│
├── reports/
│   ├── figures/                # Generated plots and charts
│   ├── presentation.pdf        # Final presentation deck
│   └── executive_summary.md    # Business-focused summary
│
├── tests/
│   ├── test_data_processing.py
│   ├── test_analysis.py
│   └── test_visualization.py
│
├── requirements.txt            # Project dependencies
├── setup.py                    # Package installation
├── .gitignore                  # Git ignore rules
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Contribution guidelines
└── README.md                   # This file
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Jupyter Notebook (optional, for interactive analysis)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/dharsoumyadeep96/hotel-booking-analysis.git
   cd hotel-booking-analysis
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Install the package** (optional)
   ```bash
   pip install -e .
   ```

### Quick Start

```python
from src.data_processing import load_and_clean_data
from src.analysis import calculate_cancellation_rate
from src.visualization import plot_cancellation_trends

# Load data
df = load_and_clean_data('data/raw/hotel_bookings.csv')

# Analyze cancellation rates
cancellation_stats = calculate_cancellation_rate(df)
print(f"Overall cancellation rate: {cancellation_stats['overall_rate']:.1%}")

# Visualize trends
plot_cancellation_trends(df, save_path='reports/figures/cancellation_trends.png')
```

## 📈 Analysis Workflow

### 1. Data Exploration
- 118,897 verified booking records (July 2015 - August 2017)
- 32 features including booking details, customer info, and pricing

### 2. Data Cleaning
- Removed outlier ADRs >$5,000
- Excluded invalid 0-guest bookings
- Dropped columns with excessive missing data

### 3. Statistical Validation
- **Chi-square Test**: Confirmed Hotel Type/Cancellation correlation (p < 0.001)
- **T-test**: Confirmed ADR significance in cancellation behavior

### 4. Key Insights

#### Price Sensitivity
- Cancelled bookings average 12% higher ADR
- Clear inverse relationship between price and retention

#### Lead Time Risk
- <30 days: High retention (safe zone)
- 30-90 days: Moderate risk
- >90 days: DANGER ZONE (>50% cancellation rate)

#### Seasonality Patterns
- **January**: High cancellation spike despite lower volume
- **August**: Best retention with highest premiums ($115+ ADR)
- Peak season guests are value-resilient

## 📊 Key Visualizations

All visualizations are available in the `reports/figures/` directory:

- `cancellation_by_hotel_type.png` - City vs Resort comparison
- `adr_price_sensitivity.png` - Price-cancellation correlation
- `lead_time_analysis.png` - Booking window risk assessment
- `seasonal_patterns.png` - Monthly trends and ADR dynamics
- `channel_distribution.png` - Booking source analysis

## 🛠️ Technologies Used

- **Python 3.8+**: Core programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib**: Static visualizations
- **Seaborn**: Statistical data visualization
- **Jupyter**: Interactive development

## 📊 Dataset

**Source**: Hotel booking data from July 2015 to August 2017  
**Size**: 118,897 verified records  
**Features**: 32 attributes including:
- Hotel type (City/Resort)
- Cancellation status
- Lead time
- Average Daily Rate (ADR)
- Distribution channel
- Country of origin
- Guest demographics
- Booking modifications

*Note*: Due to data privacy, the raw dataset is not included in this repository. Sample data structure is available in `data/README.md`.

## 🎯 Implementation Roadmap

### Phase 1: Immediate (0-30 Days)
- ✅ Implement risk-based deposit rules for >90 day lead bookings

### Phase 2: Short-term (1-3 Months)
- Direct booking campaign & loyalty pilot
- A/B test deposit policy effectiveness

### Phase 3: Medium-term (3-6 Months)
- Deploy dynamic pricing engine
- City Hotel-specific engagement campaigns

### Phase 4: Long-term (6-12 Months)
- Machine learning predictive cancellation models
- Automated revenue optimization system

## 📧 Contact

**Soumyadeep Dhar**  
Data Analyst | Virtual Intern at AtliQ Technologies

- 📧 Email: soumyadeepdhar433@gmail.com
- 💼 LinkedIn: www.linkedin.com/in/soumyadeep-dhar-785724333
- 🐙 GitHub: [@dharsoumyadeep96](https://github.com/dharsoumyadeep96)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 🙏 Acknowledgments

- AtliQ Technologies for the virtual internship opportunity
- The hospitality industry data providers
- Open-source Python data science community

## 📚 References

- Hotel booking demand datasets and industry benchmarks
- Revenue management best practices in hospitality
- Statistical methods for business analytics

---

**Note**: This is an educational project demonstrating end-to-end data analysis skills in Python, focusing on real-world business problem-solving in the hospitality domain.

⭐ If you find this project useful, please consider giving it a star!

