- [  
    Marketsetup](https://marketsetup.in/)
 - [Blog](https://marketsetup.in/posts)
 - [News](https://marketsetup.in/news)
 - [Documentation](https://marketsetup.in/documentation)

Table of content

- [Functionalities](https://marketsetup.in/documentation/jugaad-data/#functionalities)
- [Installation](https://marketsetup.in/documentation/jugaad-data/#installation)
- [Quick start](https://marketsetup.in/documentation/jugaad-data/#quick-start)
    
- [Detailed documentation](https://marketsetup.in/documentation/jugaad-data/#detailed-documentation)
    - [](https://marketsetup.in/documentation/jugaad-data/#1-download-historical-data)[1. Download historical data](https://marketsetup.in/documentation/jugaad-data/historical/)
    - [](https://marketsetup.in/documentation/jugaad-data/#2-fetch-live-data)[2. Fetch live data](https://marketsetup.in/documentation/jugaad-data/live/)
    - [](https://marketsetup.in/documentation/jugaad-data/#3-fetch-rbi-data)[3. Fetch RBI data](https://marketsetup.in/documentation/jugaad-data/rbi/)

# Jugaad Data

`jugad-data` is a library to fetch live as well as historical stock data. This library will be a cruicial part of your analysis, backtesting and automation workflow for trading and investing.

This library fetches data from new website of NSE and hence `jugaad-data` is future-proof. Many other libraries still rely on old website and may eventually stop working.

## Functionalities

- Download bhavcopy for stocks, index and derivatives
    
- Download historical stock, index and derivatives (Futures & Options) data
    
- Fetch live quotes for stocks and derivatives
    
- Fetch live index and turnover data
    
- Fetch option chains
    
- Fetch current rates from RBI website
    

In pipeline

- Corporate information
- Financial results

In case you find other information available in NSE’s website as JSON api, please raise a feature [here](https://github.com/jugaad-py/jugaad-data/issues)

## Installation

`pip install jugaad-data`

You can optionally install `pandas` library in case you are interested in fetching data directly into ‘pandas’ dataframes, in which case you can run-

`pip install jugaad-data pandas`

## Quick start

#### Download bhavcopies and historical stock/index/derivatives data

```python
from datetime import date
from jugaad_data.nse import bhavcopy_save, bhavcopy_fo_save

# Download bhavcopy
bhavcopy_save(date(2020,1,1), "./")

# Download bhavcopy for futures and options
bhavcopy_fo_save(date(2020,1,1), "./")
```

```
'./fo01Jan2020bhav.csv'
```

```python
 ls *.csv
```

```
cm01Jan2020bhav.csv  fo01Jan2020bhav.csv
```

```python
!tail cm01Jan2020bhav.csv
```

```
ZENITHEXPO,BE,46.95,46.95,43.6,45.55,46.6,44.95,1201,54268.2,01-JAN-2020,22,INE058B01018,
ZENSARTECH,EQ,175.95,176.9,173,175.4,175.85,174.6,18748,3281047.5,01-JAN-2020,4269,INE520A01027,
ZENTEC,EQ,55.15,57.4,54.3,55.95,56.4,56.45,25296,1412952.05,01-JAN-2020,266,INE251B01027,
ZICOM,BE,1.65,1.65,1.55,1.65,1.65,1.6,36099,56326.85,01-JAN-2020,32,INE871B01014,
ZODIACLOTH,EQ,175.35,184.95,168.75,171.75,172,175.35,12971,2249854.55,01-JAN-2020,758,INE206B01013,
ZODJRDMKJ,EQ,32.05,32.75,32,32.05,32.05,32.8,1070,34359.15,01-JAN-2020,73,INE077B01018,
ZOTA,EQ,188.9,189.75,186.75,188.5,188.5,186.45,25664,4828369.25,01-JAN-2020,165,INE358U01012,
ZUARI,EQ,92.4,92.4,90.6,92,92,90.5,9173,840932.3,01-JAN-2020,174,INE840M01016,
ZUARIGLOB,EQ,49.1,50.25,48.1,48.5,48.2,50.05,19086,937517.35,01-JAN-2020,408,INE217A01012,
ZYDUSWELL,EQ,1462,1479.95,1462,1465.95,1465.45,1470.3,1118,1642480.7,01-JAN-2020,301,INE768C01010,
```

```python
!tail fo01Jan2020bhav.csv
```

```
OPTSTK,ZEEL,26-Mar-2020,240,PE,0,0,0,15.55,13.15,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,260,PE,0,0,0,22.8,20.35,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,280,PE,0,0,0,31.7,29.45,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,300,PE,0,0,0,42.15,40.35,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,320,PE,0,0,0,54,52.85,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,340,PE,0,0,0,67.15,66.75,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,360,PE,0,0,0,81.4,81.9,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,380,PE,0,0,0,96.6,98,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,400,PE,0,0,0,112.65,114.95,0,0,0,0,01-JAN-2020,
OPTSTK,ZEEL,26-Mar-2020,420,PE,0,0,0,129.3,132.5,0,0,0,0,01-JAN-2020,
```

```python
# Download stock data to pandas dataframe
from jugaad_data.nse import stock_df
df = stock_df(symbol="SBIN", from_date=date(2020,1,1),
            to_date=date(2020,1,30), series="EQ")
print(df.head())
```

```
        DATE SERIES    OPEN    HIGH     LOW  PREV. CLOSE     LTP   CLOSE  \
0 2020-01-30     EQ  316.75  316.75  305.65       316.45  310.00  310.70   
1 2020-01-29     EQ  317.85  319.70  315.55       315.10  316.95  316.45   
2 2020-01-28     EQ  317.95  320.00  311.05       316.20  316.40  315.10   
3 2020-01-27     EQ  320.90  322.00  315.80       324.05  316.40  316.20   
4 2020-01-24     EQ  323.50  327.30  321.15       323.20  324.30  324.05   

     VWAP  52W H   52W L    VOLUME         VALUE  NO OF TRADES SYMBOL  
0  311.18  373.8  244.35  35802330  1.114102e+10        227687   SBIN  
1  317.75  373.8  244.35  23914114  7.598704e+09        143297   SBIN  
2  316.67  373.8  244.35  26488426  8.388015e+09        173879   SBIN  
3  318.82  373.8  244.35  23309355  7.431558e+09        148768   SBIN  
4  325.15  373.8  244.35  22706879  7.383247e+09        146667   SBIN  
```

Download stock data to pandas dataframe

```python

from jugaad_data.nse import stock_df
df = stock_df(symbol="SBIN", from_date=date(2020,1,1),
            to_date=date(2020,1,30), series="EQ")
print(df.head())
```

```
        DATE SERIES    OPEN    HIGH     LOW  PREV. CLOSE     LTP   CLOSE  \
0 2020-01-30     EQ  316.75  316.75  305.65       316.45  310.00  310.70   
1 2020-01-29     EQ  317.85  319.70  315.55       315.10  316.95  316.45   
2 2020-01-28     EQ  317.95  320.00  311.05       316.20  316.40  315.10   
3 2020-01-27     EQ  320.90  322.00  315.80       324.05  316.40  316.20   
4 2020-01-24     EQ  323.50  327.30  321.15       323.20  324.30  324.05   

     VWAP  52W H   52W L    VOLUME         VALUE  NO OF TRADES SYMBOL  
0  311.18  373.8  244.35  35802330  1.114102e+10        227687   SBIN  
1  317.75  373.8  244.35  23914114  7.598704e+09        143297   SBIN  
2  316.67  373.8  244.35  26488426  8.388015e+09        173879   SBIN  
3  318.82  373.8  244.35  23309355  7.431558e+09        148768   SBIN  
4  325.15  373.8  244.35  22706879  7.383247e+09        146667   SBIN  
```

#### Fetch live quotes

```python
from jugaad_data.nse import NSELive
from pprint import pprint
n = NSELive()
q = n.stock_quote("HDFC")
pprint(q)
```

```
{'industryInfo': {'basicIndustry': '',
                  'industry': '',
                  'macro': '',
                  'sector': ''},
 'info': {'activeSeries': [],
          'companyName': 'Housing Development Finance Corporation Limited',
          'debtSeries': [],
          'identifier': 'HDFCEQN',
          'industry': 'FINANCE - HOUSING',
          'isCASec': False,
          'isDebtSec': False,
          'isDelisted': False,
          'isETFSec': False,
          'isFNOSec': False,
          'isSLBSec': False,
          'isSuspended': True,
          'isTop10': False,
          'isin': 'INE001A13049',
          'symbol': 'HDFC',
          'tempSuspendedSeries': ['EQ', 'W1', 'W2', 'W3']},
 'metadata': {'industry': 'NA',
              'isin': 'INE001A01036',
              'lastUpdateTime': '-',
              'listingDate': '23-Oct-1996',
              'pdSectorInd': 'NA',
              'pdSectorPe': 'NA',
              'pdSymbolPe': 'NA',
              'series': 'EQ',
              'status': 'Permanent Suspended',
              'symbol': 'HDFC'},
 'preOpenMarket': {'ato': {'buy': 0, 'sell': 0}, 'preopen': [{'iep': True}]},
 'priceInfo': {'basePrice': 0,
               'change': 0,
               'checkINAV': False,
               'close': 2724.3,
               'iNavValue': None,
               'intraDayHighLow': {'max': 0, 'min': 0, 'value': 0},
               'lastPrice': 0,
               'lowerCP': '2472.65',
               'open': 0,
               'pChange': 0,
               'pPriceBand': 'No Band',
               'previousClose': 0,
               'upperCP': '3022.05',
               'vwap': 0,
               'weekHighLow': {'max': 2927.4,
                               'maxDate': '03-Jul-2023',
                               'min': 2363,
                               'minDate': '27-Oct-2022',
                               'value': 0}},
 'sddDetails': {'SDDAuditor': '-', 'SDDStatus': '-'},
 'securityInfo': {'boardStatus': 'Main',
                  'classOfShare': 'Equity',
                  'derivatives': 'No',
                  'faceValue': 2,
                  'issuedSize': 1851426483,
                  'sessionNo': '-',
                  'slb': 'No',
                  'surveillance': {'desc': None, 'surv': None},
                  'tradingSegment': 'Normal Market',
                  'tradingStatus': 'Suspended'}}
```

#### Command line interface for bhavcopies and historical data

Overall CLI functionality-

```
$ jdata --help
Usage: jdata [OPTIONS] COMMAND [ARGS]...

  This is a command line tool to download stock market data to csv files.

Options:
  --help  Show this message and exit.

Commands:
  bhavcopy     Downloads bhavcopy from NSE's website Download today's...
  derivatives  Sample usage- Download stock futures- jdata derivatives -s...
  index        Download historical index data $jdata index --symbol "NIFTY...
  stock        Download historical stock data $jdata stock --symbol STOCK1...
```

Download stock data-

`$ jdata stock -s SBIN -f 2020-01-01 -t 2020-01-31 -o SBIN-Jan.csv`

## Detailed documentation

### [1. Download historical data](https://marketsetup.in/documentation/jugaad-data/historical/)

#### [1.1 Command line interface](https://marketsetup.in/documentation/jugaad-data/historical/#command-line-interface)

### [2. Fetch live data](https://marketsetup.in/documentation/jugaad-data/live/)

### [3. Fetch RBI data](https://marketsetup.in/documentation/jugaad-data/rbi/)

[

### Jugaad Data - Fetch live stock market data

Fetch live stock market data data using python

Dec 24, 2023](https://marketsetup.in/documentation/jugaad-data/live/)

[

### Jugaad Data - Download historical stock market data

Download historical stock market data using python

Jan 8, 2021](https://marketsetup.in/documentation/jugaad-data/historical/)

[

### Jugaad Data - Fetch Economic Data from RBI

Fetch economic data such as policy rates, deposit rates, T-Bill rates etc. from RBI website using …

Jan 8, 2021](https://marketsetup.in/documentation/jugaad-data/rbi/)

[![Telegram](https://marketsetup.in/telegram.svg)Join our Telegram for instant updates!](https://t.me/getmarketsetup)

- [About](https://marketsetup.in/)
 - [Privacy Policy](https://marketsetup.in/privacy/)
 - [Contact us](https://marketsetup.in/contact-us/)