# Laravel Categories

[![GitHub Tests Action Status](https://img.shields.io/github/workflow/status/kodekeep/laravel-categories/run-tests?label=tests)](https://github.com/kodekeep/laravel-categories/actions?query=workflow%3Arun-tests+branch%3Amaster)
[![Code Coverage](https://badgen.now.sh/codecov/c/github/kodekeep/laravel-categories)](https://codecov.io/gh/kodekeep/laravel-categories)
[![Minimum PHP Version](https://badgen.net/packagist/php/kodekeep/laravel-categories)](https://packagist.org/packages/kodekeep/laravel-categories)
[![Latest Version](https://badgen.net/packagist/v/kodekeep/laravel-categories)](https://packagist.org/packages/kodekeep/laravel-categories)
[![Total Downloads](https://badgen.net/packagist/dt/kodekeep/laravel-categories)](https://packagist.org/packages/kodekeep/laravel-categories)
[![License](https://badgen.net/packagist/license/kodekeep/laravel-categories)](https://packagist.org/packages/kodekeep/laravel-categories)

> Categories for Eloquent Models.

## Installation

```bash
composer require kodekeep/laravel-categories
```

## Usage

Check [lazychaser/laravel-nestedset](https://github.com/lazychaser/laravel-nestedset) to learn how to create, update, delete, etc. categories.

### Setup a Model

``` php
<?php

namespace App;

use KodeKeep\Categories\Concerns\HasCategories;
use Illuminate\Database\Eloquent\Model;

class Post extends Model
{
    use HasCategories;
}
```

### Get an array with ids and names of categories (useful for drop-downs)

```php
$post->categoriesList();
```

### Attach the Post Model these Categories

```php
$post->syncCategories([Category::find(1), Category::find(2), Category::find(3)]);
```

### Detach the Post Model from these Categories

```php
$post->syncCategories([]);
```

### Detach the Post Model from all Categories and attach it to the new ones

```php
$post->syncCategories([Category::find(1), Category::find(3)]);
```

### Attach the Post Model to the given Category

```php
$post->assignCategory(Category::find(1));
```

### Detach the Post Model from the given Category

```php
$post->removeCategory(Category::find(1));
```

### Get all Posts that are attached to the given Category

```php
Category::first()->entries(Post::class)->get();
```

## Testing

``` bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover a security vulnerability within this package, please send an e-mail to hello@kodekeep.com. All security vulnerabilities will be promptly addressed.

## Credits

This project exists thanks to all the people who [contribute](../../contributors).

## License

Mozilla Public License Version 2.0 (MPL-2.0). Please see [License File](LICENSE.md) for more information.
