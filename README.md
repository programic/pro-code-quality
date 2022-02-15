# Programic Quality Control composer package

Composer package that includes all the packages required by the Definition of Done for Code Quality.

* [PHPMD](https://phpmd.org/): PHP Mess Detector
* [PHPStan](https://phpstan.org/): PHP Static Analysis
* [PHPMND](https://github.com/povils/phpmnd): PHP Magic Number Detection
* [PHPCPD](https://github.com/sebastianbergmann/phpcpd): PHP Copy & Paste Detection
* [ECS](https://github.com/symplify/easy-coding-standard): Easy Coding Standards
    * includes `PHP_CodeSniffer` and `PHP-CS-Fixer`
    * Additional rules:
        * symplify/coding-standard
        * slevomat/coding-standard

## How to add to your project

1. Add remote repository:
    ```bash
    $ composer config --append repositories.pro-qa vcs git@bitbucket.org:programic/pro-quality-control.git
    ```
2. Make sure the `minimum-stability` is set to `dev`:
    ```bash
    $ composer config minimum-stability dev
    ```
3. Require the package:
    ```bash
    $ composer require --dev programic/quality-control
    ```
4. Copy the example config files for each tool to your project:
    * [ecs.example.php](configs/examples/ecs.example.php) -> `/ecs.php`
    * [phpmd.example.xml](configs/examples/phpmd.example.xml) -> `/phpmd.xml`
    * [phpstan.example.neon](configs/examples/phpstan.example.neon) -> `/phpstan.neon`
    
    Adjust the rules as needed.

5. Add the scripts to your `composer.json` (see example in [composer.example.json](configs/examples/composer.example.json)).

## How to run the code quality checks

### Run all the checks

```bash
$ composer check
```

### Run a specific check:

```bash
$ composer check:ecs
$ composer check:phpmd
$ composer check:phpmnd
$ composer check:phpcpd
$ composer check:phpstan
```
