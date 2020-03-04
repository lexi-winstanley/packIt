# Pack It!
[View Live](https://lexi-winstanley.github.io/packIt/)

## Motivation 
To create something that would simplify an aspect of travel. In our experience, the most stressful part of a trip is generally the days leading up to it when you’re pressed for time and trying to remember and complete all the last minute to-dos at work or home, including packing your suitcases. We’ve all made lists of items to pack for trips before and this seemed like an area that could be streamlined as we often end up packing the same items trip after trip. We wanted to be able to dynamically generate a suggested list that the user could then further customize and save for later.

## Summary
Pack It! is a web application that helps simplify the task of packing for a trip. The user inputs a destination and trip duration, Pack It! then gets a 5-day forecast for that location and suggests a packing list based on the weather and the trip duration. The location is also used to display webcams near the destination which can further inform the user’s packing plans.  

## Details
When a user navigates to Pack It! they are presented with a landing page where they input a destination and trip duration. These inputs are captured and the location is used to call the Open Weather Map API which returns forecast results for the next 120 hours (about five days) in three hour increments and the latitude and longitude of the forecast location. We then use that latitude and longitude to call the Webcams.Travel API which returns webcams within a 250 km (approximately 155 mile) radius which can help inform the user's packing plans. We display up to six webcam stills on our results page which users can click to navigate to the live stream. Using jQuery we loop through the forecast results from Open Weather Map and get the highest maximum temperature and lowest minimum temperature to display for each day. The weather description used is the first that occurs. The average high temperature over the entire forecast period is used to determine whether a warm weather or cold weather packing list should be suggested. The list display is then generated from an array. Once the user gets their results they can customize their list as desired and choose to create an account in order to save their list to our Firebase database. We use Firebase user authentication to create an email/password login and then a new node is created in our root directory using the user ID and the packing list is saved as an array. The next time the user visits Pack It! they can log in and retrieve their saved list.

## Future Development
We have many ideas for possible future improvements on our application. We would’ve liked to add the ability to edit items rather than just add or delete. We would also like the user to be able to save search parameters as well as their to-do list under a unique name so that if they traveled to a location frequently they would be able to sign in right away and select that saved search/list. We’d also like them to be able to edit the duration of their trip without completely generating a new list (i.e. if they’ve edited their list exactly as needed but the duration of their trip is longer/shorter we’d like them to be able to change just that parameter. When they save the list we’d also like the checked status to be able to be regenerated when it is retrieved, this would be so that a user could log in the night before a trip when they get the majority of their packing done and then again the morning of travel to add in last minute items. This functionality would necessitate a way to reset all check boxes as well if they were loading the list for a completely new trip. Being able to save named lists would also allow for users to create travel type specific lists (cruise, ski trip, etc).  We also would’ve liked to be able to give our users the option to put in dates further into the future and return historical or statistical data about the weather so they would at least have some idea of the weather for their trip however this information was not available freely from the Open Weather Map APIs. Another improvement could be the ability to add multiple destinations to the search or add activity parameters (i.e. skiing or scuba diving).

## Role
Part of a three person developer team. Contributed to design, responsible for altering as needed to make responsive. Authored code to capture user inputs, call Open Weather Map API, parse latitude and longitude to be used in call to Webcams.Travel API, average temperature data and serve appropriate packing list. Created custom weather graphics and favicon.

## Additional Collaborators
[Christina Chon](https://github.com/christinachon)
[Rachel Jones - GitHub](https://github.com/rachelleejones1)

## Technologies
HTML
<br/>Materialize
<br/>CSS
<br/>JavaScript
<br/>jQuery
<br/>OpenWeatherMap API
<br/>Webcams.Travel API
<br/>Firebase
