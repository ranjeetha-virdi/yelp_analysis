# yelp_analysis
# My task:

CoffeeKing is a new startup coffee company providing a unique and novel experience to its customers.  
It wants to appeal to a wide variety of clientele. 
I will use Yelp reviews and Business data to provide insights to CoffeeKing for things such as location selection and/or hours of operation (and other questions?)!

# Questions:
Are the Restaurants liked on the basis of category they belong to; is it dependent on food they serve?
Are Amenities like parking, ambience etc. they provide detrimental in attracting more people? 
Does location of a restaurant matter? Should CoffeeKing open more outlets in big cities or smaller places?
Should my client focus more on the quality and efficiency of the services they offer?
!



# Hypothesis:
1.	People would love to go to places that with good amenities like parking and which are more casual
2.	They would have liking for a particular cuisine.
3.	 Service and excellent food and Coffee would be the reason they go to a certain restaurant.
4.	Affordability shall be a key factor guiding customer decisions.

# My Approach:
1.  Start with analysis of the Business Dataset, look at the attributes.
2.  Analyze the categories.
3.  Look at the number of Restaurants in big cities.
4.  Evaluate the review dataset, analyze the reviews and then look out for things that people like and dislike about the restaurants by analysis of their reviews.
5.  I shall evaluate that with frequency metrics using word cloud.
6.  Look for word count and word frequency (plus – TFID) for sentiment analysis and topic analysis.


# Step 1: Descriptive Stats & Understanding the Data!

I looked at summary of the different descriptive statistics and I also tried to look into the data to find out if my 
initial questions and initial hypotheses are correct or it need some rethinking:

1.	The distribution of various business in our data sets, this will give our client an idea what sort of market they 
and entering and the level of competition they will face: 





