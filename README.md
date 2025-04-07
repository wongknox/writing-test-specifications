# writing-test-specifications

Unit Tests:

1. A function called "multiplication" that returns the product of the two input numbers.
   Expect multiplication(3, 4) to be a number
   Expect multiplication(3, 4) to be equal to 12
   Expect multiplication("b", 4) to be an error
   Expect multiplication(5, 0) to be equal to 0
   Expect multiplication(0, 0) to be equal to 0
   Expect multiplication(-3, 4) to be equal to -12
   Expect multiplication(-3, -4) to be equal to 12
   Expect multiplication(2.5, 2) to be equal to 5.0
   Expect multiplication(1.5, 2.5) to be equal to 3.75
   Expect multiplication(1000000, 1000) to be equal to 1000000000
   Expect multiplication(None, 5) to be an error
   Expect multiplication(3) to be an error (not enough arguments, needs two)
   Expect multiplication(3, 4, 5) to be an error (too many arguments, only needs two)

2. A function called "concatOdds" takes two arrays of integers as arguments. It should return a single array that only contains the odd numbers, in ascending order, from both of the arrays.
   Expect concatOdds([1, 2, 3], [4, 5, 6]) to be equal to [1, 3, 5]
   Expect concatOdds([1, 3, 5], [7, 9, 11]) to be equal to [1, 3, 5, 7, 9, 11]
   Expect concatOdds([2, 4], [6, 8]) to be equal to [] (an empty array because there are no odd numbers)
   Expect concatOdds([1, 3, 3], [3, 5, 5]) to be equal to [1, 3, 5] (duplicates are only counted once)
   Expect concatOdds([-1, 2, -3], [4, -5, 6]) to be equal to [-5, -3, -1]
   Expect concatOdds([], [1, 3, 5]) to be equal to [1, 3, 5]
   Expect concatOdds([], []) to be equal to [] (an empty array)
   Expect concatOdds([5, -3, 1], [-7, 9, -11]) to be equal to [-11, -7, -3, 1, 5, 9]
   Expect concatOdds("a string not an array", [1, 3]) to be an error
   Expect concatOdds([1, 3], {1: 2}) to be an error
   Expect concatOdds([1, 3], 456) to be an error

Functional Tests:

1. A shopping cart checkout feature that allows a user to check out as a guest (without an account), or as a logged-in user. They should be allowed to do either, but should be asked if they want to create an account or log in if they check out as a guest.
   #if the user chooses to check out as a guest:
   The user should be guided through the guest checkout process, which involves providing shipping, billing, and payment details
   After sucessfully completing the guest checkout process, the user should see a confirmation message or page with the confirmation number and order details
   After sucessfully completing the guest checkout process, the user should also receive an email containing the confirmation number and order details
   After sucessfully completing the guest checkout process, the user should be prompted to create an account if they haven't already or log in if they already have an account

   #If the user chooses to create an account/ log in to checkout:
   The user should go through the account creation process if they don't already have one, which involves setting up a username and password
   The user should be taken directly to the checkout process after finalizing all items in their cart
   The account checkout process should pre-fill any saved user info to make the process faster and more convenient
   After sucessfully completing the checkout process, the user should see a confirmation message or page with the confirmation number and order details, which should all be accessible in the user's account order history
   After sucessfully completing the checkout process, the user should also receive an email containing the confirmation number and order details, which should all be accessible in the user's account order history

   #If the cart is empty:
   The system should send an error message stating that the cart is empty
   The user should not be presented with the option to check out as a guest or create an account/ log in for checkout since no items have been selected
   The user should see an option to navigate back to the product page

   #If there's an error during the checkout process:
   The user should be presented with an error message if they enter invalid shipping and/ or billing info
   The user should be presented with an error message and the option to try a different payment method if there is an issue with their payment method
   The user should be presented with a notification if an item in their cart goes out of stock during the checkout process, and the item should subsequently be automatically removed from the user's cart
