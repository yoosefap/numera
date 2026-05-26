# AGENTS.md

## Cursor Cloud specific instructions

This is a **PHP library** (not a web application). There are no servers, databases, or services to run.

### Key commands

| Action | Command |
|--------|---------|
| Install dependencies | `composer install --prefer-dist --no-progress` |
| Run tests | `vendor/bin/phpunit` |
| Run tests with coverage | `vendor/bin/phpunit --coverage-clover=coverage.xml` (requires Xdebug) |

### Notes

- PHP 8.0+ is required (`composer.json` specifies `"php": "^8.0"`). CI tests against PHP 8.0-8.3.
- The only dev dependency is PHPUnit 10.5, installed via Composer.
- There is no lint tool configured in this project; code quality is validated through the PHPUnit test suite (1044 tests).
- 4 tests are skipped by design (locale coverage tests that expect specific locale data).
- No `.env`, Docker, or external services are needed.
- To exercise the library interactively, use `php -r 'require "vendor/autoload.php"; use Pino\Numera; echo Numera::init("en")->n2w(42);'`.
