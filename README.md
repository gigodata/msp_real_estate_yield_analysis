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

Saint Paul sold (training): 290 results

Minneapolis for sale (test): 41 results

Saint Paul for sale (test): 21 results **NB: Below n=27--results may vary**

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
	
