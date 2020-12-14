# clever-php
The Clever API

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 2.0.0
- Build package: io.swagger.codegen.languages.PhpClientCodegen

## Requirements

PHP 5.4.0 and later

## API Documentation
View more detailed documentation [here](docs/README.md)

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/clever/clever-php"
        }
    ],
    "require": {
       "clever/clever": "*"
}
}
```

Then run `composer install`

**Note that it is necessary to include the vcs link to be sure that you are pulling from this repo.**

The package manager for composer currently does **not** point to the correct repo for [clever/clever-php](https://packagist.org/packages/clever/clever-php).

We are published as [clever/clever](https://packagist.org/packages/clever/clever).

### Manual Installation

Download the files and include `autoload.php`:

```php
require_once('/path/to/clever-php/autoload.php');
```

## Tests

To run the unit tests:

```
make test
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once('./autoload.php');

$api_instance = new Clever\Api\DataApi();

// Note: This is hard coded for demo purposes only. Keep your access tokens secret!
// https://dev.clever.com/docs/security#section-security-best-practices
$api_instance->getConfig()->setAccessToken('TEST_TOKEN');

try {
    $result = $api_instance->getStudents();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DataApi->getStudents: ', $e->getMessage(), PHP_EOL;
}

?>
```

## Updating the Library

1. Git clone swagger-codegen (https://github.com/swagger-api/swagger-codegen)

2. Git clone Clever's swagger-api repo (https://github.com/Clever/swagger-api)

3. Run this command in the swagger-codegen repo
```
java -jar modules/swagger-codegen-cli/target/swagger-codegen-cli.jar generate -i $PATH_TO_SWAGGER_API_REPO/v2.0-client.yml -c $PATH_TO_THIS_REPO/override/config.json -l php -o $PATH_TO_THIS_REPO --additional-properties packageVersion=$VERSION
```

4. Run `make override` to copy over the override files

## Publishing

1. Update CHANGELOG
1. `git tag -a vX.X.X`
1. `git push --tags origin HEAD:master`
1. Log into [Packagist](https://packagist.org/packages/clever/clever) (credentials are in 1PFT) and click "Update"