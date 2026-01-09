# NBA Contracts Web Scraper
### Automated Data Collection from Spotrac using Selenium

This project automates the extraction of **NBA player contract data** from [Spotrac](https://www.spotrac.com/nba/contracts) using **Selenium WebDriver**. The scraper collects contract information for the top 50 highest-paid NBA players, enabling analysis of salary structures, contract trends, and player valuations across the league.

---

## 📌 Project Overview

The scraper extracts key contract details including player rankings, names, ages, and total contract values. This data is valuable for:
- **Salary cap analysis**
- **Contract trend research**
- **Player valuation studies**
- **NBA financial analysis**
- **Sports analytics and reporting**

---

## 🗂️ Data Collected

The scraper extracts the following fields for each player:

- **Rank** – Player's ranking by contract value
- **Player Name** – Full name of the NBA player
- **Age** – Player's age at time of contract signing
- **Value** – Total contract value in USD

**Output Format:** CSV file containing top 50 NBA contracts

---

## 🔄 How It Works

### Workflow

1. **Browser Automation**
   - Launches Microsoft Edge using Selenium WebDriver
   - Navigates to Spotrac NBA contracts page

2. **Dynamic Content Loading**
   - Waits for JavaScript to fully render the contract table
   - Uses explicit waits to ensure data availability

3. **Data Extraction**
   - Locates table rows using XPath selectors
   - Extracts contract details from specific columns
   - Handles missing data gracefully with error handling

4. **Data Processing**
   - Stores extracted data in a Pandas DataFrame
   - Exports to CSV file for further analysis
   - Displays preview of collected data

5. **Cleanup**
   - Closes browser and terminates WebDriver session

---

## 🛠️ Tech Stack

- **Python**
- **Selenium** – Browser automation
- **Microsoft Edge WebDriver** – Browser control
- **Pandas** – Data manipulation and export
- **XPath** – Web element location

---

## 📁 Repository Structure
```
├── NBA Contracts Scraper.ipynb    # Main scraping notebook
├── top_50_nba_contracts.csv       # Output data file
└── README.md                      # Project documentation
```

---

## 🚀 How to Run

### Prerequisites

1. **Install Python packages**
```bash
   pip install selenium pandas
```

2. **Download Microsoft Edge WebDriver**
   - Download from [Microsoft Edge Driver](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/)
   - Ensure version matches your Edge browser version
   - Update the `edge_driver_path` variable in the script

### Running the Scraper

1. **Clone the repository**
```bash
   git clone <repository-url>
   cd <repository-name>
```

2. **Update WebDriver path**
```python
   edge_driver_path = r"C:\path\to\your\msedgedriver.exe"
```

3. **Run the notebook**
```bash
   jupyter notebook "NBA Contracts Scraper.ipynb"
```

4. **Output**
   - CSV file: `top_50_nba_contracts.csv`
   - Console display of extracted data

---

## 📊 Sample Output
```
   Rank              Player Name Age         Value
0     1             Jayson Tatum  26  $313,933,410
1     2             Jaylen Brown  26  $285,393,640
2     3             Nikola Jokic  27  $276,122,630
3     4             Bradley Beal  29  $251,019,650
4    T5          Anthony Edwards  21  $244,623,120
```

---

## 🔧 Customization Options

### Modify Number of Players
```python
rows = driver.find_elements(By.XPATH, '//table/tbody/tr')[:100]  # Get top 100
```

### Add Additional Fields
Update XPath selectors to extract more columns:
```python
team = row.find_element(By.XPATH, './/td[3]').text.strip()  # Team
years = row.find_element(By.XPATH, './/td[6]').text.strip()  # Contract length
```

### Change Output Format
```python
df.to_excel("nba_contracts.xlsx", index=False)  # Export as Excel
df.to_json("nba_contracts.json", orient="records")  # Export as JSON
```

---

## ⚠️ Important Notes

### Legal & Ethical Considerations
- **Respect website terms of service** – Check Spotrac's robots.txt and ToS
- **Rate limiting** – Add delays between requests to avoid overloading servers
- **Data usage** – Use scraped data responsibly and for legitimate purposes

### Technical Considerations
- **WebDriver compatibility** – Ensure Edge WebDriver version matches browser version
- **Dynamic content** – Adjust wait times if page loads slowly
- **XPath stability** – Website structure changes may break selectors

---

## 📈 Future Enhancements

- Support for Chrome and Firefox WebDriver
- Historical contract data scraping
- Multi-season comparison analysis
- Salary cap calculations and projections
- Player performance vs. salary correlation
- Automated scheduling for regular updates
- Database integration for persistent storage

---

## 📧 Contact

**Talha Gulzar**  
MS in Business Analytics  
Babson College

🔗 LinkedIn: [linkedin.com/in/talhagulzar2](https://www.linkedin.com/in/talhagulzar2)

---

## 📄 Copyright & Usage

© 2025 Talha Gulzar. All rights reserved.

This project is shared for **portfolio and educational purposes only**. Users are responsible for ensuring their use of this scraper complies with Spotrac's terms of service and applicable laws. Unauthorized commercial use or redistribution is prohibited without explicit permission from the author.


