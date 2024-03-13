# Project 4 Outline & Scope Document
### Author: Adrian Santos
### Updated: 2024-03-12, v1.0

------------------------------------------------
# Business Question:
## Which is a better market for residential real estate investment opportunities: 
## `Minneapolis` or `Saint Paul`?

------------------------------------------------
Purpose:
------------------------------------------------

1.  Predict the sales price of homes currently for sale, based on similar homes that sold in the past 12 months.
 2. Identify under-valued properties.
 3. Discover highest yields and rental yields.
4. Identify the best investment opportunities for each market.
5. Determine which market is better to invest in: Minneapolis or Saint Paul.

------------------------------------------------
Datasources: 
------------------------------------------------
https://app.scrapeak.com/dashboard/scrapers/zillow-scraper-api
https://propertysearch.streamlit.app/Analytics

------------------------------------------------
Zillow URLs for data extraction:
------------------------------------------------
Minneapolis sold (training): 461 results
https://www.zillow.com/minneapolis-mn/sold/?searchQueryState=%7B%22pagination%22%3A%7B%7D%2C%22isMapVisible%22%3Atrue%2C%22mapBounds%22%3A%7B%22west%22%3A-93.53888328515625%2C%22east%22%3A-92.98407371484375%2C%22south%22%3A44.80851730600839%2C%22north%22%3A45.13253221131886%7D%2C%22mapZoom%22%3A11%2C%22regionSelection%22%3A%5B%7B%22regionId%22%3A5983%2C%22regionType%22%3A6%7D%5D%2C%22filterState%22%3A%7B%22sort%22%3A%7B%22value%22%3A%22globalrelevanceex%22%7D%2C%22fsba%22%3A%7B%22value%22%3Afalse%7D%2C%22fsbo%22%3A%7B%22value%22%3Afalse%7D%2C%22nc%22%3A%7B%22value%22%3Afalse%7D%2C%22cmsn%22%3A%7B%22value%22%3Afalse%7D%2C%22auc%22%3A%7B%22value%22%3Afalse%7D%2C%22fore%22%3A%7B%22value%22%3Afalse%7D%2C%22rs%22%3A%7B%22value%22%3Atrue%7D%2C%22price%22%3A%7B%22min%22%3A250000%2C%22max%22%3A750000%7D%2C%22mp%22%3A%7B%22min%22%3A1272%2C%22max%22%3A3817%7D%2C%22beds%22%3A%7B%22min%22%3A3%2C%22max%22%3Anull%7D%2C%22baths%22%3A%7B%22min%22%3A2%2C%22max%22%3Anull%7D%2C%22tow%22%3A%7B%22value%22%3Afalse%7D%2C%22mf%22%3A%7B%22value%22%3Afalse%7D%2C%22con%22%3A%7B%22value%22%3Afalse%7D%2C%22land%22%3A%7B%22value%22%3Afalse%7D%2C%22apa%22%3A%7B%22value%22%3Afalse%7D%2C%22manu%22%3A%7B%22value%22%3Afalse%7D%2C%22apco%22%3A%7B%22value%22%3Afalse%7D%2C%22hoa%22%3A%7B%22min%22%3Anull%2C%22max%22%3A0%7D%2C%22gar%22%3A%7B%22value%22%3Atrue%7D%2C%22sqft%22%3A%7B%22min%22%3A2000%2C%22max%22%3Anull%7D%2C%22lot%22%3A%7B%22min%22%3A5000%2C%22max%22%3Anull%2C%22units%22%3Anull%7D%2C%22nohoa%22%3A%7B%22value%22%3Afalse%7D%2C%22doz%22%3A%7B%22value%22%3A%2212m%22%7D%7D%2C%22isListVisible%22%3Atrue%7D

