<<<<<<< HEAD
# Tunisia Real Estate Data Analysis

A comprehensive data scraping and analysis project for Tunisian real estate market, focusing on apartment listings from Mubawab.tn.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Data Pipeline](#data-pipeline)
- [Dataset Description](#dataset-description)
- [Contributing](#contributing)
- [License](#license)

## 🏠 Overview

This project scrapes, cleans, and analyzes real estate data from Tunisian property websites, primarily focusing on apartment listings. The pipeline extracts detailed property information including prices, locations, features, and specifications to create a structured dataset for analysis.

### Key Objectives

- Scrape apartment listings from Mubawab.tn
- Clean and structure the raw data for analysis
- Provide insights into the Tunisian real estate market
- Create a reusable data pipeline for ongoing market monitoring

## ✨ Features

- **Web Scraping**: Automated data extraction from Mubawab.tn using requests and BeautifulSoup
- **Data Cleaning**: Comprehensive preprocessing pipeline to handle inconsistent data formats
- **Feature Extraction**: Parse complex property details into structured columns
- **Location Processing**: Clean and separate location hierarchies (region, city, neighborhood)
- **Price Analysis**: Handle various price formats and currency notations
- **Export Options**: Clean datasets exported in CSV format for further analysis

## 📁 Project Structure

```
real_estate_tunisia/
├── README.md                          # Project documentation
├── requirements.txt                   # Python dependencies
├── thoughts.txt                       # Project notes and future plans
├── data.ipynb                        # Main analysis notebook
├── datacleaning.ipynb                # Data cleaning pipeline
├── scraping_scripts/
│   ├── mubawaba_scraper.ipynb        # Web scraping implementation
│   └── apartments.csv                # Raw scraped data
└── Data/
    ├── rawdata.csv                   # Initial scraped dataset
    ├── processed_data.csv            # Intermediate processing stage
    ├── cleaned_data.csv              # Final cleaned dataset
    ├── dataSetFull.csv              # Complete dataset
    ├── data_prices_cleaned.csv       # Price-focused dataset
    ├── menzili_preprocessed.csv      # Menzili.tn data (planned)
    ├── mubawab_preprocessed.csv      # Mubawab.tn processed data
    ├── tayara_preprocessed.csv       # Tayara.tn data (planned)
    ├── tunisia-real-estate-data.csv  # Consolidated dataset
    └── tunisia-real-estate.csv       # Alternative format
```

## 🛠 Installation

### Prerequisites

- Python 3.7+
- Internet connection for web scraping

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/real_estate_tunisia.git
   cd real_estate_tunisia
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

### Dependencies

- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `beautifulsoup4` - HTML parsing for web scraping
- `requests` - HTTP library for web requests
- `matplotlib` - Data visualization
- `scikit-learn` - Machine learning utilities
- `selenium` - Web automation (alternative scraping method)
- `webdriver-manager` - WebDriver management

## 🚀 Usage

### 1. Web Scraping

Run the scraping notebook to collect fresh data:

```python
# Open scraping_scripts/mubawaba_scraper.ipynb
# Execute cells to scrape apartment listings
```

The scraper will:

- Navigate through Mubawab.tn apartment listings
- Extract property details, prices, locations, and features
- Save raw data to CSV format

### 2. Data Cleaning

Process the raw scraped data:

```python
# Open datacleaning.ipynb
# Run the complete data cleaning pipeline
```

The cleaning process includes:

- Removing unwanted text and formatting
- Splitting location data into hierarchical columns
- Parsing property features and details
- Standardizing price formats
- Handling missing values

### 3. Data Analysis

Analyze the cleaned dataset:

```python
# Open data.ipynb for analysis examples
# Load the cleaned dataset
import pandas as pd
df = pd.read_csv('Data/cleaned_data.csv')
```

## 📊 Data Pipeline

### Stage 1: Web Scraping

- **Source**: Mubawab.tn apartment listings
- **Method**: Requests + BeautifulSoup
- **Output**: Raw scraped data with basic structure

### Stage 2: Data Cleaning

- **Location Processing**: Split hierarchical location data
- **Feature Extraction**: Parse property details into columns
- **Price Standardization**: Clean currency and numeric formats
- **Data Validation**: Handle missing and inconsistent values

### Stage 3: Feature Engineering

- **Property Attributes**: Extract room counts, surface areas, amenities
- **Location Hierarchy**: Separate city, neighborhood, and district information
- **Categorical Variables**: Standardize property types and conditions

## 📈 Dataset Description

### Final Dataset Features

| Column             | Description                | Type           |
| ------------------ | -------------------------- | -------------- |
| `Title`            | Property listing title     | String         |
| `Price`            | Property price in TND      | String/Numeric |
| `nom_immobilier`   | Real estate company/region | String         |
| `nom_appartement`  | Apartment category         | String         |
| `nom_quartier`     | Neighborhood name          | String         |
| `espace_en_m²`     | Property surface area      | Numeric        |
| `nombre_de_pieces` | Number of rooms            | Numeric        |
| `nb_de_chambres`   | Number of bedrooms         | Numeric        |
| `nb_salle_de_bain` | Number of bathrooms        | Numeric        |
| `Type_de_bien`     | Property type              | Categorical    |
| `Etat`             | Property condition         | Categorical    |
| `Standing`         | Property standing/quality  | Categorical    |
| `Vue_sur_mer`      | Sea view availability      | Boolean        |
| `Piscine`          | Swimming pool              | Boolean        |
| `Garage`           | Garage availability        | Boolean        |
| `Ascenseur`        | Elevator access            | Boolean        |
| `Climatisation`    | Air conditioning           | Boolean        |
| ...                | Additional amenities       | Various        |

### Sample Statistics

- **Total Records**: ~5,154 property listings
- **Geographic Coverage**: Major Tunisian cities and regions
- **Price Range**: Varies from affordable to luxury properties
- **Property Types**: Primarily apartments with various configurations

## 🔮 Future Enhancements

As noted in `thoughts.txt`, planned expansions include:

- **Additional Sources**:
  - Tayara.tn integration
  - Menzili.tn scraping
  - Facebook Marketplace data
- **Advanced Analytics**:
  - Price prediction models
  - Market trend analysis
  - Geographic price mapping
- **Automation**:
  - Scheduled data updates
  - Real-time monitoring
  - Alert systems for price changes

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/new-data-source
   ```
3. **Make your changes**
4. **Add tests if applicable**
5. **Commit your changes**
   ```bash
   git commit -m "Add Tayara.tn scraper"
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/new-data-source
   ```
7. **Create a Pull Request**

### Development Guidelines

- Follow PEP 8 style guidelines
- Add documentation for new functions
- Test scrapers with small samples before full runs
- Respect website terms of service and rate limits

## ⚠️ Disclaimer

This project is for educational and research purposes. Please ensure compliance with:

- Website terms of service
- Robots.txt guidelines
- Local data protection regulations
- Ethical web scraping practices

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

For questions, suggestions, or collaboration opportunities, please open an issue on GitHub.

---

**Note**: This project demonstrates data engineering and analysis techniques for real estate market research. The scraped data should be used responsibly and in accordance with applicable laws and website policies.
=======
# Real_Estate_Tunisia
>>>>>>> 6e20d60c5cfd86fe7bffa2d658815b670ffb83a8
