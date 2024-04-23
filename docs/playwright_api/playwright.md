# Playwright Testing

## About

Playwright was created specifically to accommodate the needs of end-to-end testing. Playwright supports all modern rendering engines including Chromium, WebKit, and Firefox. Test on Windows, Linux, and macOS, locally or on CI, headless or headed with native mobile emulation.

Playwright recommends using the official Playwright Pytest plugin to write end-to-end tests. It provides context isolation, running it on multiple browser configurations out of the box. Alternatively you can use the library to manually write the testing infrastructure with your preferred test-runner. The Pytest plugin utilizes the sync version of Playwright, there is also an async version accessible via the library.

[Playwright - Python](https://playwright.dev/python/){:target="_blank"}

## Install 

- move to `TEST_SUITE_02_API_PLAYWRIGHT` 
- create virtual environment as you wish
- run `pip install requirements_02.txt`
- run `playwright install` to load in browsers. IMPORTANT.

## Run Tests

- run `python -m pytest -vs`


