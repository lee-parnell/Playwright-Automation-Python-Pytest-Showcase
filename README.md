# Playwright Automation with Python and Pytest Showcase

**Written by Brian McCarthy**

A complete hands-on Playwright automation guide using **Python**, **Pytest**, `pytest-playwright`, Page Object Model design, fixtures, web-first assertions, API testing, network interception, CI execution, data-driven testing, and behavior-driven development.

This README is organized as a detailed numbered tutorial. Each module explains the purpose of the module, the subtopics covered, what the user needs to know, practical code examples, and expected results.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Repository Goals](#2-repository-goals)
3. [Languages, Tools, and Frameworks](#3-languages-tools-and-frameworks)
4. [Project File Links](#4-project-file-links)
5. [Core Commands](#5-core-commands)
6. [Module 1 - Getting Started](#6-module-1---getting-started)
7. [Module 2 - Locators](#7-module-2---locators)
8. [Module 3 - Actions](#8-module-3---actions)
9. [Module 4 - Events](#9-module-4---events)
10. [Module 5 - Authentication](#10-module-5---authentication)
11. [Module 6 - Automated Mail Checker](#11-module-6---automated-mail-checker)
12. [Module 7 - Pytest](#12-module-7---pytest)
13. [Module 8 - pytest-playwright Plugin](#13-module-8---pytest-playwright-plugin)
14. [Module 9 - Playwright Tools](#14-module-9---playwright-tools)
15. [Module 10 - Web-First Assertions](#15-module-10---web-first-assertions)
16. [Module 11 - UI Testing Playground](#16-module-11---ui-testing-playground)
17. [Module 12 - Playwright Fixtures](#17-module-12---playwright-fixtures)
18. [Module 13 - Page Object Model](#18-module-13---page-object-model)
19. [Module 14 - Network Events](#19-module-14---network-events)
20. [Module 15 - API Testing](#20-module-15---api-testing)
21. [Module 16 - Optimization](#21-module-16---optimization)
22. [Module 17 - Tips and Tricks](#22-module-17---tips-and-tricks)
23. [Module 18 - GitHub API](#23-module-18---github-api)
24. [Module 19 - Continuous Integration](#24-module-19---continuous-integration)
25. [Module 20 - Data-Driven Testing](#25-module-20---data-driven-testing)
26. [Module 21 - Behavior-Driven Development](#26-module-21---behavior-driven-development)
27. [Playwright Automation Top 20 Interview Questions and Answers](#27-playwright-automation-top-20-interview-questions-and-answers)
28. [Best Practices and Troubleshooting](#28-best-practices-and-troubleshooting)
29. [Author](#29-author)

---

## 1. Project Overview

This repository demonstrates browser automation and test engineering with Playwright for Python. It starts with installation and browser launch scripts, then progresses into locators, actions, event handling, authentication, automated email checking, Pytest, plugin fixtures, Playwright debugging tools, web-first assertions, UI challenge automation, custom fixtures, Page Object Model, network events, API testing, performance optimization, GitHub API automation, CI, data-driven testing, and BDD.

The repository is designed as a practical learning and portfolio project. It shows that the author can create reliable UI tests, API tests, reusable fixtures, maintainable page objects, CI-ready automation, and scalable test patterns.

---

## 2. Repository Goals

1. Demonstrate Playwright automation in Python.
2. Show reliable locator strategies for modern web apps.
3. Use realistic user actions: clicks, text input, file upload, dropdowns, keyboard shortcuts, and hover.
4. Handle auto-waiting, navigation, dialogs, downloads, asynchronous operations, and events.
5. Save and reuse authentication state.
6. Build Pytest test cases with fixtures and scoped setup.
7. Use `pytest-playwright` fixtures such as `page`, `context`, and `browser`.
8. Apply web-first assertions to reduce flaky test behavior.
9. Organize UI automation with Page Object Model.
10. Test APIs with Playwright request contexts.
11. Mock and intercept network requests.
12. Improve runtime with optimization patterns.
13. Run tests in GitHub Actions.
14. Expand coverage using data-driven and BDD techniques.

---

## 3. Languages, Tools, and Frameworks

| Tool / Language | Purpose |
|---|---|
| Python | Main automation language |
| Playwright for Python | Browser automation, UI assertions, event handling, API request contexts, tracing, screenshots, and network mocking |
| Pytest | Test discovery, test execution, fixtures, parametrization, and reporting |
| pytest-playwright | Plugin-provided browser/page/context fixtures and command-line browser options |
| Behave | BDD feature files and Given/When/Then step definitions |
| GitHub API | Authenticated API automation practice |
| GitHub Actions | Continuous integration execution |
| HTML / Test Pages | Practice pages for UI automation examples |

---

## 4. Project File Links

| Section | Link | Main Focus |
|---:|---|---|
| 1 | [S01 - Getting Started](S01%20-%20Getting%20Started/) | Installation, browser launch, documentation, link clicking, script overview |
| 2 | [S02 - Locators](S02%20-%20Locators/) | Role, input, text, alt text, title, CSS, XPath, and other locators |
| 3 | S03 - Actions | Mouse, text input, radio buttons, checkboxes, switches, select options, dropdowns, uploads, shortcuts |
| 4 | [S04 - Events](S04%20-%20Events/) | Auto-waiting, navigation waits, custom waits, listeners, dialogs, downloads, sync/async |
| 5 | [S05 - Authentication](S05%20-%20Authentication/) | Sign-in, storage state, auth reuse, login edge cases |
| 6 | [S06 - Automated Mail Checker](S06%20-%20Automated%20Mail%20Checker/) | Email location, email data extraction, combined locators, terminal checks |
| 7 | [S07 - pytest](S07%20-%20pytest/) | Pytest basics, writing/running tests, type hints, state, fixtures, scope |
| 8 | [S08 - pytest-playwright Plugin](S08%20-%20pytest-playwright%20Plugin/) | Plugin setup, Playwright tests, config, hooks |
| 9 | [S09 - Playwright Tools](S09%20-%20Playwright%20Tools/) | Codegen, inspector, trace viewer, screenshots, debugging tools |
| 10 | [S10 - Web-First Assertions](S10%20-%20Web-First%20Assertions/) | Page, element state, text, attributes, inputs, checkboxes, option menus |
| 11 | [S11 - UI Testing Playground](S11%20-%20UI%20Testing%20Playground/) | Dynamic IDs, hidden layers, Ajax, dynamic tables, progress bars, visibility, login, hover |
| 12 | [S12 - Playwright Fixtures](S12%20-%20Playwright%20Fixtures/) | Function scope, session scope, browser selection, launch/context args |
| 13 | [S13 - Page Object Model](S13%20-%20Page%20Object%20Model/) | POM implementation and usage |
| 14 | S14 - Network Events | Requests, request handling, response modification |
| 15 | [S15 - API Testing](S15%20-%20API%20Testing/) | API calls, request context, query strings, CRUD, mocks |
| 16 | [S16 - Optimization](S16%20-%20Optimization/) | Request interception, disabling JavaScript, parallel execution |
| 17 | [S17 - Tips and Tricks](S17%20-%20Tips%20and%20Tricks/) | CLI args, debugger, device emulation, JS evaluation, reports |
| 18 | [S18 - GitHub API](S18%20-%20GitHub%20API/) | Token setup, authorized API context, GitHub tests |
| 19 | [S19 - Continuous Integration](S19%20-%20Continuous%20Integration/) | GitHub Actions, automated test runs |
| 20 | [S20 - Data Driven Testing](S20%20-%20Data%20Driven%20Testing/) | Pytest parametrization |
| 21 | [S21 - Behaviour Driven Development](S21%20-%20Behaviour%20Driven%20Development/) | Behave feature files and step implementations |

---

## 5. Core Commands

```bash
pip install pytest playwright pytest-playwright behave
playwright install
pytest
pytest --headed
pytest --browser chromium
pytest path/to/test_file.py
pytest -k login
pytest --tracing on
playwright show-trace trace.zip
behave
```

**Expected result:** Dependencies install, Playwright browsers are downloaded, tests are discovered by Pytest or Behave, and pass/fail results are printed in the terminal.

---

## 6. Module 1 - Getting Started

**Subtopics covered:** Playwright installation, Playwright documentation, browser launch, clicking a link element, and script overview.

**What to know:** A basic Playwright script starts the Playwright driver, launches a browser, creates a page, navigates to a URL, interacts with the page, and closes the browser. Playwright supports Chromium, Firefox, and WebKit.

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    page = browser.new_page()
    page.goto("https://playwright.dev/python/")
    print(page.title())
    page.get_by_role("link", name="Docs").click()
    print(page.url)
    browser.close()
```

**Expected result:** Chromium opens, loads the Playwright Python site, prints the title, clicks the Docs link, prints the resulting URL, and closes.

```text
Fast and reliable end-to-end testing for modern web apps | Playwright Python
https://playwright.dev/python/docs/intro
```

**Necessary details:**

- Use `headless=False` when learning or debugging.
- Use `headless=True` or the default in CI.
- Always close the browser when writing standalone scripts.
- In Pytest, plugin fixtures often handle browser lifecycle automatically.

---

## 7. Module 2 - Locators

**Subtopics covered:** Playwright Python REPL, locator role, input field locators, text locators, alt text, title, CSS selectors, CSS hierarchy, CSS pseudo-classes, XPath, XPath functions, and other locators.

**What to know:** Locators are not just selectors; they are Playwright objects that auto-wait and re-query the DOM. Prefer user-facing locators before technical CSS/XPath selectors.

```python
from playwright.sync_api import Page, expect

def test_locator_examples(page: Page):
    page.goto("https://playwright.dev/python/")
    expect(page.get_by_role("heading", name="Playwright")).to_be_visible()
    page.get_by_role("link", name="Docs").click()
    expect(page).to_have_url(lambda url: "docs" in url)
```

```python
def test_input_and_text_locators(page: Page):
    page.goto("https://example.com/search")
    page.get_by_placeholder("Search").fill("playwright")
    page.get_by_text("Submit").click()
```

```python
def test_css_and_xpath(page: Page):
    page.goto("https://example.com")
    page.locator("main nav a:first-child").click()
    page.locator("xpath=//button[contains(., 'Save')]").click()
```

**Expected result:** Elements are found by accessibility role, placeholder, text, CSS hierarchy, pseudo-class, or XPath function and then interacted with.

**Locator decision table:**

| Locator Type | Use When |
|---|---|
| `get_by_role()` | Best for buttons, links, headings, checkboxes, dialogs, menus |
| `get_by_label()` | Best for accessible forms |
| `get_by_placeholder()` | Useful for inputs with placeholder text |
| `get_by_text()` | Useful for visible text content |
| `get_by_alt_text()` | Useful for images with alt text |
| `get_by_title()` | Useful for title attributes |
| CSS | Useful when semantic locators are unavailable |
| XPath | Last resort for complex traversal |

---

## 8. Module 3 - Actions

**Subtopics covered:** Mouse actions, text input, radio buttons, checkboxes, switches, select option, dropdown menu, file upload, and keyboard shortcuts.

**What to know:** Playwright actions auto-wait until elements are visible, enabled, stable, and ready for interaction. This makes tests more reliable than raw Selenium-style click timing.

```python
from playwright.sync_api import Page, expect

def test_form_actions(page: Page):
    page.goto("https://example.com/form")
    page.get_by_label("First Name").fill("Brian")
    page.get_by_label("Subscribe").check()
    page.get_by_label("Country").select_option("US")
    page.get_by_role("button", name="Submit").click()
    expect(page.get_by_text("Form submitted")).to_be_visible()
```

```python
def test_keyboard_and_upload(page: Page):
    page.goto("https://example.com/upload")
    page.locator("input[type='file']").set_input_files("tests/data/sample.txt")
    page.keyboard.press("Control+S")
```

**Expected result:** Text fields are filled, checkbox/radio style controls are selected, dropdowns are changed, a file is attached, and keyboard shortcuts are sent to the page.

**Necessary details:**

- Use `fill()` for replacing existing text.
- Use `type()` when keystroke-by-keystroke behavior matters.
- Use `select_option()` for native `<select>` elements.
- Custom dropdowns usually require `click()` plus selecting a visible option.

---

## 9. Module 4 - Events

**Subtopics covered:** Playwright auto-waiting, auto-waiting navigation, custom waiting, event listeners, dialogs, downloads, sync vs. async, and asynchronous Playwright.

**What to know:** Events are critical when actions trigger browser-level behavior such as downloads, dialogs, popups, network calls, or navigation. Playwright has context managers for many of these events.

```python
from playwright.sync_api import Page, expect

def test_dialog(page: Page):
    page.goto("https://the-internet.herokuapp.com/javascript_alerts")
    page.on("dialog", lambda dialog: dialog.accept())
    page.get_by_text("Click for JS Alert").click()
    expect(page.locator("#result")).to_have_text("You successfully clicked an alert")
```

```python
def test_download(page: Page):
    page.goto("https://example.com/downloads")
    with page.expect_download() as download_info:
        page.get_by_text("Download report").click()
    download = download_info.value
    download.save_as("downloaded-report.pdf")
```

```python
import asyncio
from playwright.async_api import async_playwright

async def main():
    async with async_playwright() as p:
        browser = await p.chromium.launch()
        page = await browser.new_page()
        await page.goto("https://example.com")
        await browser.close()

asyncio.run(main())
```

**Expected result:** Dialogs are handled, downloads are captured, and async code performs the same browser workflow using `await`.

---

## 10. Module 5 - Authentication

**Subtopics covered:** Google sign-in concepts, saving authentication state, reusing auth state, and login issues.

**What to know:** Authentication should be handled carefully. Avoid logging in through the UI in every test when possible. Save storage state after a successful login and reuse it.

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

```python
def test_reuse_auth_state(browser):
    context = browser.new_context(storage_state="auth_state.json")
    page = context.new_page()
    page.goto("https://example.com/account")
    assert "account" in page.url
```

**Expected result:** The first script creates `auth_state.json`; the test reuses it and skips login.

**Security notes:**

- Do not commit real credentials or real auth state to public repositories.
- Use environment variables for usernames, passwords, and tokens.
- Some providers block automation or require MFA; use test accounts and test environments.

---

## 11. Module 6 - Automated Mail Checker

**Subtopics covered:** Automated mail checker overview, project setup, locating new emails, locating email data, combining locators, and checking email from the terminal.

**What to know:** Email automation requires stable mailbox locators and clear filtering. Tests should search by sender, subject, timestamp, body text, or unique test identifiers rather than relying only on the first row.

```python
from playwright.sync_api import Page, expect

def test_locate_email(page: Page):
    page.goto("https://example-mail-app.test/inbox")
    email = page.locator(".email-row").filter(has_text="Password reset")
    expect(email).to_be_visible()
    expect(email.locator(".subject")).to_contain_text("Password reset")
```

```python
def get_email_data(page: Page, subject: str) -> dict:
    page.goto("https://example-mail-app.test/inbox")
    row = page.locator(".email-row").filter(has_text=subject).first
    return {
        "sender": row.locator(".sender").inner_text(),
        "subject": row.locator(".subject").inner_text(),
        "preview": row.locator(".preview").inner_text(),
    }
```

**Expected result:** The test locates the target email, confirms it is visible, and extracts sender/subject/preview data.

**Terminal usage pattern:**

```python
if __name__ == "__main__":
    print("Checking latest email from terminal...")
```

---

## 12. Module 7 - Pytest

**Subtopics covered:** Testing Pytest, writing tests, running tests, type hinting, test state, Pytest fixtures, using fixtures, and fixture scope.

**What to know:** Pytest discovers files and functions by naming convention. Fixtures inject reusable dependencies. Scope controls how often setup runs.

```python
import pytest

@pytest.fixture
def user_data() -> dict:
    return {"username": "brian", "role": "qa"}

def test_user_role(user_data: dict):
    assert user_data["role"] == "qa"
```

```python
@pytest.fixture(scope="session")
def config():
    return {"base_url": "https://example.com"}

@pytest.fixture(scope="function")
def empty_cart():
    return []
```

**Expected result:** Pytest injects fixture return values into tests. The first test passes and prints a result such as `1 passed`.

**Necessary details:**

- Function scope runs once per test.
- Class scope runs once per test class.
- Module scope runs once per module.
- Session scope runs once per test run.

---

## 13. Module 8 - pytest-playwright Plugin

**Subtopics covered:** Installing the plugin, Playwright test, running test, Pytest config, and test hooks.

**What to know:** `pytest-playwright` supplies the `page`, `context`, `browser`, and `browser_name` fixtures. It also enables CLI browser selection.

```python
from playwright.sync_api import Page, expect

def test_homepage(page: Page):
    page.goto("https://playwright.dev/python/")
    expect(page).to_have_title(lambda title: "Playwright" in title)
```

```ini
# pytest.ini
[pytest]
addopts = --browser chromium
```

```python
# conftest.py
def pytest_runtest_setup(item):
    print(f"Running test: {item.name}")
```

**Expected result:** The plugin creates the browser page automatically, the test opens the page, and the title assertion passes.

---

## 14. Module 9 - Playwright Tools

**Subtopics covered:** Playwright debugging tools, code generation, screenshots, trace viewer, headed mode, slow motion, videos, and reports.

**What to know:** Playwright tools improve productivity by showing what the browser did and why a test failed. Trace viewer is one of the most useful tools for diagnosing flaky UI tests.

```python
def test_screenshot(page):
    page.goto("https://playwright.dev/python/")
    page.screenshot(path="homepage.png", full_page=True)
```

```bash
playwright codegen https://playwright.dev/python/
pytest --headed --slowmo 500
pytest --tracing on
playwright show-trace trace.zip
```

**Expected result:** Screenshots, traces, and codegen output help inspect browser behavior and generate starter locator code.

---

## 15. Module 10 - Web-First Assertions

**Subtopics covered:** Assertions page, element state, element text, attribute, input field, checkbox, and option menu.

**What to know:** Playwright assertions wait automatically. This reduces flaky tests caused by timing delays.

```python
from playwright.sync_api import expect

def test_assertions(page):
    page.goto("https://example.com/settings")
    expect(page).to_have_url(lambda url: "settings" in url)
    expect(page.get_by_role("heading", name="Settings")).to_be_visible()
    expect(page.get_by_label("Email")).to_have_value("user@example.com")
    expect(page.get_by_label("Subscribe")).to_be_checked()
```

```python
expect(page.locator("#save")).to_have_attribute("type", "submit")
expect(page.locator("select#country")).to_have_value("US")
```

**Expected result:** Each assertion waits for the expected condition and passes when the UI state is correct.

---

## 16. Module 11 - UI Testing Playground

**Subtopics covered:** Dynamic ID, class attribute, hidden layer, load delay, Ajax request, click action, input field, scrollbars, dynamic table, verify text, progress bar, visibility, app login, mouse hover, NBSP character, and overlapped elements.

**What to know:** UI Testing Playground examples represent real automation problems: unstable IDs, overlays, delays, hidden content, dynamic data, scroll behavior, and text formatting issues.

```python
from playwright.sync_api import expect

def test_dynamic_id(page):
    page.goto("http://uitestingplayground.com/dynamicid")
    page.get_by_role("button", name="Button with Dynamic ID").click()
```

```python
def test_ajax_request(page):
    page.goto("http://uitestingplayground.com/ajax")
    page.get_by_role("button", name="Button Triggering AJAX Request").click()
    expect(page.locator(".bg-success")).to_contain_text("Data loaded")
```

```python
def test_dynamic_table(page):
    page.goto("http://uitestingplayground.com/dynamictable")
    chrome_row = page.get_by_role("row").filter(has_text="Chrome")
    expect(chrome_row).to_contain_text("Chrome")
```

```python
def test_nbsp(page):
    page.goto("http://uitestingplayground.com/nbsp")
    expect(page.get_by_text("My Button", exact=True)).to_be_visible()
```

**Expected result:** Tests avoid brittle IDs and use meaningful locator strategies for dynamic and difficult UI cases.

---

## 17. Module 12 - Playwright Fixtures

**Subtopics covered:** Function scope fixtures, session scope fixtures, browser selection, browser launch arguments, and context arguments.

**What to know:** Fixtures centralize setup, reduce duplicate code, and make tests easier to maintain.

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

```python
@pytest.fixture(scope="session")
def browser_context_args(browser_context_args):
    return {**browser_context_args, "viewport": {"width": 1440, "height": 900}}
```

**Expected result:** Tests receive preconfigured pages or contexts without repeating setup logic.

---

## 18. Module 13 - Page Object Model

**Subtopics covered:** What POM is, POM implementation, POM usage, Playwright homepage POM, and POM usage in tests.

**What to know:** POM hides selectors and UI actions behind page classes. Tests become clearer and less brittle.

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

class DashboardPage:
    def __init__(self, page: Page):
        self.page = page
        self.heading = page.get_by_role("heading", name="Dashboard")

    def should_be_open(self):
        expect(self.heading).to_be_visible()
```

```python
def test_login(page: Page):
    login = LoginPage(page)
    dashboard = DashboardPage(page)
    login.open()
    login.login("user@example.com", "password")
    dashboard.should_be_open()
```

**Expected result:** The test reads like a user workflow, while locator details stay inside page classes.

---

## 19. Module 14 - Network Events

**Subtopics covered:** Network events, handle requests, and modify response.

**What to know:** Network handling lets tests observe, block, mock, or modify browser traffic.

```python
def test_request_logging(page):
    page.on("request", lambda request: print(request.method, request.url))
    page.goto("https://example.com")
```

```python
def test_mock_user_api(page):
    page.route("**/api/user", lambda route: route.fulfill(
        status=200,
        content_type="application/json",
        body='{"name":"Brian","role":"QA"}'
    ))
    page.goto("https://example.com/profile")
```

```python
def test_block_images(page):
    page.route("**/*", lambda route: route.abort() if route.request.resource_type == "image" else route.continue_())
    page.goto("https://example.com")
```

**Expected result:** Requests are logged, selected API calls are mocked, and image requests are blocked when desired.

---

## 20. Module 15 - API Testing

**Subtopics covered:** Making an API call, API request context, API query string, CRUD operations, and mock API.

**What to know:** Playwright can test APIs directly through `APIRequestContext`. API tests are faster than UI tests and help verify backend behavior.

```python
from playwright.sync_api import Playwright

def test_get_post(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://jsonplaceholder.typicode.com")
    response = api.get("/posts/1")
    assert response.ok
    assert response.json()["id"] == 1
    api.dispose()
```

```python
def test_query_string(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://jsonplaceholder.typicode.com")
    response = api.get("/comments", params={"postId": 1})
    assert response.ok
    assert len(response.json()) > 0
    api.dispose()
```

```python
def test_create_update_delete(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://jsonplaceholder.typicode.com")
    created = api.post("/posts", data={"title": "test", "body": "data", "userId": 1})
    assert created.status in [200, 201]
    updated = api.put("/posts/1", data={"title": "updated", "body": "data", "userId": 1})
    assert updated.ok
    deleted = api.delete("/posts/1")
    assert deleted.ok
    api.dispose()
```

**Expected result:** GET, query string, POST, PUT, and DELETE requests return successful responses and expected JSON data.

---

## 21. Module 16 - Optimization

**Subtopics covered:** Intercept requests, disabling JavaScript, and running tests in parallel.

**What to know:** Optimization reduces test runtime and isolates behavior. Blocking unnecessary resources and running tests in parallel are common strategies.

```python
def test_block_fonts_and_images(page):
    def handle(route):
        if route.request.resource_type in ["image", "font"]:
            route.abort()
        else:
            route.continue_()

    page.route("**/*", handle)
    page.goto("https://playwright.dev/python/")
    assert "playwright" in page.url
```

```python
def test_without_javascript(browser):
    context = browser.new_context(java_script_enabled=False)
    page = context.new_page()
    page.goto("https://example.com")
    assert page.locator("body").is_visible()
    context.close()
```

```bash
pytest -n auto
```

**Expected result:** Nonessential requests are blocked, no-JavaScript behavior can be validated, and tests run in parallel when `pytest-xdist` is installed.

---

## 22. Module 17 - Tips and Tricks

**Subtopics covered:** Pytest CLI arguments, Python debugger, device emulation, evaluate JavaScript, and generate reports.

**What to know:** Productivity tools make it easier to debug, inspect, emulate, and report test behavior.

```python
def test_evaluate_javascript(page):
    page.goto("https://example.com")
    title = page.evaluate("() => document.title")
    assert isinstance(title, str)
```

```python
def test_device_emulation(playwright):
    iphone = playwright.devices["iPhone 12"]
    browser = playwright.webkit.launch()
    context = browser.new_context(**iphone)
    page = context.new_page()
    page.goto("https://example.com")
    browser.close()
```

```bash
pytest -k login
pytest -x
pytest --maxfail=1
pytest --html=report.html
```

**Expected result:** JavaScript executes in the browser, device settings emulate mobile, and CLI options control test selection and reporting.

---

## 23. Module 18 - GitHub API

**Subtopics covered:** GitHub API introduction, project setup, GitHub token, authorized API context, writing tests, and running tests.

**What to know:** Authenticated API tests should use environment variables for tokens. Never hard-code secrets.

```python
import os
from playwright.sync_api import Playwright

def test_github_authenticated_user(playwright: Playwright):
    token = os.getenv("GITHUB_TOKEN")
    api = playwright.request.new_context(
        base_url="https://api.github.com",
        extra_http_headers={"Authorization": f"Bearer {token}"}
    )
    response = api.get("/user")
    assert response.status in [200, 401]
    api.dispose()
```

```python
def test_github_repo_metadata(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://api.github.com")
    response = api.get("/repos/microsoft/playwright")
    assert response.ok
    assert response.json()["name"] == "playwright"
    api.dispose()
```

**Expected result:** Public GitHub API calls return repository metadata. Authenticated calls return user data when the token is valid.

---

## 24. Module 19 - Continuous Integration

**Subtopics covered:** GitHub CI introduction, setup repository, writing tests, GitHub Action, and running automated tests.

**What to know:** CI automation should install dependencies, install Playwright browsers, run tests in headless mode, and upload reports or traces when useful.

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
      - run: pytest --tracing on
```

**Expected result:** GitHub Actions checks out the repo, installs Python dependencies, installs browser dependencies, runs tests, and marks the workflow pass/fail.

---

## 25. Module 20 - Data-Driven Testing

**Subtopics covered:** What data-driven testing is, Pytest parametrization, and running parametrized tests.

**What to know:** Data-driven tests run the same logic with multiple data rows. This avoids copy/paste test duplication.

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

**Expected result:** Pytest executes the same test three times.

```text
3 passed
```

```python
@pytest.mark.parametrize("search_term", ["playwright", "pytest", "automation"])
def test_search_terms(page, search_term):
    page.goto("https://example.com/search")
    page.get_by_placeholder("Search").fill(search_term)
```

**Expected result:** The browser test runs once per search term.

---

## 26. Module 21 - Behavior-Driven Development

**Subtopics covered:** What BDD is, project setup, defining a feature, implementing steps, running tests, practice assessment patterns, and full course assessment patterns.

**What to know:** BDD expresses expected behavior in Given/When/Then language. Feature files are readable by non-developers, while step definitions contain Python automation code.

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

```python
# environment.py
from playwright.sync_api import sync_playwright

def before_scenario(context, scenario):
    context.playwright = sync_playwright().start()
    context.browser = context.playwright.chromium.launch()
    context.page = context.browser.new_page()

def after_scenario(context, scenario):
    context.browser.close()
    context.playwright.stop()
```

**Expected result:** Behave maps feature steps to Python functions, opens the browser before each scenario, closes it afterward, and reports scenario results.

```text
1 scenario passed
3 steps passed
```

---

## 27. Playwright Automation Top 20 Interview Questions and Answers

### 1. What is Playwright?

Playwright is an end-to-end automation framework for testing web applications across Chromium, Firefox, and WebKit. It supports browser automation, UI testing, API testing, tracing, screenshots, videos, network interception, and multiple languages including Python.

### 2. Why use Playwright instead of Selenium?

Playwright has built-in auto-waiting, modern locator strategies, browser contexts for isolation, native network interception, trace viewer, API testing support, and strong handling for modern single-page applications.

### 3. What is a browser context?

A browser context is an isolated browser session. Each context has its own cookies, local storage, session storage, permissions, and viewport. It is useful for running independent tests without sharing state.

```python
context = browser.new_context()
page = context.new_page()
```

### 4. What is the difference between `browser`, `context`, and `page`?

`browser` is the launched browser process. `context` is an isolated session inside the browser. `page` is a browser tab inside a context.

### 5. What are Playwright locators?

Locators are objects used to find and interact with elements. They auto-wait and re-query the DOM, making them more reliable than one-time element handles.

```python
page.get_by_role("button", name="Submit").click()
```

### 6. Which locator strategy is preferred?

Prefer user-facing and accessibility-based locators: `get_by_role`, `get_by_label`, `get_by_text`, and `get_by_placeholder`. Use CSS or XPath only when semantic locators are not practical.

### 7. What is auto-waiting?

Auto-waiting means Playwright waits for elements to be actionable before performing actions. For example, Playwright waits until an element is visible, stable, enabled, and able to receive events before clicking.

### 8. What are web-first assertions?

Web-first assertions are Playwright assertions that automatically wait until a condition is satisfied or a timeout occurs.

```python
expect(page.get_by_text("Saved")).to_be_visible()
```

### 9. How do you handle alerts or dialogs?

Use the `dialog` event.

```python
page.on("dialog", lambda dialog: dialog.accept())
page.get_by_text("Show Alert").click()
```

### 10. How do you handle downloads?

Use `page.expect_download()` around the action that triggers the download.

```python
with page.expect_download() as download_info:
    page.get_by_text("Download").click()
download_info.value.save_as("file.pdf")
```

### 11. How do you save authentication state?

After logging in, call `context.storage_state(path="auth_state.json")` and reuse that file in future contexts.

### 12. What is the Page Object Model?

Page Object Model is a design pattern that stores page locators and page actions in classes. Tests call page methods instead of repeating selectors.

### 13. How does Pytest integrate with Playwright?

Pytest runs the tests, while Playwright controls the browser. With `pytest-playwright`, tests can use fixtures such as `page`, `browser`, and `context` directly.

### 14. What is a Pytest fixture?

A fixture is reusable setup/teardown logic. Fixtures can create test data, pages, contexts, API clients, or authenticated sessions.

```python
@pytest.fixture
def base_url():
    return "https://example.com"
```

### 15. How do you perform API testing in Playwright?

Use `playwright.request.new_context()` to create an API request context.

```python
api = playwright.request.new_context(base_url="https://api.example.com")
response = api.get("/users")
assert response.ok
```

### 16. How do you intercept network requests?

Use `page.route()` to continue, abort, or fulfill matching requests.

```python
page.route("**/*.png", lambda route: route.abort())
```

### 17. How do you mock an API response?

Use `route.fulfill()`.

```python
page.route("**/api/user", lambda route: route.fulfill(status=200, body='{"name":"Brian"}'))
```

### 18. How do you run Playwright tests in CI?

Install dependencies, install Playwright browsers, and run Pytest in a CI workflow such as GitHub Actions.

```yaml
- run: pip install pytest playwright pytest-playwright
- run: playwright install --with-deps
- run: pytest
```

### 19. How do you debug flaky Playwright tests?

Use headed mode, slow motion, screenshots, videos, traces, console logs, network logs, and better web-first assertions. Avoid fixed sleeps unless there is no better synchronization point.

### 20. What is data-driven testing?

Data-driven testing runs the same test logic with multiple input values and expected results.

```python
@pytest.mark.parametrize("value", ["a", "b", "c"])
def test_values(value):
    assert value in ["a", "b", "c"]
```

---

## 28. Best Practices and Troubleshooting

### Best Practices

1. Prefer semantic locators over CSS and XPath.
2. Use Playwright `expect()` assertions instead of `time.sleep()`.
3. Centralize setup with Pytest fixtures.
4. Use Page Object Model for repeated page workflows.
5. Keep test data isolated.
6. Use API tests for backend validation and UI tests for user journeys.
7. Store credentials and tokens in environment variables.
8. Save authentication state for repeated authenticated tests.
9. Capture traces, screenshots, and videos for debugging.
10. Keep CI tests deterministic, independent, and headless by default.

### Troubleshooting

| Problem | Likely Cause | Fix |
|---|---|---|
| Browser does not launch | Browsers not installed | Run `playwright install` |
| Element not found | Locator is unstable or wrong | Use role/label/text locators or inspect with codegen |
| Test is flaky | Page changes asynchronously | Use web-first assertions and event waits |
| Login fails in CI | Missing secret or blocked login flow | Use storage state and repository secrets |
| API test returns 401 | Missing/invalid token | Set token as an environment variable |
| Download test fails | Event not wrapped correctly | Use `page.expect_download()` before clicking |
| File upload fails | Bad path | Use repo-relative file paths |
| Test passes locally but fails in CI | Environment mismatch | Run locally headless and capture traces |

---

## 29. Author

**Brian McCarthy**  
Playwright Automation with Python and Pytest Showcase
