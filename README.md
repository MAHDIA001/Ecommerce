


The website resembles a real store and you can add products to your cart and pay for them. If you want to try the checkout process, you can use the dummy card number provided by stripe for testing which is 4242 4242 4242 4242 with any expiration date, CVC, and zip codes. Please <u><b>DO NOT</b></u> provide real card number and data.

In order to access the admin panel on "/admin" you need to provide the admin email and password.

## Run

To run this application, you have to set your own environmental variables. For security reasons, some variables have been hidden from view and used as environmental variables with the help of dotenv package. Below are the variables that you need to set in order to run the application:

- MONGO_URI: this is the connection string of your MongoDB Atlas database.

- SESSION_SECRET: a secret message for the session. You can use any string here.

- STRIPE_PRIVATE_KEY: the stripe package is used to process payment in the checkout route. To get this, you should set up a stripe account and put your private API key here.

- GMAIL_EMAIL, GMAIL_PASSWORD: the email and password given to nodemailer to send/receive the email. Please put a real email and password here because you will receive the messages sent from the contact us form on this email.

- ADMIN_EMAIL, ADMIN_PASSWORD: the email and password used to log into the admin panel using AdminBro. You can put any email and password here.

- ADMIN_COOKIE_NAME, ADMIN_COOKIE_PASSWORD: the cookie name and password used in the AdminBro authentication method. You can put any strings here.

After you've set these environmental variables in the .env file at the root of the project, you need to navigate to the "seedDB" folder and run "node category-seed.js" and "node products-seed.js" to fill your empty MongoDB Atlas database.

Now you can run "npm start" in the terminal and the application should work.


## Features

The application displays a virtual bags store that contains virtual products and contact information.

Users can do the following:

- Create an account, login or logout
- Browse available products added by the admin
- Add products to the shopping cart
- Delete products from the shopping cart
- Display the shopping cart
- To checkout, a user must be logged in
- Checkout information is processed using stripe and the payment is send to the admin
- The profile contains all the orders a user has made

Admins can do the following:

- Login or logout to the admin panel
- View all the information stored in the database. They can view/add/edit/delete orders, users, products and categories. The cart model cannot be modified by an admin because a cart is either modified by the logged in user before the purchase or deleted after the purchase.

