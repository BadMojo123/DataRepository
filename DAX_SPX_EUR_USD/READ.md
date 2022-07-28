## Price data from 2018 <br>
### Data interpretation
Each file represent price data (bar) for one instrument in one time frame.
Folder contain 2 different time ranges: 5 min and 30 min<br>
Data contain 3 different instruments: 
1. DAX - Biggest German index 
2. SPX - Standard and Poor 500
3. EUR/USD - FX pair

### Data format
1. Data is stored in ; separated CSV.
2. Data contain headers
time;closeAsk;closeBid;complete;highAsk;highBid;lowAsk;lowBid;openAsk;openBid;volume

*where volume is a volume of contracts in FX provider
3. Data values example:
2018-01-03 00:00:00+00:00;2692.1;2691.6;True;2692.1;2691.6;2691.6;2691.1;2691.6;2691.1;4
4. 

Important to note:
1. Data is available only in hours when market is open
2. When the volume is very low, some bars may be missing

## Data analysis and preprocessing
Following data require following preprocessing:
1. To analyse data togather, separate files need to be joined using time as a key
2. Missing values needs to be filled using steps below:
   1. Price data
      1. First if possible with first predeceasing available value
      2. First following available value
   2. Volume data by default should be 0 if not available
