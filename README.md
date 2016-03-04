
JSON Database Schema to Migration File Generator For Laravel
========================

This allows you to define your entire database schema in 1 JSON file and generate all the necessary migration files at once.

- [Installation](#installation)
- [Usage](#usage)
- [Changelog](CHANGELOG.md)

<a id="installation"></a>
## Installation

#### Step 1: Add package via composer

Add this package to your `composer.json` file with the following command

```bash
composer require mojopollo/laravel-json-schema
```

#### Step 2: Update laravel 5.x `config/app.php` file

Add the following into the `providers` array:
```php
```

Add the following into the `aliases` array:
```php
```

<a id="usage"></a>
## Usage
Create your JSON schema file and save as ```migration.json``` for example:

```json
{
  "users": {
      "email": "string:unique",
      "password": "string:index",
      "first_name": "string:nullable",
      "last_name": "string:nullable",
      "last_active_at": "timestamp:nullable:index"
  },
  "categories": {
      "name": "string:unique"
  }
}
```

You can generate all of your defined migrations with the following command:

```bash
php artisan make:migration:json --file=migration.json
```

After this command executes you will see all the newly created migration files