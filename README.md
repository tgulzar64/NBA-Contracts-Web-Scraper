# NBA-Contracts-Web-Scraper
This project automates the extraction of NBA player contract data from Spotrac using Selenium and Microsoft Edge WebDriver. It focuses on gathering financial information for the top 50 highest-paid players, making it useful for salary analysis, sports finance research, and valuation models.

## Project Purpose 📊
To build a robust web scraping tool that captures player contract details, including rank, age, and contract value — enabling downstream financial insights in sports analytics.

## Workflow ⚙️
Launches Microsoft Edge browser and navigates to Spotrac

Waits for the JavaScript-rendered contract table to load

Extracts data for the top 50 NBA players by contract value

Stores data in a pandas DataFrame

Saves the dataset to a CSV file and displays a preview

## Data Extracted 🧾
Rank

Player Name

Age

Contract Value

## Tech Stack 🛠
selenium, pandas, time, Microsoft Edge WebDriver

## File Included 📁
NBA Contracts Scraper (1).ipynb: Full implementation notebook for scraping and saving the contract data.


