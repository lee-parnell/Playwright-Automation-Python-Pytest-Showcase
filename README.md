# Playwright Automation with Python and Pytest Showcase

**Written by Brian McCarthy**

A complete hands-on Playwright automation guide using **Python**, **Pytest**, `pytest-playwright`, Page Object Model design, fixtures, web-first assertions, API testing, network interception, CI execution, data-driven testing, and behavior-driven development.

This README is organized as a numbered tutorial. Each module explains what the user needs to know, why the concept matters, a practical code sample, and the expected result from the sample.

---

## Table of Contents

1. [Project Overview - What This Repository Demonstrates](#1-project-overview---what-this-repository-demonstrates)
2. [Repository Goals - Skills Demonstrated](#2-repository-goals---skills-demonstrated)
3. [Languages, Tools, and Frameworks](#3-languages-tools-and-frameworks)
4. [Project File Links - Main Repository Sections](#4-project-file-links---main-repository-sections)
5. [How the Project Works - Automation Flow](#5-how-the-project-works---automation-flow)
6. [Core Playwright and Pytest Commands](#6-core-playwright-and-pytest-commands)
7. [Module 1 - Getting Started](#7-module-1---getting-started)
8. [Module 2 - Locators](#8-module-2---locators)
9. [Module 3 - Actions](#9-module-3---actions)
10. [Module 4 - Events](#10-module-4---events)
11. [Module 5 - Authentication](#11-module-5---authentication)
12. [Module 6 - Automated Mail Checker](#12-module-6---automated-mail-checker)
13. [Module 7 - Pytest](#13-module-7---pytest)
14. [Module 8 - pytest-playwright Plugin](#14-module-8---pytest-playwright-plugin)
15. [Module 9 - Playwright Tools](#15-module-9---playwright-tools)
16. [Module 10 - Web-First Assertions](#16-module-10---web-first-assertions)
17. [Module 11 - UI Testing Playground](#17-module-11---ui-testing-playground)
18. [Module 12 - Playwright Fixtures](#18-module-12---playwright-fixtures)
19. [Module 13 - Page Object Model](#19-module-13---page-object-model)
20. [Module 14 - Network Events](#20-module-14---network-events)
21. [Module 15 - API Testing](#21-module-15---api-testing)
22. [Module 16 - Optimization](#22-module-16---optimization)
23. [Module 17 - Tips and Tricks](#23-module-17---tips-and-tricks)
24. [Module 18 - GitHub API](#24-module-18---github-api)
25. [Module 19 - Continuous Integration](#25-module-19---continuous-integration)
26. [Module 20 - Data-Driven Testing](#26-module-20---data-driven-testing)
27. [Module 21 - Behavior-Driven Development](#27-module-21---behavior-driven-development)
28. [Best Practices and Troubleshooting](#28-best-practices-and-troubleshooting)
29. [Author](#29-author)

---

## 1. Project Overview - What This Repository Demonstrates

This repository demonstrates end-to-end browser automation and test engineering using Playwright with Python. It begins with simple browser launch scripts and grows into a full automation showcase covering locators, user actions, events, authentication, Pytest fixtures, Page Object Model, API testing, network mocking, optimization, CI, data-driven testing, and BDD.

The project is valuable as a portfolio because it shows several real automation skills together:

- Browser automation with Playwright.
- Test execution and organization with Pytest.
- Maintainable test design with fixtures and Page Object Model.
- UI validation with web-first assertions.
- API validation with Playwright request contexts.
- Test data expansion with parametrized tests.
- BDD collaboration with feature files and step definitions.
- CI-ready execution patterns.

---

## 2. Repository Goals - Skills Demonstrated

1. Build reliable Playwright browser tests in Python.
2. Use locators based on role, text, label, placeholder, CSS, and XPath.
3. Simulate real user actions such as typing, clicking, selecting, hovering, uploading, and using the keyboard.
4. Handle asynchronous browser behavior through auto-waiting, custom waits, dialogs, downloads, and event listeners.
5. Save and reuse authentication state.
6. Organize tests with Pytest fixtures and plugin-provided Playwright fixtures.
7. Use Page Object Model to reduce locator duplication.
8. Validate API behavior using request contexts.
9. Intercept and modify network traffic.
10. Optimize test execution with selective resource blocking and parallel runs.
11. Debug tests with traces, screenshots, videos, headed mode, and Python debugging.
12. Connect automation to CI and GitHub Actions.
13. Use data-driven and BDD workflows for broader test coverage.

---

## 3. Languages, Tools, and Frameworks

| Tool / Language | Purpose |
|---|---|
| Python | Main automation language for UI, API, fixtures, and BDD step code |
| Playwright for Python | Browser automation, locators, actions, events, web assertions, API contexts, tracing, and network mocking |
| Pytest | Test discovery, test execution, fixtures, parametrization, and assertions |
| pytest-playwright | Pytest plugin that provides `page`, `browser`, `context`, browser CLI options, and Playwright fixtures |
| Behave | Behavior-driven development with Gherkin feature files and step definitions |
| GitHub API | Authenticated API automation practice |
| GitHub Actions | CI workflow execution for automated tests |
| HTML / Test Pages | Local or remote pages used to practice UI automation patterns |

---

## 4. Project File Links - Main Repository Sections

| Section | Link | Main Focus |
|---:|---|---|
| 1 | [S01 - Getting Started](S01%20-%20Getting%20Started/) | Installation, browser launch, simple navigation, link clicking, script structure |
| 2 | [S02 - Locators](S02%20-%20Locators/) | Role locators, text locators, input fields, CSS, XPath, and advanced selectors |
| 3 | S03 - Actions | Mouse, keyboard, form controls, dropdowns, uploads, shortcuts |
| 4 | [S04 - Events](S04%20-%20Events/) | Auto-waiting, custom waits, event listeners, dialogs, downloads, async Playwright |
| 5 | [S05 - Authentication](S05%20-%20Authentication/) | Sign-in flows, saving storage state, reusing authenticated sessions |
| 6 | [S06 - Automated Mail Checker](S06%20-%20Automated%20Mail%20Checker/) | Locate emails, extract email data, combine locators, run terminal checks |
| 7 | [S07 - pytest](S07%20-%20pytest/) | Test functions, test state, fixtures, scope, type hints |
| 8 | [S08 - pytest-playwright Plugin](S08%20-%20pytest-playwright%20Plugin/) | Plugin setup, Playwright fixtures, Pytest config, hooks |
| 9 | [S09 - Playwright Tools](S09%20-%20Playwright%20Tools/) | Inspector, code generation, screenshots, traces, videos, debugging support |
| 10 | [S10 - Web-First Assertions](S10%20-%20Web-First%20Assertions/) | Page, element, text, attribute, input, checkbox, and option assertions |
| 11 | [S11 - UI Testing Playground](S11%20-%20UI%20Testing%20Playground/) | Dynamic IDs, hidden layers, Ajax, scrollbars, dynamic tables, login, hover |
| 12 | [S12 - Playwright Fixtures](S12%20-%20Playwright%20Fixtures/) | Function scope, session scope, browser selection, launch/context args |
| 13 | [S13 - Page Object Model](S13%20-%20Page%20Object%20Model/) | Page classes, reusable locators, maintainable test design |
| 14 | S14 - Network Events | Request inspection, request handling, response mocking |
| 15 | [S15 - API Testing](S15%20-%20API%20Testing/) | API calls, request context, query strings, CRUD, mock API |
| 16 | [S16 - Optimization](S16%20-%20Optimization/) | Intercept requests, disable JavaScript, run tests in parallel |
| 17 | [S17 - Tips and Tricks](S17%20-%20Tips%20and%20Tricks/) | CLI args, Python debugger, device emulation, JS evaluation, reports |
| 18 | [S18 - GitHub API](S18%20-%20GitHub%20API/) | GitHub token, authorized API context, API tests |
| 19 | [S19 - Continuous Integration](S19%20-%20Continuous%20Integration/) | Repository setup, test execution in GitHub Actions |
| 20 | [S20 - Data Driven Testing](S20%20-%20Data%20Driven%20Testing/) | Pytest parametrization and multi-data coverage |
| 21 | [S21 - Behaviour Driven Development](S21%20-%20Behaviour%20Driven%20Development/) | Feature files, steps, hooks, Behave execution |

---

## 5. How the Project Works - Automation Flow

1. Pytest discovers test files and test functions.
2. Playwright creates a browser, browser context, and page.
3. The test navigates to a page with `page.goto()` or creates an API client with `playwright.request.new_context()`.
4. Locators identify elements by role, text, label, placeholder, CSS, XPath, or other selector strategies.
5. Actions simulate user behavior.
6. Assertions validate the expected UI, page state, API response, or data result.
7. Fixtures provide reusable setup and teardown.
8. Page Object Model classes wrap locators and page actions.
9. Parametrized tests repeat the same logic across multiple data sets.
10. BDD feature files describe scenarios in human-readable language.
11. CI workflows run tests automatically after code changes.

---

## 6. Core Playwright and Pytest Commands

```bash
# Install dependencies
pip install pytest playwright pytest-playwright behave

# Install browser binaries
playwright install

# Run all tests
pytest

# Run with headed browser
pytest --headed

# Run a specific test file
pytest path/to/test_file.py

# Run tests with a specific browser
pytest --browser chromium

# Run tests in parallel when pytest-xdist is installed
pytest -n auto

# Run Behave BDD tests
behave
```

**Expected result:** Pytest discovers matching tests, launches Playwright resources when needed, executes assertions, and reports passed/failed test results in the terminal.

---

## 7. Module 1 - Getting Started

**What this module covers:** Playwright installation, documentation usage, launching a browser, opening a page, clicking a link, and understanding script structure.

**What the user needs to know:** Playwright automation usually starts with a browser, a context, and a page. The browser is the engine, the context is an isolated session, and the page is the tab where actions happen.

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    page = browser.new_page()
    page.goto("https://playwright.dev/python/")
    print(page.title())
    browser.close()
```

**Expected result:** Chromium opens, navigates to the Playwright Python documentation, prints the page title, and closes the browser.

```text
Fast and reliable end-to-end testing for modern web apps | Playwright Python
```

**Key takeaways:**

- `sync_playwright()` starts the Playwright driver.
- `p.chromium.launch()` opens Chromium.
- `browser.new_page()` creates a tab.
- `page.goto()` navigates to a URL.
- `browser.close()` releases resources.

---

## 8. Module 2 - Locators

**What this module covers:** Role locators, input locators, text locators, alt text, title, CSS selectors, hierarchy, pseudo-classes, XPath, XPath functions, and other locator strategies.

**What the user needs to know:** Locators are the foundation of reliable Playwright tests. Prefer user-facing locators such as role, label, placeholder, and text before falling back to CSS or XPath.

```python
from playwright.sync_api import Page, expect

def test_search_docs(page: Page):
    page.goto("https://playwright.dev/python/")
    page.get_by_role("link", name="Docs").click()
    expect(page).to_have_url(lambda url: "docs" in url)
```

**Expected result:** The test opens the Playwright Python site, clicks the Docs link, and passes when the final URL contains `docs`.

**Locator strategy guide:**

| Locator | Best Use |
|---|---|
| `get_by_role()` | Buttons, links, headings, checkboxes, and accessible UI elements |
| `get_by_text()` | Visible text content |
| `get_by_placeholder()` | Form inputs with placeholder text |
| `get_by_label()` | Inputs connected to labels |
| `locator("css")` | Precise CSS selector targeting |
| `locator("xpath=...")` | Complex document traversal when other locators are not practical |

---

## 9. Module 3 - Actions

**What this module covers:** Mouse actions, text input, radio buttons, checkboxes, switches, select options, dropdown menus, file uploads, and keyboard shortcuts.

**What the user needs to know:** Playwright actions automatically wait for elements to become actionable. An element must generally be visible, enabled, stable, and able to receive input.

```python
from playwright.sync_api import Page, expect

def test_form_actions(page: Page):
    page.goto("https://www.w3schools.com/html/html_forms.asp")
    page.get_by_label("First name:").fill("Brian")
    page.get_by_label("Last name:").fill("McCarthy")
    expect(page.get_by_label("First name:")).to_have_value("Brian")
```

**Expected result:** The first-name and last-name inputs are filled, and the assertion confirms the first-name field contains `Brian`.

**Common action methods:**

```python
locator.click()
locator.fill("text")
locator.check()
locator.uncheck()
locator.select_option("value")
locator.hover()
locator.press("Enter")
locator.set_input_files("file.txt")
```

---

## 10. Module 4 - Events

**What this module covers:** Auto-waiting, navigation waiting, custom waits, event listeners, dialogs, downloads, synchronous vs. asynchronous Playwright, and async Playwright usage.

**What the user needs to know:** Modern web apps are asynchronous. Playwright reduces flaky tests through auto-waiting, but explicit event handling is still necessary for dialogs, downloads, popups, and network-dependent flows.

```python
from playwright.sync_api import Page, expect

def test_dialog_event(page: Page):
    page.goto("https://the-internet.herokuapp.com/javascript_alerts")

    page.on("dialog", lambda dialog: dialog.accept())
    page.get_by_text("Click for JS Alert").click()

    expect(page.locator("#result")).to_have_text("You successfully clicked an alert")
```

**Expected result:** The alert appears, Playwright accepts it automatically, and the page displays the success message.

**Important event patterns:**

```python
page.on("dialog", handler)
with page.expect_download() as download_info:
    page.get_by_text("Download").click()
with page.expect_popup() as popup_info:
    page.get_by_text("Open").click()
```

---

## 11. Module 5 - Authentication

**What this module covers:** Google sign-in concepts, saving authentication state, reusing authentication state, and handling login limitations.

**What the user needs to know:** Authentication flows can be expensive and fragile. A common strategy is to sign in once, save browser storage state to a JSON file, and reuse that state in later tests.

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    context = browser.new_context()
    page = context.new_page()
    page.goto("https://example.com/login")
    page.get_by_label("Email").fill("user@example.com")
    page.get_by_label("Password").fill("password")
    page.get_by_role("button", name="Sign in").click()
    context.storage_state(path="auth_state.json")
    browser.close()
```

**Expected result:** After login succeeds, Playwright saves cookies and local/session storage into `auth_state.json`.

**Reuse example:**

```python
def test_authenticated_page(browser):
    context = browser.new_context(storage_state="auth_state.json")
    page = context.new_page()
    page.goto("https://example.com/account")
    assert "account" in page.url
```

**Expected result:** The test starts already authenticated and skips the login form.

---

## 12. Module 6 - Automated Mail Checker

**What this module covers:** Project setup, locating new emails, locating email data, combining locators, and checking email data from the terminal.

**What the user needs to know:** Email automation usually requires stable locators for message rows, sender values, subjects, dates, and body content. Tests should avoid relying only on message order when the mailbox can change.

```python
from playwright.sync_api import Page, expect

def test_find_email_subject(page: Page):
    page.goto("https://example-mail-app.test/inbox")
    email_row = page.locator(".email-row").filter(has_text="Welcome")
    expect(email_row).to_be_visible()
    expect(email_row.locator(".subject")).to_contain_text("Welcome")
```

**Expected result:** The test finds an email row containing `Welcome` and confirms that its subject contains `Welcome`.

**Terminal-oriented pattern:**

```python
def get_latest_email_subject(page: Page) -> str:
    page.goto("https://example-mail-app.test/inbox")
    return page.locator(".email-row .subject").first.inner_text()
```

**Expected result:** The helper returns a subject string that can be printed or used in another automation step.

---

## 13. Module 7 - Pytest

**What this module covers:** Writing tests, running tests, type hinting, test state, fixtures, using fixtures, and fixture scope.

**What the user needs to know:** Pytest discovers functions that begin with `test_`. Fixtures provide reusable setup. Assertions can be plain Python `assert` statements or Playwright `expect()` assertions.

```python
import pytest

@pytest.fixture
def user_data():
    return {"username": "brian", "role": "qa"}

def test_user_role(user_data):
    assert user_data["role"] == "qa"
```

**Expected result:** Pytest injects the `user_data` fixture into the test and the assertion passes.

```text
1 passed
```

**Fixture scope examples:**

```python
@pytest.fixture(scope="function")
def fresh_data():
    return []

@pytest.fixture(scope="session")
def config():
    return {"base_url": "https://example.com"}
```

---

## 14. Module 8 - pytest-playwright Plugin

**What this module covers:** Installing the plugin, writing Playwright tests with plugin fixtures, running tests, Pytest config, and hooks.

**What the user needs to know:** `pytest-playwright` provides ready-to-use fixtures such as `page`, `browser`, `context`, and `browser_name`. This removes boilerplate browser setup code.

```python
from playwright.sync_api import Page, expect

def test_homepage_title(page: Page):
    page.goto("https://playwright.dev/python/")
    expect(page).to_have_title(lambda title: "Playwright" in title)
```

**Expected result:** The plugin creates the page fixture, opens the website, and validates the title.

```text
1 passed
```

**Useful config example:**

```ini
# pytest.ini
[pytest]
addopts = --browser chromium --headed
```

**Expected result:** Pytest uses Chromium and headed mode by default when running tests.

---

## 15. Module 9 - Playwright Tools

**What this module covers:** Playwright inspector, codegen, screenshots, tracing, video recording, debugging, and productivity tooling.

**What the user needs to know:** Playwright tools help create, debug, and investigate tests. Tracing is especially useful because it records actions, DOM snapshots, console logs, network calls, and screenshots.

```python
def test_screenshot(page):
    page.goto("https://playwright.dev/python/")
    page.screenshot(path="homepage.png", full_page=True)
```

**Expected result:** A screenshot file named `homepage.png` is created.

```bash
pytest --headed --slowmo 500
pytest --tracing on
playwright show-trace trace.zip
playwright codegen https://playwright.dev/python/
```

**Expected result:**

- `--headed` shows the browser.
- `--slowmo` slows actions for debugging.
- `--tracing on` records trace files.
- `codegen` opens an interactive recorder that suggests locator code.

---

## 16. Module 10 - Web-First Assertions

**What this module covers:** Page assertions, element state assertions, text assertions, attribute assertions, input assertions, checkbox assertions, and option-menu assertions.

**What the user needs to know:** Playwright `expect()` assertions auto-wait until the expected condition is met or a timeout occurs. This is more reliable than `time.sleep()`.

```python
from playwright.sync_api import expect

def test_web_first_assertions(page):
    page.goto("https://playwright.dev/python/")
    expect(page).to_have_title(lambda title: "Playwright" in title)
    expect(page.get_by_role("link", name="Docs")).to_be_visible()
```

**Expected result:** The test waits for the page title and Docs link to be correct, then passes.

**Common assertions:**

```python
expect(locator).to_be_visible()
expect(locator).to_be_enabled()
expect(locator).to_have_text("Success")
expect(locator).to_contain_text("Success")
expect(locator).to_have_attribute("href", "/docs")
expect(locator).to_have_value("Brian")
expect(locator).to_be_checked()
```

---

## 17. Module 11 - UI Testing Playground

**What this module covers:** Dynamic IDs, class attributes, hidden layers, load delay, Ajax request, click actions, input fields, scrollbars, dynamic tables, text verification, progress bars, visibility, app login, mouse hover, non-breaking spaces, and overlapped elements.

**What the user needs to know:** Real applications often include unstable IDs, delayed rendering, overlays, scrollbars, asynchronous data, and dynamic content. Good tests target stable business meaning rather than fragile implementation details.

```python
from playwright.sync_api import expect

def test_dynamic_id_pattern(page):
    page.goto("http://uitestingplayground.com/dynamicid")
    page.get_by_role("button", name="Button with Dynamic ID").click()
```

**Expected result:** The test clicks the button even though the button ID changes because it uses the accessible role and name.

```python
def test_ajax_wait(page):
    page.goto("http://uitestingplayground.com/ajax")
    page.get_by_role("button", name="Button Triggering AJAX Request").click()
    expect(page.locator(".bg-success")).to_contain_text("Data loaded")
```

**Expected result:** Playwright waits for the Ajax-loaded success message before passing the assertion.

---

## 18. Module 12 - Playwright Fixtures

**What this module covers:** Function-scope fixtures, session-scope fixtures, browser selection, browser launch arguments, and browser context arguments.

**What the user needs to know:** Fixtures reduce duplication. Function-scoped fixtures run for each test. Session-scoped fixtures run once for the whole test session.

```python
import pytest

@pytest.fixture
def logged_in_page(page):
    page.goto("https://example.com/login")
    page.get_by_label("Email").fill("user@example.com")
    page.get_by_label("Password").fill("password")
    page.get_by_role("button", name="Sign in").click()
    return page

def test_dashboard(logged_in_page):
    logged_in_page.goto("https://example.com/dashboard")
    assert "dashboard" in logged_in_page.url
```

**Expected result:** The fixture logs in before the test checks the dashboard.

**Context argument example:**

```python
@pytest.fixture
def mobile_context(browser):
    return browser.new_context(viewport={"width": 390, "height": 844})
```

**Expected result:** Tests using `mobile_context` run with a mobile-sized viewport.

---

## 19. Module 13 - Page Object Model

**What this module covers:** What POM is, implementation, usage, Playwright homepage POM, and POM usage in tests.

**What the user needs to know:** Page Object Model keeps selectors and page actions in page classes. Tests call meaningful methods instead of duplicating locator details.

```python
from playwright.sync_api import Page, expect

class LoginPage:
    def __init__(self, page: Page):
        self.page = page
        self.email = page.get_by_label("Email")
        self.password = page.get_by_label("Password")
        self.submit = page.get_by_role("button", name="Sign in")

    def open(self):
        self.page.goto("https://example.com/login")

    def login(self, email: str, password: str):
        self.email.fill(email)
        self.password.fill(password)
        self.submit.click()

def test_login(page: Page):
    login_page = LoginPage(page)
    login_page.open()
    login_page.login("user@example.com", "password")
    expect(page).to_have_url(lambda url: "dashboard" in url)
```

**Expected result:** The test logs in using reusable page-object methods and passes when the URL contains `dashboard`.

**Why this matters:** When the login page changes, update the `LoginPage` class instead of every test.

---

## 20. Module 14 - Network Events

**What this module covers:** Network events, request handling, and response modification.

**What the user needs to know:** Network interception lets tests inspect requests, block resources, mock responses, or force error paths.

```python
def test_mock_api_response(page):
    page.route("**/api/user", lambda route: route.fulfill(
        status=200,
        content_type="application/json",
        body='{"name":"Brian","role":"QA"}'
    ))

    page.goto("https://example.com/profile")
```

**Expected result:** Calls to `/api/user` receive the mocked JSON response instead of the real backend response.

**Request inspection example:**

```python
page.on("request", lambda request: print(request.method, request.url))
```

**Expected result:** Each network request method and URL prints to the terminal.

---

## 21. Module 15 - API Testing

**What this module covers:** Making API calls, API request contexts, query strings, CRUD operations, and mock APIs.

**What the user needs to know:** Playwright can test APIs without opening a browser. API tests are fast and useful for validating backend behavior directly.

```python
from playwright.sync_api import Playwright

def test_get_posts(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://jsonplaceholder.typicode.com")
    response = api.get("/posts/1")
    assert response.ok
    data = response.json()
    assert data["id"] == 1
    api.dispose()
```

**Expected result:** The API returns post `1`, the response is OK, and the JSON body contains `id == 1`.

**CRUD pattern:**

```python
created = api.post("/posts", data={"title": "test", "body": "data", "userId": 1})
assert created.status in [200, 201]
```

**Expected result:** The API accepts the request and returns a successful creation-style status.

---

## 22. Module 16 - Optimization

**What this module covers:** Request interception, disabling JavaScript, and running tests in parallel.

**What the user needs to know:** UI tests can be slow when they load images, fonts, analytics, ads, or unnecessary scripts. Interception and parallelism can reduce runtime.

```python
def test_block_images(page):
    page.route("**/*", lambda route: route.abort() if route.request.resource_type == "image" else route.continue_())
    page.goto("https://playwright.dev/python/")
    assert "playwright" in page.url
```

**Expected result:** The page loads without image requests, reducing unnecessary network overhead.

```python
context = browser.new_context(java_script_enabled=False)
```

**Expected result:** JavaScript is disabled for that context, which is useful for testing no-JS fallback behavior.

---

## 23. Module 17 - Tips and Tricks

**What this module covers:** Pytest CLI arguments, Python debugger, device emulation, JavaScript evaluation, and report generation.

**What the user needs to know:** Test productivity improves when you can debug interactively, emulate devices, inspect page state, and generate useful reports.

```python
def test_evaluate_javascript(page):
    page.goto("https://example.com")
    title = page.evaluate("() => document.title")
    assert isinstance(title, str)
```

**Expected result:** JavaScript executes in the browser page and returns the document title to Python.

**Device emulation example:**

```python
def test_mobile_view(playwright):
    iphone = playwright.devices["iPhone 12"]
    browser = playwright.webkit.launch()
    context = browser.new_context(**iphone)
    page = context.new_page()
    page.goto("https://example.com")
    browser.close()
```

**Expected result:** The page opens with iPhone 12 viewport and user-agent settings.

---

## 24. Module 18 - GitHub API

**What this module covers:** GitHub API introduction, project setup, token usage, authorized API context, writing tests, and running tests.

**What the user needs to know:** Authenticated API tests require secure token handling. Store tokens in environment variables, not hard-coded source files.

```python
import os
from playwright.sync_api import Playwright

def test_github_user(playwright: Playwright):
    token = os.getenv("GITHUB_TOKEN")
    api = playwright.request.new_context(
        base_url="https://api.github.com",
        extra_http_headers={"Authorization": f"Bearer {token}"}
    )
    response = api.get("/user")
    assert response.status in [200, 401]
    api.dispose()
```

**Expected result:** With a valid token, GitHub returns the authenticated user. Without a token or with an invalid token, the response is unauthorized.

```text
Valid token -> 200 OK
Missing/invalid token -> 401 Unauthorized
```

---

## 25. Module 19 - Continuous Integration

**What this module covers:** GitHub CI introduction, repository setup, writing CI-safe tests, GitHub Actions workflow setup, and automated test execution.

**What the user needs to know:** CI tests should be repeatable, headless by default, and avoid local-only dependencies. Secrets should be stored in GitHub repository secrets.

```yaml
name: Playwright Python Tests

on:
  push:
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install pytest playwright pytest-playwright
      - run: playwright install --with-deps
      - run: pytest
```

**Expected result:** GitHub Actions installs dependencies, installs browsers, runs tests, and marks the workflow green when tests pass.

---

## 26. Module 20 - Data-Driven Testing

**What this module covers:** Data-driven testing, `pytest.mark.parametrize`, and running the same test with multiple input values.

**What the user needs to know:** Data-driven tests reduce duplication and increase coverage. One test function can validate several input and expected-output combinations.

```python
import pytest

@pytest.mark.parametrize("username,password,expected", [
    ("standard_user", "secret_sauce", True),
    ("locked_out_user", "secret_sauce", False),
    ("invalid", "bad", False),
])
def test_login_data(username, password, expected):
    result = username == "standard_user" and password == "secret_sauce"
    assert result == expected
```

**Expected result:** Pytest runs the test three separate times with different data rows.

```text
3 passed
```

---

## 27. Module 21 - Behavior-Driven Development

**What this module covers:** BDD concepts, project setup, feature files, step definitions, and running Behave tests.

**What the user needs to know:** BDD uses human-readable scenarios to connect business requirements to automated tests. Feature files describe behavior; step definitions implement the automation.

```gherkin
Feature: Login

  Scenario: Valid user logs in
    Given the login page is open
    When the user logs in with valid credentials
    Then the dashboard should be displayed
```

```python
from behave import given, when, then
from playwright.sync_api import expect

@given("the login page is open")
def open_login_page(context):
    context.page.goto("https://example.com/login")

@when("the user logs in with valid credentials")
def login(context):
    context.page.get_by_label("Email").fill("user@example.com")
    context.page.get_by_label("Password").fill("password")
    context.page.get_by_role("button", name="Sign in").click()

@then("the dashboard should be displayed")
def verify_dashboard(context):
    expect(context.page).to_have_url(lambda url: "dashboard" in url)
```

**Expected result:** Behave executes each Given/When/Then step and reports the scenario as passed when the dashboard URL appears.

```text
1 scenario passed
3 steps passed
```

---

## 28. Best Practices and Troubleshooting

### Best Practices

1. Prefer `get_by_role`, `get_by_label`, and `get_by_text` before CSS or XPath.
2. Use Playwright `expect()` assertions instead of fixed sleeps.
3. Keep browser setup in fixtures.
4. Keep selectors and page actions in Page Object Model classes.
5. Store tokens and passwords in environment variables.
6. Use traces and screenshots for failure debugging.
7. Keep CI tests deterministic and independent.
8. Use parametrization for repeated input/output combinations.
9. Use API tests to validate backend behavior before UI workflows.
10. Use BDD when scenarios need to be readable by business stakeholders.

### Troubleshooting

| Problem | Likely Cause | Fix |
|---|---|---|
| Browser does not launch | Browsers not installed | Run `playwright install` |
| Test cannot find element | Locator is unstable or incorrect | Use role/text/label locators or inspect with codegen |
| Test is flaky | App loads asynchronously | Use web-first assertions and event waits |
| Login fails in CI | Missing secret or blocked login flow | Use storage state or environment variables |
| API test returns 401 | Missing or invalid token | Set token as an environment variable |
| Test passes locally but fails in CI | Environment difference | Run headless locally and capture trace/video |
| File upload fails | Bad file path | Use a repo-relative file path or fixture-created file |

---

## 29. Author

**Brian McCarthy**  
Playwright Automation with Python and Pytest Showcase
