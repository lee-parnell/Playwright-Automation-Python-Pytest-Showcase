# Playwright Automation with Python and Pytest

A comprehensive hands-on automation project demonstrating **Playwright**, **Python**, and **Pytest** for browser automation, UI testing, API testing, Page Object Model design, fixtures, data-driven testing, behavior-driven testing, debugging tools, optimization, and CI-oriented test execution.

**Written by Brian McCarthy**

---

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Goals](#repository-goals)
- [Languages Used](#languages-used)
- [Technologies and Frameworks](#technologies-and-frameworks)
- [Methodologies Used](#methodologies-used)
- [File Structure](#file-structure)
- [Project File Links](#project-file-links)
- [How the Project Works](#how-the-project-works)
- [Core Functions and Patterns](#core-functions-and-patterns)
- [Code Methodology Summary](#code-methodology-summary)
- [Sample Code from This Project](#sample-code-from-this-project)
  - [Basic Playwright Page Fixture Test](#basic-playwright-page-fixture-test)
  - [Page Object Model Login Page](#page-object-model-login-page)
  - [Page Object Model Test Case](#page-object-model-test-case)
  - [API Context Fixture](#api-context-fixture)
  - [API CRUD Tests](#api-crud-tests)
  - [Data-Driven Test with Pytest Parametrize](#data-driven-test-with-pytest-parametrize)
  - [Behavior-Driven Test Steps](#behavior-driven-test-steps)
  - [Behavior Test Environment Hooks](#behavior-test-environment-hooks)
  - [CI-Ready UI Test Example](#ci-ready-ui-test-example)
- [Playwright Pytest Tutorial and Guide](#playwright-pytest-tutorial-and-guide)
- [Common Commands](#common-commands)
- [Recommended Setup](#recommended-setup)
- [Testing Strategy](#testing-strategy)
- [Best Practices and Tips](#best-practices-and-tips)
- [Troubleshooting Guide](#troubleshooting-guide)
- [Suggested Improvements](#suggested-improvements)
- [Author](#author)

---

## Project Overview

This repository is a learning and portfolio project for modern test automation using **Playwright for Python** with **Pytest**. It demonstrates how to automate browser workflows, validate UI behavior, test REST APIs, use fixtures, organize reusable page objects, parameterize test data, handle BDD-style scenarios, and prepare tests for repeatable execution.

The repository is organized into numbered sections, with each section focusing on a major automation topic:

- Playwright setup and browser basics
- Locator strategies
- Browser events
- Authentication workflows
- Automated mail checking
- Pytest fundamentals
- `pytest-playwright` plugin usage
- Playwright debugging tools
- Web-first assertions
- UI Testing Playground examples
- Playwright fixtures
- Page Object Model
- API testing
- Optimization techniques
- GitHub API testing
- CI-oriented testing
- Data-driven testing
- Behavior-driven development

---

## Repository Goals

The project is designed to show practical automation skills in the following areas:

1. Build automated UI tests with Python and Playwright.
2. Use Pytest as the test runner and assertion organizer.
3. Apply reliable locator strategies such as role, placeholder, CSS, and text locators.
4. Use Playwright web-first assertions to reduce flaky waits.
5. Separate test logic from page interaction logic using the Page Object Model.
6. Create reusable Pytest fixtures for setup, teardown, and API contexts.
7. Automate REST API validation using Playwright request contexts.
8. Run the same test logic against multiple data sets using `pytest.mark.parametrize`.
9. Demonstrate behavior-style test steps with `behave` and Playwright.
10. Prepare tests so they can be run locally or inside a CI workflow.

---

## Languages Used

| Language | Purpose |
|---|---|
| Python | Main automation, test cases, fixtures, API tests, Page Object Model classes, BDD step definitions |
| HTML | Sample/static pages or UI content used by some examples |
| Gherkin-style BDD text | Behavior-driven scenario wording used with Behave-style step definitions |
| YAML / CI concepts | CI-oriented automation concepts in the continuous integration section |

---

## Technologies and Frameworks

| Technology | Used For |
|---|---|
| Playwright for Python | Browser automation, UI testing, assertions, API request contexts |
| Pytest | Test discovery, test execution, fixtures, parametrization, reporting |
| pytest-playwright | Built-in Playwright fixtures such as `page`, `browser`, `context`, and browser CLI options |
| Behave | BDD-style step definitions and scenario hooks |
| Python `requests` / Playwright APIRequestContext concepts | REST API validation patterns |
| GitHub API | API testing practice using authenticated API context fixtures |
| UI Testing Playground | Practice site for dynamic IDs, hidden layers, load delays, scrollbars, client-side delays, and other real UI automation challenges |

---

## Methodologies Used

### 1. Functional UI Automation

Tests simulate real user actions such as opening a page, filling fields, clicking buttons, hovering, waiting for UI changes, and validating results.

### 2. Page Object Model

The Page Object Model separates page structure and page actions from test assertions. This makes tests easier to maintain because locators and common actions are centralized in page classes instead of duplicated across test files.

### 3. Fixture-Based Test Design

Pytest fixtures manage browser pages, API clients, setup work, teardown work, and reusable dependencies. This keeps test methods short and improves repeatability.

### 4. Web-First Assertions

Playwright assertions such as `expect(locator).to_have_text()` automatically wait for the expected condition before failing. This reduces the need for manual sleeps and lowers test flakiness.

### 5. API-First Validation

The API testing section validates backend behavior directly through HTTP methods such as GET, POST, PUT, and DELETE. This helps catch service-level problems before UI workflows are tested.

### 6. Data-Driven Testing

Pytest parametrization runs the same test logic against multiple data combinations. This improves coverage without duplicating test functions.

### 7. Behavior-Driven Development

The BDD section uses human-readable step definitions such as `given`, `when`, and `then` to describe behavior in business-friendly language.

### 8. CI-Oriented Testing

The continuous integration section includes tests structured for repeatable command-line execution. These tests can be connected to a GitHub Actions workflow or another CI pipeline.

---

## File Structure

```text
Playwright-Automation-Python-Pytest/
├── S01 - Getting Started/                  # Playwright setup and first scripts
├── S02 - Locators/                         # Locator strategy examples
├── S04 - Events/                           # Browser and page event handling
├── S05 - Authentication/                   # Authentication and login examples
├── S06 - Automated Mail Checker/           # Mail-checking automation examples
├── S07 - pytest/                           # Pytest basics and reporting examples
├── S08 - pytest-playwright Plugin/         # pytest-playwright plugin examples
├── S09 - Playwright Tools/                 # Video, trace, inspector, debugging examples
├── S10 - Web-First Assertions/             # Page, text, attribute, input, checkbox assertions
├── S11 - UI Testing Playground/            # Real-world UI automation practice problems
├── S12 - Playwright Fixtures/              # Fixture and argument examples
├── S13 - Page Object Model/                # Page classes and tests using POM
├── S15 - API Testing/                      # REST API tests using Playwright request context
├── S16 - Optimization/                     # Resource blocking and performance optimization
├── S17 - Tips and Tricks/                  # Useful Playwright/Pytest techniques
├── S18 - GitHub API/                       # Authenticated GitHub API tests
├── S19 - Continuous Integration/           # CI-ready app tests
├── S20 - Data Driven Testing/              # Parametrized Pytest tests
├── S21 - Behaviour Driven Development/     # Behave + Playwright step definitions
└── README.md                               # Project documentation
```

---

## Project File Links

### Main Repository Sections

- [S01 - Getting Started](S01%20-%20Getting%20Started/)
- [S02 - Locators](S02%20-%20Locators/)
- [S04 - Events](S04%20-%20Events/)
- [S05 - Authentication](S05%20-%20Authentication/)
- [S06 - Automated Mail Checker](S06%20-%20Automated%20Mail%20Checker/)
- [S07 - pytest](S07%20-%20pytest/)
- [S08 - pytest-playwright Plugin](S08%20-%20pytest-playwright%20Plugin/)
- [S09 - Playwright Tools](S09%20-%20Playwright%20Tools/)
- [S10 - Web-First Assertions](S10%20-%20Web-First%20Assertions/)
- [S11 - UI Testing Playground](S11%20-%20UI%20Testing%20Playground/)
- [S12 - Playwright Fixtures](S12%20-%20Playwright%20Fixtures/)
- [S13 - Page Object Model](S13%20-%20Page%20Object%20Model/)
- [S15 - API Testing](S15%20-%20API%20Testing/)
- [S16 - Optimization](S16%20-%20Optimization/)
- [S17 - Tips and Tricks](S17%20-%20Tips%20and%20Tricks/)
- [S18 - GitHub API](S18%20-%20GitHub%20API/)
- [S19 - Continuous Integration](S19%20-%20Continuous%20Integration/)
- [S20 - Data Driven Testing](S20%20-%20Data%20Driven%20Testing/)
- [S21 - Behaviour Driven Development](S21%20-%20Behaviour%20Driven%20Development/)

### Key Project Files

- [Login Page Object](S13%20-%20Page%20Object%20Model/87-login_page.py)
- [Login Page Object Tests](S13%20-%20Page%20Object%20Model/88-test_app.py.py)
- [Playwright Documentation Page Object](S13%20-%20Page%20Object%20Model/89-playwright_page.py)
- [Playwright Documentation Tests](S13%20-%20Page%20Object%20Model/90-test_app.py)
- [Basic API Test](S15%20-%20API%20Testing/95-test_api_context.py)
- [API Method Tests](S15%20-%20API%20Testing/97-test_methods.py)
- [API Mock Test](S15%20-%20API%20Testing/98-test_mock.py)
- [GitHub API Fixture](S18%20-%20GitHub%20API/109-conftest.py)
- [CI Example Test](S19%20-%20Continuous%20Integration/114-test_cubeit.py)
- [Data-Driven Root Test](S20%20-%20Data%20Driven%20Testing/118-test_root.py)
- [BDD Environment Hooks](S21%20-%20Behaviour%20Driven%20Development/123-environment.py)
- [BDD Login Steps](S21%20-%20Behaviour%20Driven%20Development/123-login.py)

---

## How the Project Works

At a high level, this repository follows this automation flow:

1. **Pytest discovers test files** named with `test_` or containing test functions named `test_*`.
2. **Playwright opens a browser page** using the `page` fixture from `pytest-playwright` or a manually created browser/page fixture.
3. **The test navigates to an application or API endpoint** using `page.goto()` for UI flows or `api_context.get()`, `post()`, `put()`, and `delete()` for API flows.
4. **Locators identify page elements** using role, placeholder, CSS, text, or other locator strategies.
5. **Actions simulate user behavior** such as `fill()`, `click()`, `hover()`, keyboard input, and page navigation.
6. **Assertions validate outcomes** using Playwright `expect()` or Python `assert` statements.
7. **Fixtures handle reusable setup and teardown** such as API clients, browser instances, and test data.
8. **Page Object Model classes hide locator details** so test files can focus on business behavior.
9. **Parametrized tests repeat the same scenario with multiple data inputs**.
10. **BDD step definitions describe behavior in Given/When/Then style** for readable acceptance scenarios.

---

## Core Functions and Patterns

| Function / Pattern | Purpose |
|---|---|
| `page.goto(url)` | Opens a browser page or endpoint |
| `page.get_by_role()` | Finds elements by accessible role and name |
| `page.get_by_placeholder()` | Finds input fields by placeholder text |
| `page.locator()` | Finds elements using CSS or other selector syntax |
| `locator.fill()` | Enters text into an input field |
| `locator.click()` | Clicks a button, link, or element |
| `expect(locator).to_have_text()` | Waits for text and validates it |
| `expect(page).to_have_url()` | Verifies final page URL after navigation |
| `playwright.request.new_context()` | Creates an API client for REST testing |
| `api_context.get()` | Sends a GET request |
| `api_context.post()` | Sends a POST request |
| `api_context.put()` | Sends a PUT request |
| `api_context.delete()` | Sends a DELETE request |
| `pytest.fixture` | Creates reusable setup/teardown resources |
| `pytest.mark.parametrize` | Runs one test against multiple data rows |
| `before_scenario()` | Behave hook that runs before each scenario |
| `after_scenario()` | Behave hook that runs after each scenario |

---

## Code Methodology Summary

The code is organized as a progressive automation course. Early sections focus on Playwright fundamentals such as navigation and locators. Later sections introduce Pytest, then add more maintainable testing patterns such as fixtures and Page Object Model classes. API testing expands coverage beyond the browser, while data-driven and behavior-driven sections demonstrate scalable ways to increase test coverage and readability.

The strongest methodology examples in the project are:

- **Reusable page classes** in `S13 - Page Object Model`
- **Reusable API request contexts** in `S15 - API Testing` and `S18 - GitHub API`
- **Parametrized test data** in `S20 - Data Driven Testing`
- **BDD Given/When/Then step functions** in `S21 - Behaviour Driven Development`
- **CI-friendly tests** in `S19 - Continuous Integration`

---

## Sample Code from This Project

### Basic Playwright Page Fixture Test

A typical Playwright/Pytest test accepts a `page: Page` fixture, navigates to a URL, interacts with locators, and validates the result.

```python
from playwright.sync_api import Page, expect


def test_cube(page: Page):
    page.goto("http://127.0.0.1:8000/")

    input = page.get_by_placeholder("enter number...")
    input.fill("5")

    page.get_by_role("button", name="Cube").click()

    result = page.locator("css=p#result")
    expect(result).to_contain_text("125")
```

**How it works:**

- `page.goto()` opens the local web application.
- `get_by_placeholder()` targets the input field.
- `fill()` enters the test value.
- `get_by_role()` finds the button by accessible role and visible name.
- `expect()` validates the UI result.

---

### Page Object Model Login Page

The Page Object Model stores page elements and page actions inside a reusable class.

```python
from playwright.sync_api import Page


class LoginPage:

    def __init__(self, page: Page):
        self.page = page
        self.page.goto("http://uitestingplayground.com/sampleapp")

        self.username_input = self.page.get_by_placeholder("User Name")
        self.password_input = self.page.get_by_placeholder("********")
        self.login_btn = self.page.get_by_role("button", name="Log In")
        self.label = self.page.locator("label#loginstatus")

    def login(self, username, password):
        self.username_input.fill(username)
        self.password_input.fill(password)
        self.login_btn.click()
```

**How it works:**

- The constructor receives the Playwright `page` fixture.
- Page locators are assigned to class attributes.
- The `login()` method performs the repeated login workflow.
- Tests can call `login_page.login()` instead of repeating locator code.

---

### Page Object Model Test Case

```python
from models.login_page import LoginPage
from playwright.sync_api import Page, expect


def test_successful_login(page: Page):
    username = "dan"
    password = "pwd"

    login_page = LoginPage(page)
    login_page.login(username, password)

    expect(login_page.label).to_have_text(f"Welcome, {username}!")


def test_failed_login(page: Page):
    username = "dan"
    password = "cnasdjc"

    login_page = LoginPage(page)
    login_page.login(username, password)

    expect(login_page.label).to_have_text("Invalid username/password")
```

**How it works:**

- One test validates a successful login path.
- One test validates a failed login path.
- Both tests reuse the same `LoginPage` object and `login()` method.
- The tests stay readable because the page interaction details are hidden inside the page object.

---

### API Context Fixture

Playwright can test APIs without opening a visible browser page. This project uses `playwright.request.new_context()` for API clients.

```python
from playwright.sync_api import Playwright


def test_users_api(playwright: Playwright):
    api_context = playwright.request.new_context(
        base_url="https://dummyjson.com"
    )

    response = api_context.get("/users/1")
    user_data = response.json()

    assert "firstName" in user_data
    assert "lastName" in user_data
    assert user_data["firstName"] == "Terry"
    assert user_data["lastName"] == "Medhurst"
```

**How it works:**

- `new_context()` creates a reusable API client.
- `base_url` prevents repeating the full URL in every request.
- `get()` sends a GET request.
- `response.json()` converts the response body into a Python dictionary.
- Python `assert` statements validate response fields and values.

---

### API CRUD Tests

```python
import pytest
from playwright.sync_api import Playwright, APIRequestContext


@pytest.fixture
def api_context(playwright: Playwright) -> APIRequestContext:
    api_context = playwright.request.new_context(
        base_url="https://dummyjson.com",
        extra_http_headers={"Content-Type": "application/json"},
    )
    yield api_context
    api_context.dispose()


def test_create_user(api_context: APIRequestContext):
    response = api_context.post(
        "users/add",
        data={"firstName": "Damien", "lastName": "Smith", "age": 27}
    )
    user_data = response.json()

    assert user_data["id"] == 101
    assert user_data["firstName"] == "Damien"


def test_update_user(api_context: APIRequestContext):
    response = api_context.put(
        "users/1",
        data={"lastName": "Smith", "age": 20}
    )
    user_data = response.json()

    assert user_data["lastName"] == "Smith"
    assert user_data["age"] == 20


def test_remove_user(api_context: APIRequestContext):
    response = api_context.delete("users/1")
    user_data = response.json()

    assert user_data["isDeleted"]
```

**How it works:**

- The fixture creates one API context for each test.
- `yield` gives the API context to the test.
- After the test finishes, `dispose()` cleans up the API context.
- Separate tests validate POST, PUT, and DELETE behavior.

---

### Data-Driven Test with Pytest Parametrize

```python
import pytest
from root import root


@pytest.mark.parametrize(
    ("num", "num_root"),
    (
        (100, 10),
        (36, 6),
        (25, 5),
        (16, 4),
        (9, 3),
        (4, 2),
    )
)
def test_root(num, num_root):
    assert root(num) == num_root
```

**How it works:**

- `pytest.mark.parametrize` defines multiple input/output pairs.
- Pytest runs `test_root()` once for every tuple.
- This avoids writing six separate test functions.
- When one data row fails, Pytest reports the failing parameter set.

---

### Behavior-Driven Test Steps

The BDD section uses Behave-style step decorators.

```python
from behave import *
from playwright.sync_api import expect


@given("username and pwd password")
def fill_username_and_password(context):
    context.page.goto("http://uitestingplayground.com/sampleapp")
    context.page.get_by_placeholder("User Name").fill("name")
    context.page.get_by_placeholder("********").fill("pwd")


@when("Log In button clicked")
def click_login(context):
    context.page.get_by_role("button", name="Log In").click()


@then("show welcome message")
def expect_welcome_message(context):
    message = context.page.locator("css=label#loginstatus")
    expect(message).to_have_text("Welcome, name!")
```

**How it works:**

- `@given` prepares the test state.
- `@when` performs the action under test.
- `@then` validates the expected behavior.
- `context.page` is created in the environment hooks before the scenario runs.

---

### Behavior Test Environment Hooks

```python
from playwright.sync_api import sync_playwright


def before_scenario(context, _):
    context.playwright = sync_playwright().start()
    context.browser = context.playwright.chromium.launch(
        headless=False,
        slow_mo=500
    )
    context.page = context.browser.new_page()


def after_scenario(context, _):
    context.browser.close()
    context.playwright.stop()
```

**How it works:**

- `before_scenario()` starts Playwright before each BDD scenario.
- Chromium launches with `headless=False` so the test can be watched visually.
- `slow_mo=500` slows actions down for demonstration and debugging.
- `after_scenario()` closes the browser and stops Playwright to avoid resource leaks.

---

### CI-Ready UI Test Example

```python
from playwright.sync_api import Page, expect


BASE_URL = "http://127.0.0.1:8000/"


def test_empty_input(page: Page):
    page.goto(BASE_URL)

    input = page.get_by_placeholder("enter number...")
    input.fill("")

    page.get_by_role("button", name="Cube").click()

    result = page.locator("css=p#result")
    expect(result).to_have_text("Enter something!")
```

**How it works:**

- `BASE_URL` centralizes the application URL.
- The test validates an error/empty-input path.
- This kind of deterministic UI test is a good candidate for CI execution.

---

## Playwright Pytest Tutorial and Guide

### 1. Create a Python Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Activate it on macOS/Linux:

```bash
source .venv/bin/activate
```

### 2. Install Playwright and Pytest

```bash
pip install playwright pytest pytest-playwright
```

### 3. Install Browsers

```bash
playwright install
```

### 4. Create a Basic Test File

Create a file named `test_example.py`:

```python
from playwright.sync_api import Page, expect


def test_homepage_title(page: Page):
    page.goto("https://playwright.dev/python")
    expect(page).to_have_title("Fast and reliable end-to-end testing for modern web apps | Playwright Python")
```

### 5. Run Tests

```bash
pytest
```

### 6. Run Tests in Headed Mode

```bash
pytest --headed
```

### 7. Run Tests in a Specific Browser

```bash
pytest --browser chromium
pytest --browser firefox
pytest --browser webkit
```

### 8. Run Tests Slowly for Debugging

```bash
pytest --headed --slowmo 500
```

### 9. Generate a Trace

```bash
pytest --tracing on
```

### 10. Open a Trace

```bash
playwright show-trace test-results/path-to-trace.zip
```

---

## Common Commands

| Command | Purpose |
|---|---|
| `pytest` | Run all tests |
| `pytest path/to/test_file.py` | Run one test file |
| `pytest -k login` | Run tests matching keyword `login` |
| `pytest -v` | Run tests with verbose output |
| `pytest -s` | Show print statements in output |
| `pytest --headed` | Run browser visibly |
| `pytest --browser chromium` | Run tests in Chromium |
| `pytest --browser firefox` | Run tests in Firefox |
| `pytest --browser webkit` | Run tests in WebKit |
| `pytest --tracing on` | Capture Playwright traces |
| `pytest --video on` | Capture videos |
| `pytest --screenshot only-on-failure` | Save screenshots when tests fail |

---

## Recommended Setup

A clean project setup for this repository would include:

```text
project-root/
├── tests/
│   ├── test_login.py
│   ├── test_api_users.py
│   └── test_checkout.py
├── pages/
│   ├── login_page.py
│   └── home_page.py
├── fixtures/
│   └── api_fixtures.py
├── test_data/
│   └── users.json
├── conftest.py
├── pytest.ini
├── requirements.txt
└── README.md
```

Example `requirements.txt`:

```text
playwright
pytest
pytest-playwright
behave
```

Example `pytest.ini`:

```ini
[pytest]
testpaths = tests
python_files = test_*.py
python_functions = test_*
addopts = -v --screenshot only-on-failure --tracing retain-on-failure
```

---

## Testing Strategy

### Smoke Tests

Run a small set of critical tests to confirm the application is basically working.

Examples:

- Login page loads
- User can log in
- Main navigation works
- Critical API endpoint responds

### Regression Tests

Run broader coverage after changes to confirm existing functionality still works.

Examples:

- UI playground tests
- API CRUD tests
- Authentication tests
- Page Object Model tests
- Data-driven tests

### API Tests

Validate service responses directly before relying on UI tests.

Examples:

- GET user
- Search user
- Create user
- Update user
- Delete user

### Negative Tests

Validate bad input and error behavior.

Examples:

- Failed login
- Empty input
- Invalid credentials
- Invalid search criteria

### Cross-Browser Tests

Use Playwright browser support to test Chromium, Firefox, and WebKit.

---

## Best Practices and Tips

### Prefer User-Facing Locators

Best:

```python
page.get_by_role("button", name="Log In")
page.get_by_placeholder("User Name")
page.get_by_text("Welcome")
```

Use CSS when role/text locators are not stable:

```python
page.locator("label#loginstatus")
```

### Avoid Hard Waits

Avoid:

```python
page.wait_for_timeout(5000)
```

Prefer:

```python
expect(page.locator("#status")).to_have_text("Complete")
```

### Keep Tests Short

A good test should usually follow this pattern:

```python
# Arrange
page.goto(BASE_URL)

# Act
page.get_by_role("button", name="Submit").click()

# Assert
expect(page.locator("#message")).to_have_text("Saved")
```

### Use Page Objects for Repeated Workflows

If multiple tests repeat the same login or navigation workflow, move it into a page object method.

```python
login_page.login(username, password)
```

### Use Fixtures for Setup and Cleanup

Use fixtures for browser setup, API clients, authentication state, and test data preparation.

```python
@pytest.fixture
def api_context(playwright):
    context = playwright.request.new_context(base_url="https://dummyjson.com")
    yield context
    context.dispose()
```

### Use Parametrization for Coverage

```python
@pytest.mark.parametrize("username,password", [
    ("valid_user", "valid_pass"),
    ("locked_user", "valid_pass"),
    ("invalid_user", "bad_pass"),
])
def test_login_cases(page, username, password):
    pass
```

### Store Secrets Outside Source Code

For GitHub API tests, do not commit personal access tokens. Use environment variables or GitHub Actions secrets.

Recommended pattern:

```python
import os

GITHUB_TOKEN = os.environ["GITHUB_TOKEN"]
```

### Capture Debugging Artifacts

For failures, use screenshots, video, and traces:

```bash
pytest --screenshot only-on-failure --video retain-on-failure --tracing retain-on-failure
```

### Keep API Tests Independent

API tests should create their own data and clean it up when possible. This keeps tests repeatable.

---

## Troubleshooting Guide

### Browser Not Installed

Error example:

```text
Executable doesn't exist...
```

Fix:

```bash
playwright install
```

### Test Cannot Find Element

Possible causes:

- The locator is incorrect.
- The element is inside an iframe.
- The element is not visible yet.
- The page did not navigate successfully.

Fixes:

```python
expect(page.get_by_role("button", name="Log In")).to_be_visible()
```

Use Playwright Inspector:

```bash
PWDEBUG=1 pytest
```

On Windows PowerShell:

```powershell
$env:PWDEBUG=1
pytest
```

### Flaky Timing Failures

Avoid fixed sleeps. Use web-first assertions:

```python
expect(page.locator("#result")).to_contain_text("Done")
```

### API Test Fails with Authentication Error

Check:

- Token exists
- Token has required permissions
- Token is passed in the expected header format
- Token is stored securely outside the repo

### Localhost Test Fails

If a test uses `http://127.0.0.1:8000/`, make sure the application server is running before executing Pytest.

---

## Suggested Improvements

Future enhancements that would make this project even stronger:

1. Add a `requirements.txt` file with pinned dependency versions.
2. Add a `pytest.ini` file with default Pytest settings.
3. Add a `.github/workflows/playwright.yml` workflow to run tests automatically.
4. Add screenshots and trace artifacts to CI results.
5. Move page object classes into a consistent `pages/` or `models/` package.
6. Move test data into a `test_data/` directory.
7. Add Allure or HTML reports for portfolio-friendly reporting.
8. Add environment variable handling for API tokens.
9. Add README badges for Python, Pytest, Playwright, and CI status.
10. Add more negative tests and boundary-value tests.

---

## Author

**Written by Brian McCarthy**

This repository demonstrates practical Playwright automation engineering skills using Python, Pytest, Page Object Model design, REST API testing, data-driven testing, behavior-driven testing, and CI-ready automation patterns.
