# ML-project-predicting-house-prices-in-London

This proof of concept ML project demonstrates how databases for extracting valuable market information, such as house prices in London, can be created quickly with web-scraping and enhanced with the inclusion of other databases such as a database for income as a function of location, and crime-rate. Various models including linear regression, decision tree regression, support vector regression (SVR), and random forest regression were explored, and optimised using both Grid Search and Randomised Search algorithms.  

The final optimised model, which used a Randomised Search algorithm to optimise a random forest regressor, performs with >80% accuracy on the test set.

It is clear that the proof of concept is satisfactory and may even be improved by including more data points and extending the database to include more features in the future (such as proximity to stations, bus stop density, air quality, etc…)

—————————————————————————————————————————————
— Acquiring all the individual databases — 
—————————————————————————————————————————————

ONS income estimates for all of England and Wales by MSOA code
https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/earningsandworkinghours/datasets/smallareaincomeestimatesformiddlelayersuperoutputareasenglandandwales

The National Ordinance Survey data from CodePointOpen links MSOA District Areas to Coordinates:
Come from National Ordinance Survey data: https://osdatahub.os.uk/downloads/open/CodePointOpen

Can use GoogleMapsAPI to convert coordinates into postcodes:
https://maps.googleapis.com/maps/api/geocode/json?address={address}&key={GoogleAPIkey}

Then simplify all postcodes into postcode districts, i.e. CB5 8BL would become CB5 8)

Crime database from: https://www.plumplot.co.uk/London-violent-crime-statistics.html

House prices database acquired through web-scraping of RightMove using BeautifulSoup and then averaged out the results via postcode district. Found web-scraping script for RightMove already available on Brandon Low’s GitHub (GitHub.com/BrandonLow96/Rightmove-scrapping/blob/main/rightmove_sales_data.py) and explained on (low-brandon96.medium.com/scraping-property-listings-from-rightmove-bd3cfb36516a)
