# Stock-Analysis
Analysis of Steve's green energy financial data

---

## Overview of the Project

Steve is managing a portfolio of green energy stocks for his parents and I was tasked with creating a 
program that compiles useful datapoints for financial analysis. My program is able to do this by combing
through a user-defined worksheet in Excel and reprinting it in an easily read table. This program removes
the need for Steve to look manually through over 3,000 rows of data. It also allows him to expand his 
research just by downloading a new dataset in the same format and running the program on that sheet.

## Refactoring the Code

The prototype of this code had all the same functionality as the complete version, but it was much slower
and had a lot less potential for analyzing larger datasets. It used to utilize nested for-loops, where the
inside loop iterated through every row of the dataset and the outer loop iterated through the array of
stock tickers. In this portfolio there are 12 stocks and just over 3,000 rows of data, meaning that it had
to check conditions on a total of ~36,000 rows of data. The new program only iterates through the
datasheets one time. It can do this by taking advantage of the fact that the data is already ordered,
making it possible to iterate through the arrays containing stock-specific data using conditionals.

---

## Results

The original build of this analysis code ran in 1.09 seconds for both 2017 and 2018. As explained before,
this is due to the fact that it had to essentially look through ~36,000 rows of data (not to mention, I 
initially used a for-loop through the datasheet to build the tickers array; more like 40,000 rows). If you
were to try to scale it up (as I would assume Steve will) to perform some prospective analysis of
something like 100 stocks, you could see how the timing was going to be a real issue. So, the change from
13 total loops through the entire dataset, to only 1 loop made the program nearly 80% faster on average
(and I assume that it approaches ~7.5% or 1/13 with larger and larger datasets).

![2017_old](https://github.com/chrisagarcia/Stock-Analysis/blob/main/Resources/2017_old.PNG)
![2018_old](https://github.com/chrisagarcia/Stock-Analysis/blob/main/Resources/2018_old.PNG)

### v.s.

![new 2017](https://github.com/chrisagarcia/Stock-Analysis/blob/main/Resources/2017_new.png)
![new_2018](https://github.com/chrisagarcia/Stock-Analysis/blob/main/Resources/2018_new.png)

---

## Summary

Refactoring code seems to be an essential part of building a functional program. It is important to
optimize the program for the task it is trying to accomplish. After using the optimized version of my
program, I can say it is a little scary and very annoying to use the old version. Every time I run it, the
screen is unresponsive for that second while it processes. The only reason I might use the old script now
is use the ticker finding for-loop for newer datasets. It might be worth the extra processing time it
would take to take the ticker array build for-loop for its utility. That might be included in the next
refactoring.
