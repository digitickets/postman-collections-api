# Unconfirmed Order Flow

## The Unconfirmed Order Flow

1. Add items to the cart
2. Create a reservation
3. Create an unconfirmed order
4. Take payment from the customer
5. Confirm the order
6. Save the payment

## Creating an unconfirmed order

You can create an unconfirmed order by submitting `confirmed = 0` as part of the order creation request.

If you now fetch the order via the API you will see `paid = 0` - this means that the order has not been confirmed.

`orders.confirmed` is synonymous with `orders.paid` but the in order to trigger the unconfirmed order flow you must submit `confirmed = 0` rather than `paid = 0`. If you submit `paid = 0` then the unconfirmed order flow will not be used.

## Confirming an order

Confirm an order by making `POST /v2/orders/{{orderID}}/confirm`

## Abandoning an unconfirmed order

If you create an unconfirmed order and do not complete the reservation will be deleted after 30 minutes and any reserved spaces will be released, however if you know that you will not complete the order then we recommend that you delete the order using `DELETE /v2/orders/{{orderID}}`

## Prerequisites 

Unconfirmed Order Flow needs to be enabled by DigiTickets. You can see if it is enabled by querying the user.

`/v2/users/auth?apiKey={{apiKey}}&resolve=companies` 

Unconfirmed Order Flow is enabled if `user.companies.settings.enablePropointUnconfirmedOrderFlow = true`
