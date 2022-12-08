
# Experimental End-to-End Tests for the D-Installer

This is a testing repository with integrations tests for the
[D-Installer](https://github.com/yast/d-installer) project.


## Playwright

These tests use the [Playwright](https://playwright.dev/) testing framework.

## Installation

Checkout this repository and run this command in it:

```shell
npm install
```

This will install the NPM packages into the `node_modules` subdirectory
and download the browsers into the `~/.cache/ms-playwright` directory.

*Note: The downloaded browsers need almost 1GB, make sure you have enough
space in your $HOME directory.*

## Editing the Tests

- `playwright.config.ts` - Playwright configuration, see [documentation](
  https://playwright.dev/docs/test-configuration) for more details
- `global-setup.ts` - a helper for logging-in
- `tests/\*.spec.ts` - individual test files

## Running the Tests

### Setting the Target

This project defines the default URL as `https://localhost:9090` which
expects the D-Installer is running locally. If you want to run the test against
an instance which is running elsewhere use set the `BASE_URL` environment
variable.

```
BASE_URL=https://192.168.1.12:9090
```

### Examples

Or you can run the tests from command line. To run all tests using the embedded
Electron browser:

```
npx playwright test
```

To run just a specific test:

```
npx playwright test tests/root_password.spec.ts
```

The tests are by default run in headless mode, if want to see the actions
in a browser use the `--headed` option.

If you want to manually run a test step by step use the `--debug` option.

## Playwright Documentation

- https://playwright.dev/docs/intro
