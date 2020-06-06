# Php-style-standards
This is built on top of Laravel PHP CS Fixer package inorder to share your coding styles and standards across multiple projects and teams.

### Features
* Run artisan commands to standardize code
* Common repo to store, share across projects

### Versions and Compatability 
Refer required versions of Laravel PHP CS Fixer [here](https://github.com/stechstudio/Laravel-PHP-CS-Fixer)

### Installation
* Add the following in your `composer.json`
```
"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/ajit-t-dev/php-style-standards.git"
        }
    ]
```    
* Now require the package as a --dev dependency

```
composer require ajit-t-dev/php-style-standards --dev
```

### Setup

* PHP-CS-Fixer is going to expect your configuration to be in a /.php_cs.dist file, so we’ll create that.

```
touch .php_cs.dist
```

* Open this file and add the following finder setup for your Laravel app. You can include any other folders you would like fixed as well, but these serve as reasonable defaults.
```
<?php
 $finder = PhpCsFixer\Finder::create()
   ->in([
     __DIR__.'/app',
     __DIR__.'/config',
     __DIR__.'/database',
     __DIR__.'/routes',
     __DIR__.'/tests',
   ]);
 return Ajit\styles($finder);
```

### Usage

Run the following command to fix your coding standards
```
./vendor/bin/php-cs-fixer fix
```
