## EasyShop is an e-commerce website where users can register for an account, log in, browse products, and make purchases.
![EASY SHOP SS](https://github.com/user-attachments/assets/46c3a5ba-8eee-4d7b-a564-2d2cd836cb86)
Starting off this application, I took the approach of first fixing and debugging existing errors to ensure a clean and maintainable workflow. I followed a logical build-and-test order when working with testing requests in Postman, which is especially important since some requests depend on data created by earlier ones. By first verifying that existing functionality works correctly, I was then able to move on to adding new features and enhancements.

## Debugging Order Start with POST Requests
POST requests are crucial since they create the necessary data for other operations. Fixing these first ensures that dependent requests (like GET or DELETE) have the data they need to function.
