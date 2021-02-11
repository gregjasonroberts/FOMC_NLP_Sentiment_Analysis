# FOMC_NLP_Sentiment_Analysis
Using spaCy and NLTK along with a Bag of Words approach, this notebook combed through 30 years FOMC minutes transcripts from 1980 to 2010 to determine sentiment over time.


### Overview
* Review FOMC transcripts over a 30 year period and determine trends and baseline to analyze future Fed commentary
* Relatively basic model that emphasizes scraping over 200 pdf files, tokenizing all non-stop words and categorizing each based on sentiment.
* Apply sentiment analysis to the words in the documents using the Loughran-McDonald context-specific lexicon.  This dictionary assigns a simple  value to words based on the financial services industry context.

### Code and Resources Used
Python Version: 3.7  
Environment: Google Colab  
Packages: pandas, numpy, spaCy, NLTK, sklearn, matplotlib, pdfplumber

Source data: Fed minutes ((https://www.federalreserve.gov/monetarypolicy/); Loughran-McDonald (https://sraf.nd.edu/textual-analysis/resources/#LM_10X_Summaries

### Data Cleaning
* Extracted pdfs from the Federal Reserve website (https://www.federalreserve.gov/monetarypolicy/)
* Then on my local computer organized each pdf into its respective publication year.  Separately each file was looped through in a list and scraped with the help of the pdfplumber library, preprocessed for html symbols and after removing common words was tokenzied.  
* Each file tokenized was put into a separate row in a consolidated dataframe.

### EDA
* Parsing through 30 years of FOMC (Federal Open Market Committee) meetings minutes, which includes roughly 
8 meetings per year.

![alt text](images/fomc_top_words.png)

### Model Building
* Tracked the sentiment produced from mapping to the Loughran-McDonald financial lexicon and how the sentiment changed during these tumultuous historical periods
![alt text](images/fed_crisis_periods.png)

### Model Performance
* Our sentiment moving average explained 42% of the S&P500 price change over this period.
![alt text](images/sentiment_corr.png)



