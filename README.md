# PHPStruct class

[![Build Status](https://travis-ci.org/danog/PHPStruct.svg?branch=master)](https://travis-ci.org/danog/PHPStruct)
[![StyleCI](https://styleci.io/repos/62454134/shield)](https://styleci.io/repos/62454134)

Licensed under MIT.

PHP implementation of Python's struct module.

This library was created to help me develop a [client for the mtproto protocol](https://github.com/danog/MadelineProto).  

The functions and the formats are exactly the ones used in python's struct 
(https://docs.python.org/3/library/struct.html)

For now custom byte size may not work properly on certain machines for the i, I, f and d formats.

## Installation

Install using composer:
```
composer require danog/phpstruct
```

# Usage

```
require('vendor/autoload.php');
$struct = new \danog\PHP\Struct();
$pack = $struct->pack("2cxi", "ab", 44);
$unpack = $struct->unpack("2cxi", $pack);
var_dump($unpack);
$count = $struct->calcsize("2cxi");
```

This library can also be used statically:


```
require('vendor/autoload.php');
$pack = \danog\PHP\Struct::pack("2cxi", "ab", 44);
$unpack = \danog\PHP\Struct::unpack("2cxi", $pack);
var_dump($unpack);
$count = \danog\PHP\Struct::calcsize("2cxi");
```


[Daniil Gentili](http://daniil.it)
