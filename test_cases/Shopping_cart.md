# Test Cases Samples #

These test cases can be applied to any system that has a shopping cart.

| No. |	Test Case |	Expected Result |
|----|---------|-----------------|
|1 |Adding a product to the cart.|Product successfully added to cart.|
|2 |Continue shopping after adding product to your cart. |Product successfully added to cart.|
|3 |Adding a few products to the basket from the quantity available in stock.	|Products successfully added to cart.|
|4 |Removing the product from the cart using the cancel or remove button.| The product has been successfully removed from the cart.|
|5 |Removing products from the cart by changing the number of product, e.g. from 1 to 0.	| The deleted product is no longer in the cart.|
|6 |Removing products from the basket by removing the value from the quantity field, leaving the form empty. |The deleted product is no longer in the cart.|
|7 |Adding a product to the cart after selecting the available variant e.g. T-shirts in the selected size	(or something else).| Product successfully added to cart.|
|8 |Adding a product to the cart without selecting the appropriate product variant e.g. T-shirts without size selection.|	It is not possible to add a product. / The user should see a validation message.|
|9 |Increasing/decreasing the number of products in the basket using the up and down buttons. |	Correct increase/decrease in the number of products in the cart.|
|10 |Specifying the number of products in the cart using valid values.	|The number of products in the cart has been correctly specified.|
|11	|Specifying the number of items in a cart using invalid data, e.g. a non-integer or negative number. | Number cannot be determined. / The user should see a validation message.|
|12	| Specifying the number of products using letters or special characters.|It is not possible to enter letters or characters that are not allowed. / The user should see a validation message.|
|13 | Checking the possibility of adding a product out of stock to the cart.| It is not possible to add the product to the cart.|
|14	| Checking the possibility of adding more products to the cart than the number available in the stock.|	It is not possible to add more products to the cart than the quantity in stock.|
|15| Refreshing the page while there are added products in the basket.| The content is still in the shopping cart.|
|16 | After hovering the mouse over the cart, its contents are displayed (only if it is intended). |The content shows up.|
|17	|Logging in to your account after adding the product to your cart. _(For users with an account)_| Signing into your account does not clear the contents of shopping cart.|
|18	|Log out and log back in.	_(For users with an account)_|Signing out does not clear the contents of your shopping cart. After logging back in, the products are still in the cart.|

## Test raport based on above test cases: ##
1. [ZimaSklep](https://github.com/KarolinaSzczech/Manual_tester_Portfolio/blob/nowy_raport/test_raport/ZimaSklep.md)
2. [TestLinkReport](https://github.com/KarolinaSzczech/Manual_tester_Portfolio/blob/nowy_raport/test_raport/Przypadki%20testowe%20zrealizowane%20w%20TestLink.pdf)
