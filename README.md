# Technical assessment for Bike Rental

## Requirements

### ReactJS

Create a rent component inside of the bike-detail page (see Figma)
Whenever the user picks a Date range, the system displays the final amount and fees
Feel free to use an external package for the date picker
Whenever the user clicks on Add to booking button, the app rents a bike
Connect the UI with the API Endpoints

### NodeJS

Create an endpoint to rent a bike following rules below:
The BikeRent fees are 15% of each rent
It’s only possible to rent by days, i.e. we won’t deal with hours of rent

# Technical design

## Frontend

I took the decision of make the calendar component from scratch, because I didn't find any library that fits the requirements, mainly the design, I wanted to reach a near level of the figma prototype and I tested everything about this component. I used the `Context API` to handle state and functions inside the calendar component. Out of this component, I integrated with the BikeDetails component and adjusted the calculations to show the final amount and fees. On the BikeDetails container level I handled the booking action, calling the API endpoint and showing a success message to the user. I tried to make following the patterns of the project, the objective was integrate this new feature as if it were just another existing component. To finish, I also tried to use very simple and clean code.

## Backend
