REQUIREMENTS
------------------------------
Python 3.10 
pandas
numpy
requests
regex
pygooglenews
instaloader
datetime
matplotlib
sklearn
statsmodels
pybase64

* To successfully install pygooglenews, please follow the instructions:
$ pip install pybase64
$ pip install -U --no-deps "feedparser>=6.0.8"
$ pip install sgmllib3k


USAGE EXPLANATION
------------------------------
The jupyter notebook file (Michi_Wang_Final_Project.ipynb) shows clearly the steps of the data cleaning, analysis, and conclusion.

For the usage python file (Michi_Wang_Final_Project.py), there are two ways to run from the command line:
1. python Michi_Wang_Final_Project.py --static
This opens the stored database and performs analysis on stored data
2. python Michi_Wang_Final_Project.py
scrape the complete data, store in a database, then perform analysis on the database (most recently scraped data)


MAINTAINABILITY/EXTENSIBILITY
------------------------------
The model has a great maintainability because the input sources are split into three functions, and each of the function can be altered easily depending on the change of the sources. Most of the codes are structured into functions, so it would be easy to improve each part of them.

The extensibility is good since the data are stored in pandas dataframe, which is flexible to add or delete contents. Thereby if needed, the code can well adapt to new capabilities or functionalities. 




BACKGROUND
------------------------------
The NFT market is at the rage of the prevalence of decentralized blockchains. A couple of digital arts were once caused a sensation with their sky-high sale price. At the same time, it raises the question that do they reflecting the real price. The purpose of this project is to check how the influence of Instagram and the news will affect the trading activity of NFTs. The hypothesis is the trading activities of the NFT market are highly dependent on the influence of influencers and news. The number of times an NFT project is mentioned on Instagram and on the news website in a week will be reflected in the weekly trading volume change.

The three sources of data are:
1. Google News (API: pygooglenews)
The news of the NFT projects is recognized by web scraping the keywords of the specific keyword and then used as a level of influence. The number of times an NFT is tagged will be used as one of the inputs.

2. Instagram (API: instaloader)
Instagram is going to be used for web scraping for the keywords related to NFT projects. For an NFT project, if more posts are tagged, then it has more influence. The number of times an NFT is tagged will be used as one of the inputs.

3. CryptoSlam (web scraping: https://cryptoslam.io/)
The website is used as an inference of trading activities about NFT projects. The transactions within seven days will be used as an output of the influence of an NFT project.

The assumption of the three sets of data is close to:
B0 + B1*X_news + B2*X_ig = Y
Where B1 and B2 are positive real numbers;
X_new is the number of times an NFT project is mentioned in the news within 7 days;
X_ig is the number of times an NFT project is tagged in a post within seven days;
And Y is the transaction number of an NFT project within seven days.