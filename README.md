This project is directed at predicting the high price of a stock using data from the day prior. I decided to give it a go after reading some scholarly articles which showed high accuracy in predicting the opening price of a stock with very little input value. The project started by looking at the S&P 500 but expanded to all US traded stocks. 

This third generation includes automated education and evaluation of machine learing models. 


The order of the files is
1. TotalUsStockDataCall- This pulls in the data needed to sort and seperate the stock lists used to test models.
2. ModelSeperaterAndSorter- Ranks stocks based on change and volume before splitting the chosen stocks into groups.
3. ModelEdDataCall- Uses these lists to make the largest API call i could manage for model education.
4. AutoEd- Goes through the groups of stocks and ed data and educates the models before storring everything needed in V3100.
5. ModelAssessor- Lets each model run through a 90 day simulation, collects data and then shows visualizations of said data.
6. DailyTrader- Using previously trained and selected models this file assess the accuracy of the model using "yesterdays" data to predict "todays" High before using "todays" data to predict the three highest projected % gainers for "tomorrow" and purchasing them. Finally it sets a trailing stop for each stock now held. This file also sends out a text with info on the model for the daya and info on which and how many shares of stock were purchased on the paper market of Alpacca. 

Things I would/am doing differently. 
-Using volumes alone to sort the stocks doesn't make sense and I believe that on my current version I am using volume*opening price to create a more reliable variable to show how much fiscal activity a stock has. This is more reliable to predict possible slippage when selling during a downtrend. 
-I would love to eventually add in the European and Asian stock markets. If it works once a day why not let it try 3 times a day?
-Obviously there are a pile of beginner code examples/mistakes in here and I know that my use of python has improved just over this project so please be kind with innefficient code. 
-Finally I am planning on making a version of this project that overlaps the sections of stocks used to make the groups for education and evaluation. I think if I had 1000 models to assess that had overlapping and not overlapping stock lists I would then be able to create an adaptive version of this reverse trader that only invests when certain requirements are met. When they aren't met then the next most profitable model will have a chance to meet requirements. Also testing 1000 models instead of 100 may show a better bellcurve surrounding the most viable models when visually displayed.
