<h1>Abstract</h1>
<200
<h1>Declaration</h1>
copyright？

<h1>Acknowledgements</h1>
<h1>Content</h1>
<h1>Introduction</h1>
市场倾向？目标是预测股价和投资组合？

subject matter & scope of investigation

purpose

organization

<h1>Literature Review</h1>
<h2>Sentiment Analysis</h2>
<h2>Price Prediction</h2>
<h2>Portfolio Optimization</h2>
<h1>Problem Analysis</h1>
Many scholars in stock price prediction tend to predict the future stock price by analyzing the historical stock price. From the historical data, some useful information, such as volatility, price trend in long term, can be discovered. However, when using purely the historical price, the prediction doesn’t work very well. We’ve applied RNN on the historical training, the accuracy turns our to be 57%, which is not that high. Then an idea of add news into the data set was come out. This idea is based on a presumption that there is close relation between news of the company and the stock price of that day. When a event happen on a company, there will be news. And the event will also have impact on the stock price of the relative companies, as the event will influence the trading action of the investor. Sometimes this influence will leads to sudden turn on stock price trend, which cannot be predicted by purely the historical price. In this case, the news is a reflection of the current situation of the company. It is therefore reasonable to predict the price trend through analyzing the news.

The mainstream trading algorithms based on price prediction, on the other hand, are, to some extent, unrealistic. Most of the algorithms use the historical data to predict the close price of the next day. There is, nevertheless, a conflict between obtaining data and executing trading. All of today’s data such as close price, high price and low price, cannot be obtained before the closing bell. But if the investors want to earn money based on the predicted close tomorrow, he must long some stocks and short those tomorrow, due to the market rule that the investors cannot both long and short the same stock in the same day. Thus, everything should be done before the close today, including the data collection, price prediction and trading.

Another problem is discussed in this project is the risk of trading. Even if the prediction algorithm is relatively advanced nowadays, there is still something we cannot predict. N this case, some of the investors would like to take higher risk for higher return, while some would not. A portfolio suggestion strategy based on the investors risk preference is therefore significant. 
This project thus aims at constructing a system for both price prediction and portfolio management for the investors. The innovations are:

* To predict the future price using both historical data and the news data.

* To provide investor enough reaction time to execute trading.

* To take investors’ risk preference into account.

<h1>Methodology</h1>
<h2>Sentiment Analysis</h2>
<h2>Price Prediction</h2>
<h2>Portfolio Optimization</h2>
<h1>System Structure</h1>
A real-time systems is built using the methodology introduced above. The system is constructed with 4 major modules. The front end is a website showing the real-time data, such as daily news, real-time stock price, and portfolio suggestion. Database manages all the historical data used in the algorithm and the generated results. Data process module crawls the daily data, predicts the return of the next day and gives a portfolio suggestion every day. The 3 modules above communicates through a API. The API, the only module which can access the database, manages the database directly using MySQL. The website, and the data process module, however, can only send a HTTP request to API and get a return of its process result.

系统图

<h2>Working strategy of data process module</h2>
The data process module works automatically following a strict time sequence. The module starts to work at 10 am everyday. It first crawls the news data from 10 am yesterday to 10 am today and then calculates the sentiment score using the sentiment analysis model we built. At the same time, today’s open price is obtained from an utility called tushare and the historical stock price data will be obtained from the database. When the sentiment analysis is finished, the result will be store into database. Meanwhile, the price prediction model starts to predict the future return, combining the sentiment score, the open price and the historical price. Finally, after obtaining the predicted return, the module starts to optimize a portfolio for the user.

时间线图

<h2>Database structure</h2>
There are 4 tables in the database. Table news saves the historical news and the sentiment score of each piece of news. Table stock stores the historical stock price, the sentiment score for the company obtained everyday and the daily predicted price. Table portfolio saves the real-time suggestion for each user, with return and risk. And there is a table for storing personal information for users.

DB图

<h2>User interface for platform</h2>
The result of the real-time prediction ends up being shown on a website. 

website图

<h1>Experiment</h1>
<h2>Data selection</h2>
为什么选沪深300？为什么选新浪？为什么选这些feature？

<h2>Data preprocessing</h2>
分词？词库？nlp？  
算return？算log？为什么要shift data?

<h2>Experiment Result</h2>

<h1>Discussion</h1>
<h1>Conclusion</h1>
<h1>Reference</h1>
<h1>Appendices</h1>
platform的使用说明
