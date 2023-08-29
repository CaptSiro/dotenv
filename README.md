# dotenv
[Absol package](https://github.com/CaptSiro/absol) for parsing .env files

### Installation

```shell
absol pickup https://github.com/CaptSiro/dotenv.git
```

### Import

```php
require_once __DIR__ . "/absol/import.php";

import("dotenv");
```

### Usage

Parsing `.env` files

```php
$env = new \dotenv\Env("path/to/.env");
```

Accessing variables on `Env` object

```dotenv
# example .env
DB_PASSWORD=
```

```php
// object access
$db_password = $env->DB_PASSWORD; // returns empty string ("")
$db_password = $env->DOES_NOT_EXIST; // returns null

// looselyGet method
$db_password = $env->looselyGet("DB_PASSWORD"); // returns empty string ("")
$db_password = $env->looselyGet("DOES_NOT_EXIST"); // returns null
```

dotenv has build in [retval](https://github.com/CaptSiro/retval) Result support

```php
// get method
$db_password = $env->get("DB_PASSWORD"); // returns successful Result with empty string ("") as value
$db_password = $env->get("DOES_NOT_EXIST"); // returns failed Result
```