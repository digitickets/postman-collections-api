# Using a DigiTickets Experience Voucher

An example of creating a new order using a DigiTickets Experience Voucher as a payment method.

A DigiTickets voucher is a payment method not a type of discount. Use it as you would any other type of payment method. 

In order to get information about a specific voucher in order to check the balance for example, you need to make an authenticated request to the `/v2/soldgiftvouchers` api endpoint passing the 16 character voucher reference in the `ref` param.

**NOTE** A request for an invalid voucher code will return `[]` a request for a valid voucher code will return the details of that voucher. It is up to you as a developer to check currentBalance, status, expiredAt, etc. to decide how you would like to handle the voucher.

## Prerequisites

To run this collection you will need access to a demo company with an API user, a Ticket, and an Experience Voucher setup ready to be purchased. You will then need to sell an instance of this Experience Voucher in order use it for payment.

### Notes on Experience Voucher Setup

A DigiTickets Experience Voucher has a number of configuration options:

- **Valid For**: Any Item, Selected Items, or Items In Selected Categories
- **Taxed On**: Sale of Voucher, or Use of Voucher
- **Price**: The price of the item.

When using a DigiTickets Experience Voucher you need to assign a price of the item it is used against. This could be less than, equal to, or more than the actual price of the item if it is sold without using an Experience Voucher. As a result of this a Discount is automatically generated.

Create an experience voucher using the default settings. You will need to add:

- Category
- Name
- Price
- Branches
- Delivery Options
- A specific item or items in a category that this voucher is valid for

## Request flow

1. Add products to the cart
2. Create a reservation
3. Check the validity of a voucher
4. Make a cartcalculations request to get discount information. This must include the voucher as a payment.
5. Update (or create) a reservation using the discount information
6. Create an order using the voucher as a payment method

**NOTE** Because an Experience Voucher has a price that could be different to the item it is used to purchase the discount amount and percentage could be negative.

## Set environment variables

Edit your environment to set values for the following variables: 

- apiUrl (e.g. https://api.dtstaging.co.uk)
- apiUser
- apiPassword

(Alternatively create the variables as collection variables)

## Set collection variables

Edit the collection variables specific to this test and set:

- **voucherRef** (the ref of an existing experience voucher that has already been sold to use as the payment method)
- **ticketID** (the id of a ticket to purchase)

**NOTE** You will need to set a new voucherRef for each collection run because Postman cannot prompt for user input.
