# Create a membership order

An example of creating a new membership order passing in a member name and email address. This is the most basic scenario for a membership order.

## Request flow

1. Login and get an ApiKey
2. Get a list of membership plans
2. Create a reservation
4. Create an order using the reservation token from the previous step


## Prerequisites

To run this collection you will need access to a demo company with an API user and a membership plan.

In this example we make a request to get information about membership plans, then filter one plan which is then used in the reservation request. In reality this step would not usually be part of the order process as standing data like this would be usually be synced periodically and then cached locally.

`membershipPlanID === itemID`

## Set environment variables

Edit your environment to set values for the following variables: 

- apiUrl (e.g. https://api.dtstaging.co.uk)
- apiUser
- apiPassword

(Alternatively create the variables as collection variables)

## Set collection variables

Edit the collection variables specific to this test and set:

- **membershipPlanName** (the name of the membershipPlan to purchase)
- **branchID**

## Notes
