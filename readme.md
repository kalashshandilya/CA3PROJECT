
# CA3-PROJECT
## Installation

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


## Windows Users - money_format() issue



1. In `app/helpers.php` replace `money_format` line with `return '$'.number_format($price / 100, 2);`
1. In `app/Product.php` replace `money_format` line with `return '$'.number_format($this->price / 100, 2);`
1. In `config/cart.php` set the `thousand_seperator` to an empty string or you might get a 'non well formed numeric value encountered' error. It conflicts with `number_format`.


1. Clone the repo and `cd` into it
1. `git checkout f4f651a8a35ebb2ff38ba15771fd65c93051f947772`
 Instead of `php artisan ecommerce:install`, migrate and seed the normal way with `php artisan migrate --seed`
