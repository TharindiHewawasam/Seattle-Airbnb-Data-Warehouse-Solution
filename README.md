# Seattle-Airbnb-Data-Warehouse-Solution

A Data Warehouse designed using SSIS, SQL Server 2019 and related tools to perform set of ETL tasks of data from various sources to a staging layer and then to the Data Warehouse performing interesting set of transformations.

Airbnb is basically an American company that operates an online marketplace for lodging, 
primarily homestays for vacation rentals and tourism activities. The original source files can be 
found using the link provided below.

Source link: https://www.kaggle.com/datasets/airbnb/seattle

Preparation of data sources :

Among three CSV files I received, I only used 2 CSV files 
namely Listings and Reviews. 

In the initial Listings file, there were 92 columns and then I identified most important columns for 
the analysis purposes. As well as in the Listings.csv file there were information related to Listing’s
basic information, host details, location details and property details of that Listings. So, I separated 
Listings.csv file into four separate source files.

1. Listing Information →
Separated Listings basic information into a database table called 
AirBnbSeattle_Listings.
This table with the help of necessary attributes focus on Listings’ basic information like 
listings_id, name, price, guests_included, extra_people (price for extra people), number of 
reviews, review_scores_rating, last_scraped_date.
Listings_id taken as the primary key and host_id, property_id and location_id took as 
foreign keys.

2. Host Information →
Airbnb Host related details were separated into a database table called
AirBnbSeattle_Host.
This table contains information about host and includes following attributes ; host_id, 
host_name, host_location, host_is_superhost, host_response_time, host_response_time, 
host_response_rate, host_acceptance_rate and host_since.

3. Location Information →
Listings’ location related details were separated into a text file called 
AirBnbSeattle_Location.
This text file contains location_id (pk), zip code, city, state, country, latitude, longitude and 
neighborhood.

4. Property Information →
Listings’ property related details were separated into a CSV file called 
AirBnbSeattle_Property.
This csv file contains following attributes. Property_id, property_type, room_type, 
accommodates, bathrooms, bedrooms, beds, bed_type

In the initial Reviews.csv file, there were information of reviews as well as reviewers. So, I 
separated Review details and Reviewer details into 2 different data sources.

5. Reviewer Information →
Reviewer id and reviewer name were separated into an excel file named 
AirBnbSeattle_Reviewers.
It contains only reviewer_id and reviewer_name.

6. Review Information →
Review details were separated into a database table called reviews.
It contains review_id, date, comments and it has listing_id, reviewer_id as foreign keys.

Solution Architecture
![image](https://user-images.githubusercontent.com/88123921/180133420-34130aca-0c33-4bf6-9505-9793fcb8cf97.png)




