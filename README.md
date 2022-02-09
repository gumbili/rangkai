## A Minimalistic PHP Layouting Library

> **Rangkai** is a layouting library extracted from a popular framework: CodeIgniter 4. **Rangkai** made to be reused for the process of layouting and rendering pages in the [BuahNaga web framework](https://github.com/gumbili/buahnaga).

### Installing Rangkai

You can easily add the Rangkai Library to your PHP project by running composer installation command like this:
```bash
composer require gumbili/rangkai
```
Make sure you are load the autoload file from vendor folder.
When it is installed, you can display the page in the following way.
```php
<?php

use Gumbili\Rangkai\Rangkai;

// Create new Rangkai instance with provided views path where we store the view file.
$rangkai = new Rangkai('Views');
// Set some data to our view
$rangkai->setData(['name' => 'Gumbili Project']);
// Display our view with echo
// Note: "page" is file path relative to views path
// if your page in Views/home/page.php, you should use "home/page" instead of "page"
echo $rangkai->render('page');

?>
```
### Layouting

Rangkai provide basic layouting for your project, simple but useful.

#### Ceeating A Layout

To creating layout, create new PHP file in your views folder before (defined when creating new Rangkai instance)

```html
<!-- layout.php -->

<html>
    <head>
        <title>Rangkai</title>
    </head>
    <body>
        <header>
            <!-- Assume your header here -->
        </header>
        <main>
            <!-- Here we will place the content -->
            <?php $this->renderSection('content') ?>
        </main>
        <footer>
            <!-- Assume your footer here -->
        </footer>
    </body>
</html>
```
#### Extending Layout

```html
<!-- home.php -->
<?php $this->extend('layout') ?>

<?php $this->section('content') ?>
<div>
    <h1>Hello World!</h1>
</div>
<?php $this->endSection() ?>
```

#### Including Layout
To including layout, simply write a line of code described in the example bellow
```php
<?php $this->include('path to your view file without extension') ?>
```
Example:
```html
<!-- layout.php -->

<html>
    <head>
        <title>Rangkai</title>
    </head>
    <body>
        <header>
            <!-- We are including header here -->
            <?php $this->include('header') ?>
        </header>
        <main>
            <!-- Here we will place the content -->
            <?php $this->renderSection('content') ?>
        </main>
        <footer>
            <!-- We are including footer here -->
            <?php $this->include('footer') ?>
        </footer>
    </body>
</html>
```

### License
```
MIT License

Copyright (c) 2022 Gumbili Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```