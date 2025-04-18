---
layout: page
title: Data-Driven Cryptocurrency Trading Bot
description: A cryptocurrency backtester and strategy using Binance API data to test trading algorithms. Personal Project
img: assets/img/Crypto Backtester/1.png
importance: 3
category: Software
---

<p>In the dynamic world of cryptocurrency, data-driven decision-making can make the difference between profit and loss. This post explores a Python-based trading bot that simulates cryptocurrency trades using historical market data. With features like trade simulation, performance logging, and parameter optimization, this bot is a great starting point for aspiring algorithmic traders.</p>

<h2>Key Components</h2> 
<ul>
    <li><strong>Data Handling:</strong> Reads historical cryptocurrency prices from JSON files. Each coin’s data is encapsulated in a `Coin` object for easy access. Data is loaded into memory, and each cryptocurrency is represented as an object with its historical dataset. The `createCoins` function ensures all relevant data is integrated for analysis. This data was previously taken from the Binance API and loaded into files for increased speed.</li>

    <li><strong>Trading Simulation:</strong> Using user-defined parameters, the bot evaluates market trends and uses its strategy to simulate trades over a specified length of time and measures its performance based on metrics. The longest simulations were run over multiple years of data</li>

    <li><strong>Performance Metrics, Logging, and Visualization:</strong> Trades are logged with detailed metrics like profits, losses, and the time in each position. The `investigate` function provides a graphical view of price trends during trades.</li> 
</ul>


<h2>Strategy</h2> 
<p>This strategy is my unique take on mean reversion where a polynomial function was fit to the curve of the last 90 minutes of data. If the current price was lower than the function expected it was expected that the price would rebound toward the mean. Other factors were included in this calculation such as volatility and direction of the line to calculate the probability of the price increasing.</p>


<h2>Parameter Optimization</h2> 
<p>The `skopt` package was used for optimizing trading parameters like volatility, order of the line of fit, size and momentum. Training data was used and run many times to find the best weights and was then tested on test data to measure it's actual performance</p>


<h2>Future Improvements</h2> 
<ul>
    <li><strong>Real Time Trading:</strong> While real time trading was implemented in the project is was susceptible to errors and power outages which could result in substantial losses. In the future a server in an offsite location should be constantly ensuring that the bot is running and would step in and close positions if it was not.</li>
    
    <li><strong>Improved Metrics:</strong> As this was my first project looking into quantitative analysis I have learned a lot about the limitations of the program I have made. A better metric for performance of the system would be the Sharpe Ratio</li>

    <li><strong>Improved Data Collection:</strong> The data collected for this bot was inadequate and weighted towards coins that have preformed well in the past which padding the profits unrealistically. Methods of collecting clean data need to be implemented. </li> 
</ul>


<h2>Conclusion</h2> 
<p>This bot provides a solid foundation for exploring algorithmic trading in cryptocurrencies. Future projects can leverage the understanding gained during this project.</p>

