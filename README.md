# Shieldfy Normaization Package

Shieldfy Normalizer is package to normalize the input to prepare for running hardcore IDS/IPS rules.
The purpose of the Normalizers is to normalize the inputs to fight against WAF Bypassing techniques using obfuscation or other techniques to hide payloads.

[![Packagist](https://img.shields.io/packagist/v/shieldfy/normalizer.svg?label=Packagist&style=flat-square)](https://packagist.org/packages/shieldfy/normalizer)
[![License](https://img.shields.io/packagist/l/shieldfy/normalizer.svg?label=License&style=flat-square)](https://github.com/shieldfy/normalizer/blob/master/LICENSE)
[![Code Climate](https://img.shields.io/codeclimate/github/shieldfy/normalizer.svg)](https://codeclimate.com/github/shieldfy/normalizer)
[![Travis](https://img.shields.io/travis/shieldfy/normalizer.svg)](https://travis-ci.org/shieldfy/normalizer)


## important note

This package is based on the original converters written by Mario Heiderich & Christian Matthies the creators of [PHP IDS](https://github.com/PHPIDS/PHPIDS/) project with help from the generous security & opensource community.

## Installation

Through Composer

```
composer require shieldfy/normaizer
```


## Usage & Examples

```php

$value = "select/*!from*/information_schema.columns/*!where*/column_name%20/*!like*/char(37,%20112,%2097,%20115,%20115,%2037)";

//run all normalizers
$result = (new \Shieldfy\Normalizer\Normalizer($value))->runAll();
echo $result;
// select from information_schema.columns where column_name like char(37, 112, 97, 115, 115, 37) %pass%

//run single normalizer
$result = (new \Shieldfy\Normalizer\Normalizer($value))->run('comments');

```

## Contributing 

Thank you for considering contributing to this project!
Bug reports, feature requests, and pull requests are very welcome.


## Security Vulnerabilities

If you discover a security vulnerability within this project, please send an e-mail to security@shieldfy.com.
