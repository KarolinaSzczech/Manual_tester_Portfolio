# Test Report of the functionality shopping cart on site https://zima.sklep.pl #


**Used for testing:**

**Desktop:**

OS: Windows 10 PRO
 - Browser: Chrome version 107.0.5304.108 (Oficjalna wersja) (64-bitowa)
 - Browser: Firefox Wersja 109.0 (64 bity)
 - Browser: Firefox Developer Edition Wersja 108.0b6 (64 bity)
 - Browser: Microsoft Edge Wersja 107.0.1418.56 (Oficjalna kompilacja) (wersja 64-bitowa)
 - Browser: Opera Wersja Wersja:94.0.4606.37 (wersja 64-bitowa)

**Testing time:**
 - Shopping cart testing - 2h
 - Preparing a report - 2h


| No. |	Test Case |	Expected Result | Received Result |
|----|---------|-----------------|-------|
|1 |Adding a product to the cart.|Product successfully added to cart.| Correct result.|
|2 |Continue shopping after adding product to your cart. |Product successfully added to cart| Correct result.|
|3 |Adding a few products to the basket from the quantity available in stock.	|Products successfully added to cart.	| Correct result.|
|4 |Removing the product from the cart using the cancel or remove button.	|The product has been successfully removed from the cart.	| Correct result.|
|5 |Removing products from the cart by changing the number of product, e.g. from 1 to 0.	| The deleted product is no longer in the cart. | Correct result.|
|6 |Removing products from the basket by removing the value from the quantity field, leaving the form empty.	|The deleted product is no longer in the cart.	| Correct result.|
|7 |Adding a product to the cart after selecting the available variant e.g. T-shirts in the selected size	(or something else).| Product successfully added to cart. | Correct result.|
|8 |Adding a product to the cart without selecting the appropriate product variant e.g. T-shirts without size selection.	|	It is not possible to add a product. / The user should see a validation message.| Correct result. It is not possible to add a product. |
|9 |Increasing/decreasing the number of products in the basket using the up and down buttons.	 |	Correct increase/decrease in the number of products in the cart.| The website does not have such an option. Changing the number of items is done by entering the appropriate numerical value. |
|10 |Specifying the number of products in the cart using valid values.	 |The number of products in the cart has been correctly specified.	| Correct result.|
|11	|Specifying the number of items in a cart using invalid data, e.g. a non-integer or negative number. | Number cannot be determined. / The user should see a validation message. |Correct result. If you enter a non-integer number, e.g. 0.5, a validation message appears: "Enter a valid value. The two closest valid values are 0 and 1".If you enter a negative value, e.g. -1, the following message appears: "Value cannot be less than 0".|
|12	| Specifying the number of products using letters or special characters. 	|It is not possible to enter letters or characters that are not allowed. / The user should see a validation message. | Correct result. No letters or special characters can be entered. | 
|13 | Checking the possibility of adding a product out of stock to the cart.	 | It is not possible to add the product to the cart.	| Correct result. No add to cart button. |
|14	| Checking the possibility of adding more products to the cart than the number available in the stock |	It is not possible to add more products to the cart than the quantity in stock. | Correct result. A validation message appears. If there are 2 products in stock and we want 20, a message appears that we can only choose two products. | Correct result.|
|15| Refreshing the page while there are added products in the basket.	| The content is still in the shopping cart. | Correct result.|
|16 | After hovering the mouse over the cart, its contents are displayed (only if it is intended).	|The content shows up. | Correct result.|
|17	| Logging in to your account after adding the product to your cart. _(For users with an account)_ | Signing into your account does not clear the contents of shopping cart.	| Correct result. The products are still in the cart. |
|18	|Log out and log back in.  _(For users with an account)_	|Signing out does not clear the contents of your shopping cart. After logging back in, the products are still in the cart.  | Correct result. |

