## A Minimalistic PHP Layouting Library

> **Rangkai** is a layouting library extracted from a popular framework: CodeIgniter 4. **Rangkai** made to be reused for the process of layouting and rendering pages in the [BuahNaga web framework](https://github.com/gumbili/buahnaga).

### Simple Usage
```php
<?php

// Load the autoload file. You don't need to do this if you are installing Rangkai with composer install
require_once './vendor/autoload.php';

use Gumbili\Rangkai\Rangkai;

// Create new Rangkai instance with provided views path where we store the view file.
$rangkai = new Rangkai('Views');
// Set some data to our view
$rangkai->setData(['name' => 'Gumbili Project']);
// Display our view with echo
echo $rangkai->render('page');

?>
```