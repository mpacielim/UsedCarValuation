# Practical Assignment 11.1 - What Drives the Price of a Car?

## Introduction
This report details the requested investigation into specific factors that influence the price a consumer is willing to pay for a used car.  This information is intended to be used for the purpose of fine-tuning the client's existing used car inventory.

## Data Source
The investigation was conducted by analysing data from a dataset of 3 million cars.  The data was shrunk to a representative sample of 426,000 entries in order to assist with speed of processing.

## Links
[Link to Data](https://github.com/mpacielim/UsedCarValuation/tree/main/data)

[Link to Technical Report](https://github.com/mpacielim/UsedCarValuation/blob/main/Used%20Car%20Valuation%20Technical%20Report.ipynb)

## Findings
The dataset was further reduced by 55% to 200,000 samples after cleaning it to remove:
- Duplicate VINs (these were repeat entries for cars listed at the same price in multiple states)
- Nonsensical values (such as VINs without letters, Odometer > 300,000 miles, price > 66,500 (99% of prices were below this)

Four types of machine learning models were trained and tested on the data, using methods to optimize each type of model. 

The best performing model was able to explain approximately 67% of the variation in price in the testing data.  The Mean Absolute Error (MAE) of this model indicates that on average, its prediction for price is off by approximately +/-4,900 USD.

Nevertheless, deepdiving further into the best performing model, we used two methods to ascertain which features were most important.

1. In general, the features were determined to be most important in affect the models performance in the following order:
- Odometer
- Year
- Fuel
- Manufacturer
- Drive
- Type
- Cylinders
- State
- Title Status
- Transmission
- Paint Color
- Condition
- Size

Odometer and year were most important by far, with the last 3 items (paint color, condition and size) barely having an affect.

2. By inspecting coefficients of model, the top 11 exact sub-categories that were seen to be most important were in order:

Positive impact on price:
1. Manufacturer - Tesla
2. Manufacturer - Datsun
3. Manufacturer - Aston Martin
4. Manufacturer - Porsche
5. Manufacturer - Ferrari
6. Type - Pick Up
7. Type - Truck
8. Year
9. Manufacturer - Rover
10. Type - Offroad
11. Manufacturer - Land Rover

Negative impact on price:
1. Manufacturer - Morgan
2. Fuel - Electric
3. Fuel - Hybrid
4. Fuel - Gas
5. Manufacturer - Harley Davidson
6. Manufacturer - Fiat
7. Fuel - Other
8. Title Status - Parts Only
9. Manufacturer - Mitsubishi
10. Manufacturer - Kia
11. Odometer

## Next Steps
There is still a long way to go to optimize this type of model to more accurately predict price.  Investigating other models and further tuning hyperparameters is suggested as a next step to improving the model.