Saint Paul sold (training): 290 results
https://www.zillow.com/saint-paul-mn/sold/?searchQueryState=%7B%22isMapVisible%22%3Atrue%2C%22mapBounds%22%3A%7B%22north%22%3A45.02072165373187%2C%22south%22%3A44.85862659676513%2C%22east%22%3A-92.96735110742186%2C%22west%22%3A-93.24475589257811%7D%2C%22mapZoom%22%3A12%2C%22filterState%22%3A%7B%22sort%22%3A%7B%22value%22%3A%22globalrelevanceex%22%7D%2C%22fsba%22%3A%7B%22value%22%3Afalse%7D%2C%22fsbo%22%3A%7B%22value%22%3Afalse%7D%2C%22nc%22%3A%7B%22value%22%3Afalse%7D%2C%22cmsn%22%3A%7B%22value%22%3Afalse%7D%2C%22auc%22%3A%7B%22value%22%3Afalse%7D%2C%22fore%22%3A%7B%22value%22%3Afalse%7D%2C%22rs%22%3A%7B%22value%22%3Atrue%7D%2C%22price%22%3A%7B%22min%22%3A250000%2C%22max%22%3A750000%7D%2C%22mp%22%3A%7B%22min%22%3A1272%2C%22max%22%3A3817%7D%2C%22beds%22%3A%7B%22min%22%3A3%2C%22max%22%3Anull%7D%2C%22baths%22%3A%7B%22min%22%3A2%2C%22max%22%3Anull%7D%2C%22tow%22%3A%7B%22value%22%3Afalse%7D%2C%22mf%22%3A%7B%22value%22%3Afalse%7D%2C%22con%22%3A%7B%22value%22%3Afalse%7D%2C%22land%22%3A%7B%22value%22%3Afalse%7D%2C%22apa%22%3A%7B%22value%22%3Afalse%7D%2C%22manu%22%3A%7B%22value%22%3Afalse%7D%2C%22apco%22%3A%7B%22value%22%3Afalse%7D%2C%22hoa%22%3A%7B%22min%22%3Anull%2C%22max%22%3A0%7D%2C%22gar%22%3A%7B%22value%22%3Atrue%7D%2C%22sqft%22%3A%7B%22min%22%3A2000%2C%22max%22%3Anull%7D%2C%22lot%22%3A%7B%22min%22%3A5000%2C%22max%22%3Anull%2C%22units%22%3Anull%7D%2C%22nohoa%22%3A%7B%22value%22%3Afalse%7D%2C%22doz%22%3A%7B%22value%22%3A%2212m%22%7D%7D%2C%22isListVisible%22%3Atrue%2C%22regionSelection%22%3A%5B%7B%22regionId%22%3A20313%2C%22regionType%22%3A6%7D%5D%2C%22pagination%22%3A%7B%7D%7D

Minneapolis for sale (test): 41 results
https://www.zillow.com/minneapolis-mn/houses/?searchQueryState=%7B%22isMapVisible%22%3Atrue%2C%22mapBounds%22%3A%7B%22north%22%3A45.051700091686435%2C%22south%22%3A44.8896926387%2C%22east%22%3A-93.12277610742187%2C%22west%22%3A-93.40018089257812%7D%2C%22filterState%22%3A%7B%22sort%22%3A%7B%22value%22%3A%22globalrelevanceex%22%7D%2C%22price%22%3A%7B%22min%22%3A250000%2C%22max%22%3A750000%7D%2C%22mp%22%3A%7B%22min%22%3A1272%2C%22max%22%3A3817%7D%2C%22beds%22%3A%7B%22min%22%3A3%2C%22max%22%3Anull%7D%2C%22baths%22%3A%7B%22min%22%3A2%2C%22max%22%3Anull%7D%2C%22tow%22%3A%7B%22value%22%3Afalse%7D%2C%22mf%22%3A%7B%22value%22%3Afalse%7D%2C%22con%22%3A%7B%22value%22%3Afalse%7D%2C%22land%22%3A%7B%22value%22%3Afalse%7D%2C%22apa%22%3A%7B%22value%22%3Afalse%7D%2C%22manu%22%3A%7B%22value%22%3Afalse%7D%2C%22apco%22%3A%7B%22value%22%3Afalse%7D%2C%22hoa%22%3A%7B%22min%22%3Anull%2C%22max%22%3A0%7D%2C%22gar%22%3A%7B%22value%22%3Atrue%7D%2C%22sqft%22%3A%7B%22min%22%3A2000%2C%22max%22%3Anull%7D%2C%22lot%22%3A%7B%22min%22%3A5000%2C%22max%22%3Anull%2C%22units%22%3Anull%7D%2C%22doz%22%3A%7B%22value%22%3A%2212m%22%7D%2C%22nohoa%22%3A%7B%22value%22%3Afalse%7D%7D%2C%22isEntirePlaceForRent%22%3Atrue%2C%22isRoomForRent%22%3Afalse%2C%22isListVisible%22%3Atrue%2C%22mapZoom%22%3A12%2C%22regionSelection%22%3A%5B%7B%22regionId%22%3A5983%2C%22regionType%22%3A6%7D%5D%2C%22pagination%22%3A%7B%7D%7D

