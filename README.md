
## Project Goal  :
This project is an outcome of Programming Assignment with a goal to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through September 30 2017.  

## Data Scource & License 
* Data Scource  : Wikimedia Foundation usig [Wikimedia REST API](https://wikimedia.org/api/rest_v1/)
* Wikimedia Foundation : [Term of Use](https://wikimediafoundation.org/wiki/Terms_of_Use/en)

Data collected from [Wikimedia Foundation](https://en.wikipedia.org/wiki/Wikimedia_Foundation) is [licensed](https://en.wikipedia.org/wiki/Wikimedia_Foundation#Projects_and_initiatives) for redistribution under [v3.0](https://creativecommons.org/licenses/by/3.0/) .


## Relevant API 
Data collected for this project comes from Wikimedia Foundation using two different APIs :- 
1. The legacy Pagecounts API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts#Monthly_counts)) provides access to desktop and mobile traffic data from January 2008 through July 2016.
2. The Pageviews API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews#Monthly_counts)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through September 2017.


## Data Collection :

Using Above API Five set of data collected in JSON format using Namind convetion  : 
* #### apiname_accesstype_firstmonth-lastmonth.json 

1. Desktop Traffic  (All ) -- pagecounts_desktop-site_200801-201607.json
2. Mobile Traffic (All )    -- pagecounts_mobile-site_200801-201607.json
3. Desktop Traffic (Only User) -- pageviews_desktop-site_201501-201709.json 
4. Mobile web Traffic (Only User)-- pageviews_mobileweb-site_201501-201709.json
5. Mobile App Traffic(Only User) -- pageviews_mobileapp-site_201501-201709.json



##  Tranformed Data Description (en-wikipedia_traffic_200801-201709.csv)

* Final Data File : en-wikipedia_traffic_200801-201709.csv 

This datset(CSV format) has been created from raw data collected in JSON format.

Here is a short  description of differnet columns in the data set  :- 

| Column| Value |Comment|
| ------------- |:-------------:| :-----|
|year|	YYYY| Year from 2008 - 2017
|month|	MM| Month from 01-12
|pagecount_all_views|	num_views| All Views (Destop + Mobile)
|pagecount_desktop_views|	num_views| All Views from Desktop 
|pagecount_mobile_views	|num_views| All Views from Mobile
|pageview_all_views	|num_views| All Views (Destop + Mobile)
|pageview_desktop_views	|num_views| All Views from Desktop
|pageview_mobile_views|	num_views| All Views from Mobile

## Visaulization 

![title](https://github.com/abhishekanand/data-512-a1/blob/master/Mobile%20and%20desktop%20traffic%20data%20for%20English%20WIkipedia%20from%202008-2016.png)


Visualization Lenged Description : 

1. TotalViews : All views  (user + Spider) [2+3]
2. DesktopViews : Desktop View (user + Spider)
3. MobileViews : Mobile View (User + Spider)
4. TotalViews-UserOnly : All views  (No Spider) [5+6]
5. DesktopViews-UserOnly : Desktop View (No Spider)
6. MobileViews-UserOnly : Mobile View (No Spider)

## Consideration  :
* Data from the Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.
* There is a ~13 month (July 2015-July 2016) period in which both APIs provide traffic data.
* Pageview Mobie Views contains traffic from Mobile Web and Mobile App  
