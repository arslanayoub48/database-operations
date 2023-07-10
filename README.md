# Common Database Operations

The `Common Database Operations` package provides a trait for Laravel models to handle common database operations and track user activity. It automatically populates common database columns and simplifies the implementation of user tracking features.

## Installation

To install the `Common Database Operations` package, follow these steps:

1. Ensure that you have [Composer](https://getcomposer.org/) installed on your machine.

2. Open your terminal and navigate to your Laravel project's directory.

3. Run the following command to install the package:


```bash
composer require arslanayoub48/common-database-operations

```

4. After the package is installed, Laravel will automatically discover the package and register its service provider.

## Usage

1. Add the `CommonDatabaseOperations` trait to the model(s) where you want to implement common database operations. For example:

```php
use Common\DatabaseOperations\Traits\CommonDatabaseOperations;

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;
use Common\DatabaseOperations\Traits\CommonDatabaseOperations;

class CreateMyTable extends Migration
{
    use CommonDatabaseOperations;

    public function up()
    {
        Schema::create('my_table', function (Blueprint $table) {
            $table->id();
            // Add other columns as needed
            
            $this->addCommonDBFields($table);
            

        });
    }

    // ...
}

```