Saint Paul for sale (test): 21 results **NB: Below n=27--results may vary**
https://www.zillow.com/saint-paul-mn/houses/?searchQueryState=%7B%22isMapVisible%22%3Atrue%2C%22mapBounds%22%3A%7B%22north%22%3A45.02072165373187%2C%22south%22%3A44.85862659676513%2C%22east%22%3A-92.96735110742186%2C%22west%22%3A-93.24475589257811%7D%2C%22filterState%22%3A%7B%22sort%22%3A%7B%22value%22%3A%22globalrelevanceex%22%7D%2C%22price%22%3A%7B%22min%22%3A250000%2C%22max%22%3A750000%7D%2C%22mp%22%3A%7B%22min%22%3A1272%2C%22max%22%3A3817%7D%2C%22beds%22%3A%7B%22min%22%3A3%2C%22max%22%3Anull%7D%2C%22baths%22%3A%7B%22min%22%3A2%2C%22max%22%3Anull%7D%2C%22tow%22%3A%7B%22value%22%3Afalse%7D%2C%22mf%22%3A%7B%22value%22%3Afalse%7D%2C%22con%22%3A%7B%22value%22%3Afalse%7D%2C%22land%22%3A%7B%22value%22%3Afalse%7D%2C%22apa%22%3A%7B%22value%22%3Afalse%7D%2C%22manu%22%3A%7B%22value%22%3Afalse%7D%2C%22apco%22%3A%7B%22value%22%3Afalse%7D%2C%22hoa%22%3A%7B%22min%22%3Anull%2C%22max%22%3A0%7D%2C%22gar%22%3A%7B%22value%22%3Atrue%7D%2C%22sqft%22%3A%7B%22min%22%3A2000%2C%22max%22%3Anull%7D%2C%22lot%22%3A%7B%22min%22%3A5000%2C%22max%22%3Anull%2C%22units%22%3Anull%7D%2C%22doz%22%3A%7B%22value%22%3A%2212m%22%7D%2C%22nohoa%22%3A%7B%22value%22%3Afalse%7D%7D%2C%22isEntirePlaceForRent%22%3Atrue%2C%22isRoomForRent%22%3Afalse%2C%22isListVisible%22%3Atrue%2C%22mapZoom%22%3A12%2C%22regionSelection%22%3A%5B%7B%22regionId%22%3A20313%2C%22regionType%22%3A6%7D%5D%2C%22pagination%22%3A%7B%7D%7D

------------------------------------------------
Property Features:
------------------------------------------------
Type: Single-Family home
Bedrooms: 3+
Bathrooms: 2+
Price: $250,000 - $750,000
Home Size: minimum 2000 square feet
Lot Size: minimum 5000 square feet
Sold: last 12 months  # NB: 366 days due to Feb 29, 2024.
Must have garage
No HOA fees

