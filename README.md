# Capstone Project - Regression - Transport Demand Prediction

### Problem Statement

We're going to look at data from Mobiticket, which sells bus tickets. We'll focus on 14 towns northwest of Nairobi towards Lake Victoria. Our goal is to figure out how many tickets will be sold for buses that arrive in Nairobi from those towns.

### Data Summary

This dataset includes the variables from  17 October 2017 to  20 April 2018

- ride_id: unique ID of a vehicle on a specific route on a specific day and time.
- seat_number: seat assigned to ticket
- payment_method: method used by customer to purchase ticket from Mobiticket 
- payment_receipt: unique id number for ticket purchased from Mobiticket
- travel_date: date of ride departure. (MM/DD/YYYY)
- travel_time: scheduled departure time of ride. Rides generally depart on time. (hh:mm)
- travel_from: town from which ride originated
- travel_to: destination of ride. All rides are to Nairobi.
- car_type: vehicle type (shuttle or bus)
- max_capacity: number of seats on the vehicle

### After some Data Wrangling and Feature Manipulation we Found this :

To enhance the performance of the model, additional features have been generated. These new features aim to provide more relevant information and contribute to improved predictions. These include:

- Some columns travel_month, travel_day_of_year, travel_day_of_month and time_period_of_day have skewed data, to handle this, new weight wise columns have been created by taking log transformation.
- How frequently the bus arrives at every source destination can be a major factor effecting the number of tickets sold on that route. Hence, the following columns are created based on the frequency of bus/shuttle arriving :
    - Time_gap_btw_0_1_next_bus
    - Time_gap_btw_0_1_previous_bus
    - Time_gap_btw_0_2_next_bus
    - Time_gap_btw_0_2_previous_bus
    - Time_gap_btw_0_3_next_bus
    - Time_gap_btw_0_3_previous_bus
    - Time_gap_btw_next_previous_bus
- The distance of source to destination (Nairobi) can also be a major factor effecting the number of tickets, hence, a new column called distance_to_destination is created containing distances of all the 14 sources to Nairobi.
- To deal with multicollinearity, few of the columns are dropped.
- Categorical encoding is done on few columns and finally data is split into training and test.


### ML Implimantation :

- We Found Random Forest is Best for this dataset.
##### ![my table capstone project](https://github.com/Hasnain-Rizvi/Capstone-Project---Regression/assets/124716951/15d4bcc9-35df-4e78-ac8b-be64cc39d4ec)
#### ![featurs of mine](https://github.com/Hasnain-Rizvi/Capstone-Project---Regression/assets/124716951/7113fae0-9403-4411-bd8f-e3caa745245e)

### Conclusion 
- This project resulted in a hyperparameter-tuned Random Forest-based predictive model, achieving an R2 score of 94.4% for training data and 94.6% for test data.

