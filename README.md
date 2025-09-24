# Tunisia Real Estate Data Scraping

A data scraping project for Tunisian real estate market, focusing on apartment listings from Mubawab.tn. This project creates a structured dataset that can be used for real estate price prediction and market analysis.


## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [Data Pipeline](#-data-pipeline)
- [Dataset Description](#-dataset-description)
- [Contributing](#-contributing)
- [License](#-license)

## 🏠 Overview

This project scrapes apartment listings from Mubawab.tn (a major Tunisian real estate website) and processes the data into a clean, structured format suitable for machine learning and price prediction models.

### Key Objectives

- Scrape apartment listings from Mubawab.tn
- Extract and structure property information (prices, locations, features, specifications)
- Create a clean dataset for real estate price prediction projects
- Provide a foundation for Tunisian real estate market analysis

## ✨ Features

- **Web Scraping**: Automated data extraction from Mubawab.tn using requests and BeautifulSoup
- **Data Preprocessing**: Comprehensive pipeline to transform raw scraped data into structured format
- **Feature Extraction**: Parse complex property details into organized columns
- **Location Processing**: Clean and separate location hierarchies (region, city, neighborhood)
- **Property Details Parsing**: Extract amenities, specifications, and features from text
- **Export Ready**: Clean datasets in CSV format ready for machine learning models

## 📁 Project Structure

```
real_estate_tunisia/
├── README.md                          # Project documentation
├── requirements.txt                   # Python dependencies
├── data.ipynb                        # Data analysis notebook (future work)
├── data_cleaning.ipynb                # Data preprocessing pipeline
├── scraping_scripts/
│   ├── mubawaba_scraper.ipynb        # Web scraping implementation
│   └── apartments.csv                # Raw scraped data
└── Data/
    ├── rawdata.csv                   # Initial scraped dataset
    ├── processed_data.csv            # Intermediate processing stage
    └── cleaned_data.csv              # Final cleaned dataset
```

## 🛠 Installation

### Prerequisites

- Python 3.7+
- Internet connection for web scraping

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/oubaid0allah0ayari/Real_Estate_Tunisia.git
   cd Real_Estate_Tunisia
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

### 2. Data Preprocessing

Process the raw scraped data:

```python
# Open datacleaning.ipynb
# Run the complete data preprocessing pipeline
```

The preprocessing includes:

- Cleaning location data and removing unwanted text
- Splitting location data into hierarchical columns (region, city, neighborhood)
- Parsing property features from complex text strings
- Extracting property details (amenities, specifications) into separate columns
- Structuring data for machine learning applications

### 3. Use the Dataset

Load the cleaned dataset for your price prediction models:

```python
# Load the structured dataset
import pandas as pd
df = pd.read_csv('Data/cleaned_data.csv')

# Dataset is ready for:
# - Price prediction models
# - Market analysis
# - Feature engineering
# - Machine learning applications
```

## 📊 Data Pipeline

### Stage 1: Web Scraping

- **Source**: Mubawab.tn apartment listings
- **Method**: Requests + BeautifulSoup
- **Output**: Raw scraped data with basic structure

### Stage 2: Data Preprocessing

- **Location Processing**: Split hierarchical location data into separate columns
- **Feature Extraction**: Parse property details from complex text strings
- **Data Structuring**: Transform unstructured data into organized columns
- **Property Details**: Extract amenities, specifications, and features

### Stage 3: Dataset Export

- **Property Attributes**: Room counts, surface areas, amenities as structured features
- **Location Hierarchy**: Separate columns for region, city, and neighborhood
- **Ready for ML**: Clean dataset suitable for price prediction models

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

- **Additional Data Sources**:
  - Tayara.tn integration
  - Menzili.tn scraping
  - Facebook Marketplace data
- **Machine Learning Applications**:
  - Real estate price prediction models
  - Market trend analysis
  - Property value estimation
- **Data Pipeline Improvements**:
  - Automated data collection
  - Real-time data updates
  - Enhanced data validation

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

**Note**: This project creates a foundation dataset for real estate price prediction and market analysis. The scraped data should be used responsibly and in accordance with applicable laws and website policies.
