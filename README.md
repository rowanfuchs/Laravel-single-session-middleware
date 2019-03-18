## Laravel single session middleware
With this single session middleware Laravel will enforce a single session per user from any location.
When a new session starts the old user will be logged out.

### Installation

Install with composer:

```
composer require rowanfuchs/singlesession
```

Add the following line to your routeMiddleware in app\Http\Kernel.php

```php
'singlesession' => \rowanfuchs\SingleSession\Middleware\SingleSession::class,
```

Then use the following line in the __construct of your controller 

```php
$this->middleware('singlesession');
```

Or assign it via the route group

```php
Route::group(['middleware' => ['singlesession']], function () {
    Route::get('/home', 'HomeController@index')->name('home');
});
```

## License

### MIT

Copyright (c) 2018 Rowan Fuchs, https://rowanfuchs.nl

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
