#  Laravel & PHP Scratchpad

_Notice: the original [README.md got moved here](README-laravel.md)_

This is my personal scratchpad for testing, learning and documenting on PHP issues. This is how I started it:

```sh
$ open https://laravel.com/docs/8.x#getting-started-on-macos
$ curl -s "https://laravel.build/scratchpad-laravel" | bash
$ cd scratchpad-laravel
$ ./vendor/bin/sail up
$ open http://localhost:80/
```

Over time, I will add here whatever crosses my day job and seems worth being kept for remembering.

## First Things first: Setup Unit Testing for TDD

Test Driven Development is the easiest way to improve my developer convenience. Before touching anything else, I add automated unit testing to be run whenever something changes. `phpunit` is already part of the initial Laravel example project, so only thing missing though is a package to run tests automatically:

```sh
$ composer require --dev "spatie/phpunit-watcher"
$ composer install
$ ./vendor/bin/phpunit-watcher watch

PHPUnit Watcher
===============

 PHPUnit Watcher 1.12.1 by Spatie and contributors.

 No config file detected. Using default options.

 Tests will be rerun when *.php files are modified in
 * /Users/crux/Documents/scratchpad-laravel/app
 * /Users/crux/Documents/scratchpad-laravel/tests

PHPUnit 9.5.9 by Sebastian Bergmann and contributors.

..                                                                  2 / 2 (100%)

Time: 00:00.361, Memory: 22.00 MB

OK (2 tests, 2 assertions)
Starting PHPUnit

Press a to run all tests.
Press t to filter by test name.
Press p to filter by file name.
Press g to filter by group name.
Press s to filter by test suite name.
Press r to run tests with a random seed.
Press q to quit the watcher.
Press Enter to trigger a test run.
```

The watch command does not return, it runs forever. So I put it in an extra shell session have running somewhere on screen whenever I am working on the project.
