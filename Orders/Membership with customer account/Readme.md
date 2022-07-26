# Create a membership order

An example of creating a new membership order with a customer account.

## Request flow

1. Login and get an ApiKey
2. Get a list of membership plans
3. Create a customer account
2. Create a reservation
4. Create an order using the reservation token and customer account from the previous steps


## Prerequisites

To run this collection you will need access to a demo company with an API user and a membership plan.

In this example we make a request to get information about membership plans, then filter one plan which is then used in the reservation request. In reality this step would not usually be part of the order process as standing data like this would be usually be synced periodically and then cached locally.

This test assumes that the membership will be created linked to a customerAccount.

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

## Notes

Most memberships are created in the context of a customer account so instead of passing through all the member details again we can simply create a customer account and then pass through the `customerAccountID` and `contactID` when we make the order.




