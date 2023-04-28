# laravel9-fullcalendar

Esse pacote foi criado tendo como base o projeto [Laravel 5 Full Calendar Helper](https://github.com/maddhatter/laravel-fullcalendar)

## Requirements

* Laravel Framework 9+

## Installation

```sh
$ composer require mffonseca/laravel9-fullcalendar
```

## Registering the Package

 - Em ```config/app.php```

```php
/**
 * Package Service Provider
 */

'providers' => [
    // ...

    Mfonseca\LaravelFullcalendar\ServiceProvider::class,
],
```

- Em ```config/app.php```

```php
/**
 * Package Alias
 */

'aliases' => [
    // ...

    'Calendar' => Mfonseca\LaravelFullcalendar\Facades\Calendar::class,
],
```

## Criando eventos

```php
$event = \Calendar::event(
    "Valentine's Day", //event title
    true, //full day event?
    '2015-02-14', //start time, must be a DateTime object or valid DateTime format (http://bit.ly/1z7QWbg)
    '2015-02-14', //end time, must be a DateTime object or valid DateTime format (http://bit.ly/1z7QWbg),
    1, //optional event ID
    [
        'url' => 'http://full-calendar.io'
    ]
);
```

## View

```html
<!doctype html>
<html lang="en">
<head>
    <script src="//cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/moment.js/2.9.0/moment.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/2.2.7/fullcalendar.min.js"></script>
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/2.2.7/fullcalendar.min.css"/>


    <style>
        /* ... */
    </style>
</head>
<body>
    {!! $calendar->calendar() !!}
    {!! $calendar->script() !!}
</body>
</html>
```