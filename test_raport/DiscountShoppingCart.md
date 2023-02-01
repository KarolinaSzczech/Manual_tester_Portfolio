# Test cases for correctly verifying the calculation of discounts in the shopping cart on the site https://natura.pl #


 **Promotion conditions**

1. The promotion applies only to Botanic products.
2. The discount is 50% on the second product.
3. The discount is calculated for a cheaper product or at the same price.


**Used for testing:**

**Desktop:**

OS: Windows 10 PRO
 - Browser: Chrome Version 107.0.5304.108) 
 - Browser: Firefox Version 109.0
 - Browser: Firefox Developer Edition Version 108.0b6
 - Browser: Microsoft Edge Version 107.0.1418.56
 - Browser: Opera Version 94.0.4606.37 

**Testing time:**
 - Shopping cart testing - 2h
 - Preparing a report - 2h


| No. |	Test Case |Preconditions|	Expected Result | Actual Result |
|----|----|----|----|----|
|1 |Adding a first promotional product to the cart.|Empty cart.| Product successfully added to cart.| Correct result.|
|2 |Increasing the number of product in the cart from 1 to 2.	|One promotional product in cart.|Increasing the number of products in the basket, the price is recalculated, the discount for the second product is granted in the correct amount.	| Correct result.|
|3 |Decreasing the number of items in the cart from 1 to 2.|There are two products in the shopping cart.	|Decreasing the number of products in the cart, the price is recalculated, no discount.	| Correct result.|
|4 |Adding a different promotional product at the same price as the first product.|There is one promotional product in the cart.|The product is correctly added to the basket, the price is recalculated, the discount for the second product is granted in the correct amount.	| Correct result.|
|5 |Adding a different promotional product is cheaper than the first product to the cart. |There is one promotional product in the cart. | The product is correctly added to the basket, the price is recalculated, the discount for the second product is granted in the correct amount.	| Correct result.|
|6 |Adding a different promotional product that is more expensive than the first product in the cart.|There is one promotional product in the cart. |The product is correctly added to the basket, the price is recalculated, the discount is granted to the first (cheaper) product in the correct amount.	| Correct result.| 
|7 |Increase by 1 or add 1 product to the cart. |There are two products in the basket that meet the promotional conditions. |The discount applies to the cheaper product. The other two products are at a non-promotional price. The discount amount is correct. |  Correct result.| 
|8 |Increase by 2 or add 2 product to the cart. |There are two products in the basket that meet the promotional conditions. |The discount applies to the two cheaper products. The other two products are at a non-promotional price. The discount amount is correct. |  Correct result.| 
|9 |Adding non-promotional product to the cart. |There are promotional products in the cart. |The discount does not apply to non-promotional products.  |Correct result.| 
|10 |Removing all the promotional products from the basket and leaving in the cart the non-promotional products. |There are promotional products in the cart. |The discount does not apply. |Correct result. | 








