# ✈️ Flight Delay Patterns Analysis

![SQL](https://img.shields.io/badge/SQL-Analysis-orange)

Analysis of 7+ million domestic flight records from 2024 to uncover systematic delay patterns and inform smarter travel decisions.

## Key Findings

- **Cascade Effect**: Delays triple throughout the day—morning flights average 2.73 min late aircraft delays, escalating to 10.13 min by evening
- **Route Performance**: Regional-to-regional routes outperform hub routes (82.76% vs 78.32% on-time)
- **Weekly Patterns**: Friday is the worst travel day (14.59 min avg delay); Tuesday/Wednesday offer best reliability
- **Holiday Impact**: MLK Day shows severe delays (33.09 min avg), while Thanksgiving surprisingly outperforms regular days
- **Hub Congestion**: NAS delays nearly double at major hubs (3.48 min) compared to regional airports (1.76 min)

## Research Questions

This project investigated four critical questions:

1. **How do delays build up throughout the day?**
   - Examined morning, afternoon, evening, and night flight patterns
   - Identified late aircraft delays as the primary cascade mechanism

2. **How do delay patterns differ by route type?**
   - Analyzed hub-to-hub, hub-to-regional, and regional-to-regional routes
   - Found that hub congestion drives significantly worse performance

3. **How do holidays impact flight delays?**
   - Compared 7 major US holidays against regular travel days
   - Discovered winter weather is a bigger factor than passenger volume

4. **Which day of the week has the worst delays?**
   - Ranked all seven days by delay severity
   - Identified mid-week travel windows with optimal reliability

## Dataset

- **Source**: [2024 Flight Delays and Cancellations on Kaggle]((https://www.kaggle.com/datasets/hrishitpatil/flight-data-2024/data?select=flight_data_2024.csv))
- **Time Period**: January - December 2024
- **Size**: 7+ million rows × 35 columns
- **Content**: Scheduled/actual times, delays by cause, cancellations, diversions, distances

### Data Access
The raw dataset is **not included** in this repository due to its size (~2GB). 

**To replicate this analysis**:
1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/hrishitpatil/flight-data-2024/data?select=flight_data_2024.csv)
2. Place the CSV file in the `data/` directory
3. Run `analysis.ipynb`

The dataset includes:
- Snake_case column standardization
- ISO-formatted dates
- Binary indicators for cancellations/diversions
- Zero-filled missing delay values

**To replicate this analysis**:
1. Download 2024 On-Time Performance data from BTS TranStats
2. Place CSV file in `data/` directory
3. Run `analysis.ipynb`

The dataset was cleaned with:
- Snake_case column standardization
- ISO-formatted dates
- Binary indicators for cancellations/diversions
- Zero-filled missing delay values

## Technologies

- **Python 3.x**: Data processing and analysis
- **SQL**: Complex queries for aggregation and pattern detection
- **Jupyter Notebook**: Interactive analysis environment
- **Pandas**: Data manipulation
- **NumPy**: Numerical operations

## Repository Structure

flight-delay-analysis/

├── [README.md](http://README.md)                                          # You are here

├── analysis.ipynb                                     # SQL queries and data processing

├── Flight_Delay_Patterns_Analysis_Final_Report.pdf   # Full report with visualizations

├── data/

│   └── [README.md](http://README.md)                                      # Dataset download instructions

└── .gitignore                                         # Excludes large data files

### Running the Analysis
1. Clone this repository
2. Download the dataset (see `data/README.md`)
3. Open `analysis.ipynb` in Jupyter Notebook
4. Run all cells to reproduce results

## Analysis Methodology

Each research question was approached systematically:

- **Time-based analysis**: Flights categorized into 4 departure windows
- **Route classification**: 36 major hub airports identified; routes classified via SQL JOINs
- **Holiday detection**: 6-day windows (3 days before through 2 days after) for 7 major holidays
- **Weekly patterns**: Aggregate functions with window functions for day-over-day comparison

All metrics include departure delay, arrival delay, late aircraft delay, carrier delay, weather delay, NAS delay, and on-time percentage.

## Practical Applications

**For Travelers**:
- Book morning flights to avoid cascade delays
- Choose Tuesday/Wednesday for most reliable service
- Avoid MLK Day and Memorial Day travel periods
- Consider regional airports when possible

**For Airlines**:
- Morning schedule optimization reduces evening compounding
- Hub congestion mitigation could improve system-wide performance
- Weather contingency planning critical for January travel

## License

MIT License - feel free to use this analysis for your own projects!

## Author

**Erin Morgenthaler**
- GitHub: [@ErinMor](https://github.com/ErinMor)
- Email: erin.morgenthaler@gmail.com

## Acknowledgments

- Bureau of Transportation Statistics for maintaining comprehensive flight data
- University of Iowa for academic support

