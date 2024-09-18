# Final Project, PFS

We will start by downloading and setting up PFS so that you have a working final project to take away.

We will look at its structure and customisation and then move on to building it from scratch if necessary. Some of this may be done later in the workshop but we will see what we are able to do.

## Repo

Clone from [https://github.com/Python-Test-Engineer/PyTest-Full-Stack](https://github.com/Python-Test-Engineer/PyTest-Full-Stack).
## YouTube videos

Videos are available here: [YouTube](https://www.youtube.com/playlist?list=PLsszRSbzjyvlrB6V5dacW6G8YrD_iW7oy) 

These show you how to use and customise PFS.

## Installation

- `git clone https://github.com/Python-Test-Engineer/PyTest-Full-Stack`
- Create virtual enviroment `python -m venv venv`
- Activate your virtual enviromnent: Windows `.\venv\Scripts\activte` or Mac `source venv/bin/activate`.
- install requirements `pip install -r requirements.txt`.
- for Playwright browsers run `playwright install`.
- There are around 200 templated tests.

## Test run

Let's run `python -m pytest -vs --headed`. The `--headed` tells Playwright to open up browsers in our E2E tests for demon puposes.

We can see a CSV of results in the `results` folder. The console ouput is colorised with the Rich library. Rename the `conftest.py` in the root of the folder to say `Xconftest.py` and you will see no CSV produced and no colorisation.

## Customisation

YouTube playlist: [here](https://www.youtube.com/playlist?list=PLsszRSbzjyvlrB6V5dacW6G8YrD_iW7oy)

This covers:

- pytest.ini settings for logging.
- how to read values from the config.ini files in the config folder.
- customise the report header in the console output.
- customising the test status words, colours and icons in the console output.
- adding a report section at end of console output.
- and more...

The free online course 'PyTest Hooks and Plugins' that you have a free coupon for goes into much more detail about how to use hooks in PyTest.

<br>