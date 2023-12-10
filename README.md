# final-project

For this project I'm going to calculate the enteprise value of companies using fundamental analysis discounted cash flow method and I'm extracting the necessary information from Yahoo-Finance and Damodaran Online.


I'm extracting data from Damodaran online, a blog from connotaded NYU professor Aswath Damodaran where he posts relevant information that can be used for calculations and estimations. In this blog he posts his own estimations of relevant data that is used to valuate firms, such as discount rates, risk premiums, growth rates by industries and geographic location. As many private/non-public information is required for a robust and accurate estimation of the Enterprise Value, using Damodaran's database will help to get as accurate as possible. 

One of the purposes of this project is to integrate Damodaran's contributions with yfinance library to create a function that returns the Enterprise Value of a firm. 


## Damodaran Data Extraction

First, I defined a large set of functions to extract, clean and parse the data downloaded from the blog. 

The Database contains information of estimations of variables neaded to calculate the free cash flow, weighted averaged cost o capital (WACC) and expected growth. The values are group by industries, the logic behind this is that companies from the same industry tend to share same attributes, such as capital structure, same clients, same market risk, etc. By knowing the industry or sector that a firm is involved, I can use the estimations from Damodaran relative to that sector for the calculations.



### Data Extraction

Damodaran: 
- Cost of capital by industry (USA, Japan. Europe, Japan, (CAN, NZ, AUS), all emerging, China, India, Global)
- Expected Growth Rate in Revenues for the Next 2 years
- Expected Growth Rate in EBIT (Earnings Before Interests and Taxes)
- Tax Rates
- Non-cash Working Capital / Sales
- Net Capital Expenditures / Sales
- Cost of debt
- 10-y Treasury bills 
- Moody Classifiers (spread of cost of debt)
- Risk Premium



YFinance: 
- EBIT (Earnings Before Interests and Taxes)
- Sales
- Interest Expenses
- Total Debt / Equity


### Enterprise Value Calculation

Once we have all the information described above, we can calculate the discounted cash flow

![Alt text](https://github.com/leonplaza/damodaran-EV/blob/master/images/formulas.png)

With all the information, the function's output represent the Enterprise Value estimation

