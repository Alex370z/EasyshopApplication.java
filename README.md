## 🛒EasyShop is an e-commerce website where users can register for an account, log in, browse products, and make purchases.
![EASY SHOP SS](https://github.com/user-attachments/assets/46c3a5ba-8eee-4d7b-a564-2d2cd836cb86)
Starting off this application, I took the approach of first fixing and debugging existing errors to ensure a clean and maintainable workflow. I followed a logical build-and-test order when working with testing requests in Postman, which is especially important since some requests depend on data created by earlier ones. By first verifying that existing functionality works correctly, I was then able to move on to adding new features and enhancements.

## Debugging Order Start with POST Requests
POST requests are crucial since they create the necessary data for other operations. Fixing these first ensures that dependent requests (like GET or DELETE) have the data they need to function.

## Debug: POST /register
The POST /register endpoint is essential for creating test user accounts and is required before any login or user-authenticated actions.

Issue: Initial request failed.

Fix: Adjusted the request body to use valid test data.

✅ Result: User jerry was registered successfully. The password 123456cereal was properly hashed and stored.

## Debug: POST /login
Issue: Initially returned 401 Unauthorized – Bad Credentials.

Fix: Corrected the username and password in Postman.

✅ Result: Login now returns 200 OK and a valid token.
Postman test script detects and extracts the token successfully.

## Debugging GET requests
This is a foundational request, often used to retrieve data before creating or filtering products.

Cause: The test script incorrectly expected exactly 1 item in the response.

Fix: Updated the script to only check that the response is an array, without assuming the number of items.

## Avoid duplicates
I avoided duplicating logic or making redundant requests. For example, there were multiple GET /categories requests—some of which were unnecessary and caused confusion. I kept the collection clean by removing these duplicates and retaining only what was necessary for testing.

## Debugging DELETE requests
Finally, test and debug DELETE endpoints once all creation and retrieval logic is verified.
## Fixed Features Added
## User Register/Login
At the initial stage of debugging, EASYSHOP didn’t allow users to log in or create an account, or at least those functions weren’t working as intended.
While debugging the POST register request, I edited the NewUserName, and the issue was resolved, allowing successful user registration and login.
![login easyshop](https://github.com/user-attachments/assets/8fad0068-81e3-4ce6-a636-6e036d80bb07)
## Display products by category
![CATEGORIES EASYSHOP](https://github.com/user-attachments/assets/0cf0f9b5-07b7-471e-8bc0-4930e19afa48)

## Features to Implement
Analyzing the features of high-quality websites shows that they are well-organized and offer an easily readable user interface. They allow users to access their profiles, including settings, personal information, security, and order history. Also, when users are browsing products, the website recommends a variety of similar items, which can capture the user's attention and interest. Another feature they implement is allowing users to leave comments and reviews on products. This helps ensure that customers can make confident and informed purchases.

🔍An easily readable user interface is the number one priority. When a website is clean and navigation is smooth, it enhances the shopping experience and doesn't overwhelm the user.

🔎Second would be the must-have features, such as product search, filtering, and categorization. 

👤Third is the addition of user profiles for account management, security, reviews, and comments.

✨Fourth are quality-of-life features that enhance the user experience, such as suggesting products the user was previously viewing or smoother animations.

## Interesting Code
An interesting piece of code is the Authentication Controller. The Authentication Controller plays a crucial role in applications, as it handles new user data such as usernames, emails, and passwords. It validates the input, saves the user to the database, and returns a success response.
