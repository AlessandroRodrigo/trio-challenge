# Technical assessment for Bike Rental

## Requirements

### ReactJS

- Create a rent component inside of the bike-detail page (see Figma)
- Whenever the user picks a Date range, the system displays the final amount and fees
- Feel free to use an external package for the date picker
- Whenever the user clicks on Add to booking button, the app rents a bike
- Connect the UI with the API Endpoints

### NodeJS

- Create an endpoint to rent a bike following rules below:
- The BikeRent fees are 15% of each rent
- It’s only possible to rent by days, i.e. we won’t deal with hours of rent

# Technical design

## Solution

- The calendas was made exactly as the figma prototype;
- The calendar component is reusable;
- The calendar component is completely tested;
- The calendar component is responsive;
- The user can't rent the same bike in the same period;
- The user can't rent a bike in the past;
- The user can rent a bike and will receive a success message;
- The backend code was made following strictly the purposed clean architecture;

## General questions

- The challenge didn't ask for a validation about the rental dates, but I did something on this way, just to improve the quality of the service.

## Frontend

- I took the decision of make the calendar component from scratch, because I didn't find any library that fits the requirements, mainly the design, I wanted to reach a near level of the figma prototype and I tested everything about this component. I used the `Context API` to handle state and functions inside the calendar component.

  - Advantages: I could make the component exactly as I wanted, I could handle the state and functions inside the component, I could make the component reusable and completely tested.
  - Disadvantages: I spent a lot of time to make the component, I could use a library to make it faster.

- I integrated the calendar component with the BikeDetails component and adjusted the calculations to show the final amount and fees. On the BikeDetails container level I handled the booking action, calling the API endpoint and showing a success message to the user. I tried to make following the patterns of the project, the objective was integrate this new feature as if it were just another existing component. To finish, I also tried to use very simple and clean code.

### Next steps

- It would be nice improve the performance, with profiling and techniques like `memo` and `useCallback`;
- It would be nice improve the state management;
- Improve the API calls, maybe using a library like `react-query` or `swr`;
- write more tests ;
- Give a better feedback to the user when he clicks on the button to rent the bike and it already is rented.

## Backend

- The proposal of clean architecture was strictly adhered to;
- The schema.prisma was modified with the addition of a new model called `Rental` for rental control;
- A new repository was created for this new model;
- A new usecase was established to manage the business rules of the rental;
- A new controller was developed to manage the API endpoint;
- A new route was set up to handle the API endpoint;
- All created elements were tested, following the project's testing patterns;
- A validation about the rental date was created, it is not possible the same bike to be rented in the same period.

### Next steps

- It would be nice to improve the tests about this new feature, mainly the validation about the rental date;
- It would be nice create a middleware to handle authentication.
