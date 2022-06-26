
# Challenge 2 - VBA 



## Purpose and Overview

The Purpose of this Stock Analysis was to compare if changing and refactoring the code in a few areas would make the code run faster.  Code run times were measured using a timer inserted at the end of the macro sub for both the old baseline code and the new refactored code. 

Another purpose of this analysis would be to show the user the results of the Green Energy Stocks.  The initial problem definition was that the user wanted to only run analysis on stock DQ, but through creating an array of all the green stocks with outputs showing volumes and returns we were able to compare DQ to the industry as a whole and it should be avoided as a stock pick which we will reveal below. 

## Baseline Code

 The baseline code was only running on three outputs: 
 

 1. Ticker symbols
 2. Volumes
 3. Return %

Ticker symbols shown below:

![Ticker Pictures](https://user-images.githubusercontent.com/104876690/175838660-e3185c8f-0457-4350-a5a4-7a47b519f680.png)



The code was timed for running this analysis for both 2017 and 2018.  2017 and 2018 baselines both ran in .789 seconds.  The code looped through roughly 3,000 lines of data on 2017 and 2018 each and returned the outputs down 15 rows and across 3 columns. 

See screenshots of 2017 and 2018 baseline times below:



2017
![2017 Baseline GreenStocks](https://user-images.githubusercontent.com/104876690/175838687-ffba0b15-a525-49d7-9188-01319519a0fc.png)


2018
![2018 Baseline GreenStocks](https://user-images.githubusercontent.com/104876690/175838702-c361b407-5bb5-467c-8f0a-e0ab21b57d77.png)

## Refactored Code Analysis

The refactored code takes pieces of the baseline code and makes subtle changes to the code. The first change is to set a ticker index variable to 0.    The second change is the output metrics will be slightly changed to Starting Price and Ending Price.  The baseline code had return which was a calculation from Ending Price - Starting Price -1 to get a %  but now we are breaking out the Ending Price and Starting Price into their own columns.  Along with volume and the ticker symbols this will now bring our output count to 4.
Items in the array of new refactored code:
 1.  Ticker Symbol
 2. Volume
 3. Starting Price
 4. Ending Price 


Our code will still make the same loops to output the data but since there is one extra column my expectations were that it could take fractionally longer to output that information. 

The results of running the new refactored code run times were:

 - 2017: .8125 seconds
 - 2018: .8046875 seconds

Screenshots below:

2017
![2017 Refactored RunTime](https://user-images.githubusercontent.com/104876690/175838728-41095680-1a06-4788-a07c-f67ee6dc1a9d.png)

2018
![2018 Refactored RunTime](https://user-images.githubusercontent.com/104876690/175838734-dd77b43e-3748-4830-ac3c-a86cbc94dd28.png)




These run times were slightly slower than the original code but i believe it is due to the extra loop run in the extra column of the ending Price.  I also debated adding an additional return column so i could show Ending Price, Starting Price and Return % but this would have made the code run even slower .  



## Final Conclusion

The user should choose stocks ENPH and RUN because they were the only two with positive gains in 2017 and 2018 which had all other companies facing negative returns.  These may be well run companies and further analysis could be performed to choose one stock out of these two as the final candidate for best green stock. 

The other conclusion is that using the refactored code was a great addition to quickly changing the look and feel of the spreadsheet although adding the loops for that one extra column resulted in a slightly slower code run time it is negligible from an overall user experience. 