------------------------------------------------
Assumptions:
------------------------------------------------
1. The model assumes that property taxes do not impact sales price.
2. The property tax percentage is a percentage of sales price; everyone pays the same rate.
3. The rentZestimate provided is accurate for every property.


Search Parametres:
Training:	Single family home `Sold data` for (1) Minneapolis & (2) Saint Paul:
Testing:	Single family home `For Sale data` for (1) Minneapolis & (2) Saint Paul:
Predict:	Sales price for test data. Identify undervalued properties.

------------------------------------------------
ETL PROCESS
------------------------------------------------
Many steps -- consult the jupyter notebook for details.

------------------------------------------------
EXPERIMENTS & RESULTS
------------------------------------------------
1. Linear Regression - Accuracy: 0.3932062236325743
2. Random Forest Regressor - Accuracy: 0.5166725925615308
3. SVM - Accuracy: 0.0
4. Feature Engineering
		- Create additional calculated fields
		- Retry Experiments 1 & 2 with expanded number of features
5. Winning dataset using linear regression methodology, with additional data elements.


------------------------------------------------
DATA ELEMENTS IN CLEANED DATASET:
------------------------------------------------
 'zpid',
 'homeStatus',
 'dateSold',
 'price',
 'price_predicted',
 'price_predicted_minus_price',
 'ratio_price_predicted_minus_price_v_price',
 'ratio_price_predicted_minus_price_v_price_predicted',
 'zestimate',
 'rentZestimate',
 'price_minus_zestimate',
 'annual_rentZestimate',
 'annual_rentZestimate_v_price',
 'annual_rentZestimate_v_price_predicted',
 'taxAssessedValue',
 'price_minus_taxAssessedValue',
 'bedrooms',
 'bathrooms',
 'ttl_rooms',
 'livingArea',
 'lotAreaValue',
 'streetAddress',
 'city',
 'state',
 'zipcode',
 'latitude',
 'longitude',
 'livingArea_v_ttl_rooms',
 'livingArea_v_lotAreaValue',
 'zestimate_v_rentZestimate',
 'zestimate_v_taxAssessedValue',
 'zestimate_v_ttl_rooms',
 'zestimate_v_livingArea',
 'zestimate_v_lotAreaValue',
 'homeDetailUrl',

------------------------------------------------
TABLEAU
------------------------------------------------
Find key data elements below:
https://public.tableau.com/app/profile/adrian.santos8881/viz/MSP_final_20240312/Undervaluedpropertieswithinvestmentyield?publish=yes

------------------------------------------------
PRESENTATION
------------------------------------------------
Check out the self running movie--it is animated, and brings the analysis to life.
Project4_Presentation_movie_20240312

or the PDF:
Project4_Presentation_20240312

---------------------------------------------------------------
CONTINUING ANALYSIS / OUT OF SCOPE ITEMS / FOR THE FUTURE:
---------------------------------------------------------------

Better understanding of the markets by following them over time.
(1)	Perform weekly snapshots from extract of `for sale` and `sold` data.
	This provides a time-series view of properties on the market.
	Follow pricing prediction patterns for each property and model or methodology.

(2) As the model continues to receive more data, deeper analyses can be performed:
		(a)	Analysis & comparison by zipcode
		(b)	Cluster analysis to identify patterns -- are there differences in variables like Num_bedrooms, Square_feet_home, etc.
		
(3)	Build a model for the rental market. Identify greatest yield properties.
	Do a similar exercise with the rental market data to create a model that predicts rental prices.
	Compare this with the Zestimate from Zillow. Factor it into predictions. There may be higher rents available.

(4)	Comps - same property parametres
	Draw comparisons for each property, and see how well comps did in their predicted vs actual price sold.
	Incorporate any improvements to the model to adapt the prediction model.
	Identify the highest driver of sales price.
	
(5)	Comparisons - different property parametres	
	Perform exploratory analyses on additional property types or sizes. -- Maybe small 1 or 2 bedroom houses are more lucrative?
	
