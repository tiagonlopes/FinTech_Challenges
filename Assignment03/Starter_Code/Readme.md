# Arbitrage Report

Aiming to evaluate any possibility to profit out of Arbitrage analysis across two different exchanges (Coinbase and Bitstamp), this projects illustrates how you can calculate the daily Spread Profits, by comparing the pricing data of the same cryptocurrency sold in two different market places. Moreover, it illustrates the overall mismatching of the pricing information across the different platforms.

---

## Technologies

The project was created in jupyter notebooks in order to facilitate the interaction between the user and the information. The main python packages used:
    - Pandas
    - Path from pathlib
    - Matplotlib
    
---

## Data

The data is included on the folder Resources, however if you would like to adapt your code to another set of data, it should be quite easy. This data has pricing information of the two different exchanges tools, like:
    - Open
    - High
    - Low
    - Close
    - BTC Volume
    - USD Volume
    - Weighted Price
    
For all the analysis it was used Close price in all analysis.

## Usage

The usage of this report it is very hands-on where by changing the data sourcing as well as the timelines to be studied you can quickly run a tool to verify how much spread you could have earned by doing Arbitrage during that specific time period.
