
# CA3-PROJECT

This is a PHP-based e-commerce website designed to provide a platform for users to browse, purchase, and manage products online. The application is built using PHP, MySQL, HTML, CSS, and JavaScript.

Features
User Authentication: Secure user authentication and authorization system.
Product Catalog: Browse through a diverse catalog of products.
Shopping Cart: Add products to the cart and manage the cart items.
Checkout Process: Smooth and secure checkout process for completing purchases.
Order Management: Track and manage orders in the user account.
Admin Panel: An admin panel to manage products, orders, and users.
Responsive Design: The website is designed to be responsive, ensuring a seamless experience across devices.

## Installation
Clone the repository: git clone https://github.com/your-username/your-repo.git
Create a MySQL database and import the provided SQL file.
Configure the database connection in config.php.
Start a local server or deploy the application to your web server.


1. Clone the repo and `cd` into it
1. `composer install`
1. Rename or copy `.env.example` file to `.env`
1. `php artisan key:generate`
1. Set your database credentials in your `.env` file
1. Set your Stripe credentials in your `.env` file. Specifically `STRIPE_KEY` and `STRIPE_SECRET`
1. Set your Algolia credentials in your `.env` file. 
 If you don't, it should still work but won't show the paypal payment at checkout.
1. Set your `APP_URL` in your `.env` file. This is needed for Voyager to correctly resolve asset URLs.
1. Set `ADMIN_PASSWORD` in your `.env` file if you want to specify an admin password. If not, the default password is 'password'

1. `npm install`
1. `npm run dev`
1. `php artisan serve` or use Laravel Valet or Laravel Homestead
1. Visit `localhost:8000` in your browser
1. Visit `/admin` if you want to access the Voyager admin backend. Admin User/Password: `admin@admin.com/password`. Admin Web User/Password: `adminweb@adminweb.com/password`

## Features
User Authentication and Authorization
Users can register accounts and log in securely.
Different user roles (customer and admin) with appropriate permissions.
Product Catalog
Display of products with details such as name, price, and description.
Search and filter options for an enhanced shopping experience.
Shopping Cart
Add, update, and remove items from the shopping cart.
Real-time calculation of the total price.
Checkout Process
Secure and straightforward checkout process with multiple payment options.
Order summary and confirmation.
Order Management
Users can view their order history and track the status of their orders.
Admins can manage and update order statuses.
Admin Panel
Admins can add, edit, or remove products from the catalog.
Order management tools for processing and fulfilling orders.
User management functionalities.
Responsive Design
The website is designed to provide a seamless experience on various devices, including desktops, tablets, and smartphones.
## Windows Users - money_format() issue



1. In `app/helpers.php` replace `money_format` line with `return '$'.number_format($price / 100, 2);`
1. In `app/Product.php` replace `money_format` line with `return '$'.number_format($this->price / 100, 2);`
1. In `config/cart.php` set the `thousand_seperator` to an empty string or you might get a 'non well formed numeric value encountered' error. It conflicts with `number_format`.

 Instead of `php artisan ecommerce:install`, migrate and seed the normal way with `php artisan migrate --seed`
