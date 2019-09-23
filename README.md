# Pack It

## https://lexi-winstanley.github.io/packIt/

## Overview
The idea with our app Pack It! is to simplify the task of packing for a trip. The user inputs a destination and trip duration, Pack It! then gets a 5-day forecast for that location and suggests a packing list based on the weather and the trip duration. The location is also used to display webcams near the destination which can further inform the user’s packing plans.  

## Group Members 
- [Christina Chon - GitHub](https://github.com/christinachon)
- [Rachel Jones - GitHub](https://github.com/rachelleejones1)
- [Lexi Winstanley - GitHub](https://github.com/lexi-winstanley)

## Motivation
Our motivation to develop this app was that we wanted to create something that would simplify an aspect of travel. In our experience the most stressful part of a trip generally is the days leading up to it when you’re pressed for time and trying to get your bags packed and remembering all the last minute to-dos at work or home. We’ve all made lists of items to pack for trips before and this seemed like an area that could be streamlined. You often end up packing the same items trip after trip but rarely save the list to use later. We wanted to be able to generate some kind of dynamically suggested list that the user could then further customize and save for later.

## Design Process
Our design process started with a basic sketch in Adobe Illustrator. Once we narrowed down our desired functionality and user interaction flow we selected appropriate elements from the Materialize CSS framework to create our front end design. We attempted to create a layout that balanced visual appeal while clearly presenting relevant information to the user.

## Technologies Used
Our application uses Javascript and jQuery to dynamically display results from the Open Weather Map 5 Day Forecast and Webcams.Travel APIs using the destination city and optionally country code. Once the call is successful to the Open Weather Map API, we use the latitude and longitude provided in the result to query the Webcams.Travel API. The webcams.travel api returns all the webcams for a 250 km or about 155 mile radius around the latitude and longitude used in the query and we display up to 6 of the results. The Open Weather Map API returns forecast results for the next 40, 3 hour periods. Our code then loops through all results and gets the highest maximum temperature and lowest minimum temperature to display for each day. The description used is the first that occurs. The average high temperature over the entire forecast period is used to determine whether a warm weather or cold weather packing list should be suggested. The list display is then generated from an array. Once the user gets their results they can remove and add items to their list and they can choose to create an account in order to save their list to firebase which can then be retrieved the next time they log in. We use firebase user authentication to create an email/password login and then a new node is created in our root directory using the user ID.

We used Materialize which is a CSS framework similar to Bootstrap in order to create the front end of our application. We also included a favicon. 

## Future Development
We have many ideas for possible future improvements on our application. We would’ve liked to add the ability to edit items rather than just add or delete. We would also like the user to be able to save search parameters as well as their to-do list under a unique name so that if they traveled to a location frequently they would be able to sign in right away and select that saved search/list. We’d also like them to be able to edit the duration of their trip without completely generating a new list (i.e. if they’ve edited their list exactly as needed but the duration of their trip is longer/shorter we’d like them to be able to change just that parameter. When they save the list we’d also like the checked status to be able to be regenerated when it is retrieved, this would be so that a user could log in the night before a trip when they get the majority of their packing done and then again the morning of travel to add in last minute items. This functionality would necessitate a way to reset all check boxes as well if they were loading the list for a completely new trip. Being able to save named lists would also allow for users to create travel type specific lists (cruise, ski trip, etc).  We also would’ve liked to be able to give our users the option to put in dates further into the future and return historical or statistical data about the weather so they would at least have some idea of the weather for their trip however this information was not available freely from the Open Weather Map APIs. Another improvement could be the ability to add multiple destinations to the search or add activity parameters (i.e. skiing or scuba diving).