![distr](https://user-images.githubusercontent.com/81987445/192219489-51985449-49e9-4470-9675-102e42de63d5.jpg)







2.	My client being Coffee King, lets analyze what is the share of Coffee & Tea business in the entire Restaurants Business. As we can see there only very few Coffee & Tea business as compared to Restaurants Business.

![coffee_tea](https://user-images.githubusercontent.com/81987445/192219582-6029d4a0-c16b-4282-8bf2-6ce66cdef057.jpg)

 
3.	One of my hypotheses was that if the Restaurants are liked on the basis of category they belong to; is it dependent on food they serve (Cuisine), I could see from the dataset that people clearly loved Italian food more and one more surprising thing that I could discovered a very surprising aspect that the Coffee & Tea Business were affiliated with American Food and not with Italian in USA.



![cuisine](https://user-images.githubusercontent.com/81987445/192219649-31be693e-e2f4-4f27-8812-bc56bb88a564.jpg)




![cuisine_coffee](https://user-images.githubusercontent.com/81987445/192219665-0232c8de-d128-4d41-a6be-3684b53e9d41.jpg)


4.	Are Amenities like parking, ambience etc. they provide detrimental in attracting more people. 
    (a) I have tried to analyze the distribution of various amenities(attributes), like acceptance of credit cards, Wi-Fi, Price, outdoor seating, drive-thru, ambience,            parking, restaurants that are children friendly etc. of various restaurants.





      ![very_imp_attributes](https://user-images.githubusercontent.com/81987445/192219702-e6c5c572-e2ef-4923-973e-94d19c413061.jpg)


 

      ![parking](https://user-images.githubusercontent.com/81987445/192219719-5e5d738d-3dc0-48d3-a8d1-202a38e79fad.jpg)

 

      ![ambience](https://user-images.githubusercontent.com/81987445/192219772-319388ee-078d-46d2-8128-320a0e31b4ab.jpg)
 
 
    (b) Plotting the Attributes of the best Coffee Places!
    
      [image](https://user-images.githubusercontent.com/81987445/192219890-803c340f-03c5-4856-b28c-501f36347375.png)


5.	I wanted to analyze the location of restaurants on the basis of their location according to city,state etc to check if the location of a restaurant really matters. How much importance should CoffeeKing give to this aspect. Should they open more outlets in big cities or smaller places.
   (a)  Where are all the best Restaurants located? 
   The best restaurants are located in big cities

   ![image](https://user-images.githubusercontent.com/81987445/192220806-a88d8cf7-e9e7-48c5-8d76-d230a4e1b00f.png)
   
   (b)  Where are all the best Coffee Places located? 
   
   The best Coffee Places
   
   ![image](https://user-images.githubusercontent.com/81987445/192221110-d3c44cc3-1d36-41df-bfb9-17da1e1333de.png)
   
   City-wise distribution of best Coffee Places
   
   ![image](https://user-images.githubusercontent.com/81987445/192221275-c6166314-9bc7-4db5-89d0-d76c93eaf26d.png)
6.  City-wise and State-wise distribution of Restaurants!
   
   ![image](https://user-images.githubusercontent.com/81987445/192221479-b47ae6c0-c7ed-4bde-ad3c-78fdb3036c1b.png)
   ![image](https://user-images.githubusercontent.com/81987445/192221586-636382c4-17cd-4ca0-aa44-4efff4d24ca0.png)

7.  	I tried to analyze my data to gauage how much importance my client should give to Affordability, check the data to get insights how much shall the price be a key factor guiding customer decisions. I got very good insights into these aspects. I have divided the restaurants on the basis of the prices they offer into the following four price categories:
      (a) pricing under 20 $ 
      (b) pricing between 21 $  & 50 $
      (c) pricing between 51 $  & 80 $
      (d) pricing above 80 $
 
  ![price_distr](https://user-images.githubusercontent.com/81987445/192221812-b6f43851-98f5-4804-a48d-b264f4cba0b5.jpg)
  
  I have also plotted a pair plot to see how the review counts and star ratings are distributed amoung these categories: 
  
  ![image](https://user-images.githubusercontent.com/81987445/192223533-aabd15aa-8f78-4a05-90b2-2e8f8edca046.png)
  
8. I also tried to find Correlation and Regression between the different features of the data set!

  (a) Star Rating Vs Review Count :Weak Correlation with R² value of 0.12
  ![image](https://user-images.githubusercontent.com/81987445/192223941-e75602dc-3473-4e36-b23c-5575a835bbb9.png)
  
  (b) Correlation Matrix of Star Rating, Review Count, Price
  ![image](https://user-images.githubusercontent.com/81987445/192224202-8a83caca-ce13-4088-84d4-cf5528bcaa63.png)
  
  (c) Correlation between Stars and the length of the Review
  ![image](https://user-images.githubusercontent.com/81987445/192224287-4f0041bb-b507-4455-aec6-0a34bf28c0c6.png)
  
  (d) Longer Reviews tends to be useful!
  
  ![image](https://user-images.githubusercontent.com/81987445/192224353-254bb141-8c4e-4eff-a048-bad5b2bcb7fc.png)
  
  
9. I tried to carry out indepth analysis of the reviews data and get insights on what people actually like about their favourite restaurants, 
to understand what should a good business actually have.
    (a) What do People want?

    ![image](https://user-images.githubusercontent.com/81987445/192224853-22a0fc86-329d-46d6-8fd1-60e8db59e482.png)
    
    (b) What do People want from specifically a Coffee Business
    ![image](https://user-images.githubusercontent.com/81987445/192225025-3e0b699e-2a65-4874-ad1d-92adce7812ec.png)
    
    (c) What is the best about Starbucks: The Best in the Coffee Business.
    ![image](https://user-images.githubusercontent.com/81987445/192225177-cd76bcbd-e207-41dc-9af4-21a5b9ad768f.png)
    
    
10. Summary of Sentiment Analysis:
    A good Restaurant depends upon its:
    (a) Quality of food & Coffee
    (b) Price
    (c) Location
    (d) Friendliness of Staff
    (e) Experience
    (f) Cusine
   










  





















