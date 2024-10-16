# SQL Final Project - Flights during COVID-19
Authors: Roy Madpis, Gal Gritzerstein, Doron Danor

## INTRODUCTION
### Prologue

Our project focuses on the Israeli airline “EL-AL” during the COVID-19 pandemic. The goal is to assist the airline in navigating the challenges imposed by the pandemic and help it prepare for a new reality. Flight destinations are no longer based solely on financial considerations; morbidity rates and government restrictions, such as airport closures, are now critical factors.

COVID-19 remains an ongoing crisis, with situations changing rapidly. The analysis presented is based on data retrieved up to June 6th, 2020.

## Database Description
We created a database named COVID19_Flights, consisting of four tables:

1. General Details: This table includes global COVID-19 data such as daily new cases, mortality rates, testing numbers, and population statistics, updated until 06/06/2020.
Source: `Our World in Data`

2. fixed_airports: This table contains a list of international airports and whether they are closed due to COVID-19 restrictions, as of 06/06/2020.
Source: ICAO

3. El Al Destinations: Contains all EL-AL destinations from the company’s inception, with a column indicating whether EL-AL still operates flights to those destinations.
Source: EL-AL website, Wikipedia.

4. Cost-Destination Table: This table estimates ticket prices, operating costs (taxes, fees, fuel), and the number of weekly flights for various destinations to analyze profitability.
Source: EL-AL website and other related sources.

## Business Questions Addressed
### Question 1: Which countries are safe to fly to soon?
Israel defines “green countries” as those with less than 50 new COVID-19 cases per day for the last 21 days. We categorized countries into three groups based on recent case trends:

* Green: ≤ 50 new cases/day
* Yellow: 51–300 new cases/day
* Red: > 300 new cases/day

Additionally, 16 countries that do not accept Israeli passports were excluded from the analysis.

#### Data Analysis:
We queried the data to filter countries based on their case trends and categorized them as Green, Yellow, or Red. The analysis identified around 100 "green" countries, including Greece, Cyprus, and Switzerland, where morbidity levels were low enough for potential flight operations.

### Question 2: Which countries have open airports?
Even though some countries are "green," their airports might still be closed due to COVID-19 restrictions. We queried the database to determine which countries had open airports and cross-referenced them with the green countries list.

**Conclusion:**
Of the 97 green countries, only 34 had open airports. These represent the immediate, practical destinations for EL-AL flights.

### Question 3: Which green countries with open airports are EL-AL’s existing destinations?
We analyzed EL-AL’s current destinations and filtered for those countries where airports are open and classified as green. This provides EL-AL with a list of destinations where flights can be resumed quickly without establishing new agreements.

**Conclusion:**
Based on this analysis, EL-AL could immediately fly to Australia, China, Cyprus, Greece, and Thailand.

### Question 4: What is the financial profitability of these destinations?
In this part of the analysis, we calculated the costs and revenues for green and yellow countries (with both open and closed airports), considering future plans when restrictions ease.

Using EL-AL’s pricing data for economic and business seats, fuel costs, taxes, and other operational expenses, we estimated the revenue per flight and identified which destinations would be most profitable once flying restrictions are lifted.
