Lumen-CORS
==========

[Cross-origin resource sharing](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS) (CORS) Middleware for [Lumen micro-framework](http://lumen.laravel.com/).

## Installation

After you install lumen as per [lumen docs](http://lumen.laravel.com/docs/installation#install-lumen), install lumen-cors from `lumen` folder.

### Install with [Composer](https://packagist.org/packages/palanik/lumen-cors) ###

Run `composer require binjuhor/lumen-cors` to install lumen-cors.

## Usage

### Global CORS

If you want CORS enabled for every HTTP request to your application, head over to your `bootstrap/app.php` file and register your new middleware with the following lines:

```php
$app->middleware([
    Binjuhor\Lumen\Middleware\CorsMiddleware::class
 ]);
```

### CORS for Routes

If you would like to enable CORS to specific routes, you should first assign the `lumen-cors` middleware a short-hand key in your `bootstrap/app.php` file.

```php
$app->routeMiddleware([
    'cors' => 'Binjuhor\Lumen\Middleware\LumenCors',
]);
```

Then, you use the key in the route options array.
```php
$app->get('/api/products', ['middleware' => 'cors', function() {
    //Get all products with this route
}]);
```

More info. - http://lumen.laravel.com/docs/middleware#registering-middleware

## License

[MIT](LICENSE)