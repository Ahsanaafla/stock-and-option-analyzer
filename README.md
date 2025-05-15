A python program to analyze and summerize stock and options trade activities.
FEATUES:
- Accepts csv files
- cleans the file
- standardizes the input data
CATEGORIZATION:
trades are sepaarated into 3 categories:
- stocks
- options
- other
Computational logic :
All transactions are sorted by date to simplify matching and application of fifo logic
FOR TRANSACTIONS OF STOCK:

-Realized Profit/Loss:
For completed buy and sell trades, computed using FIFO method.

-Unrealized Profit/Loss:
For open buy positions (not yet sold), computed using current stock price from Yahoo Finance.

FOR TRANSACTIONS OF OPTIONS
Matching based on full description (including strike price and expiration).

-Realized Profit/Loss:
Calculated when both sides of the trade are available (Buy/Sell or Sell/Buy).
Expiration is treated as a closing event:
Sell + Expire → Realized = Sell amount
Buy + Expire → Realized = -1 × Buy amount

-Unrealized Profit/Loss:
Computed for unmatched open option positions using current market prices.

FILTERING ACCORDING TO TIME PERIOD :
Users can choose from:
Current Month
Last Month
Year-to-Date
All Time

OUTPUT
Displays a summary table with the following columns:
Symbol – Ticker or Option Contract Identifier
Transaction Type – Stock or Option
Realized_Profit_Loss – Total P/L from closed trades
Unrealized_Profit_Loss – Market-to-market P/L for open positions

TECH STACK
Python
Pandas – Data processing
yfinance – Fetch current market prices
Matplotlib – Visualization
Ipywidgets – Interactive filtering
Jupyter / Google Colab – Development environment
