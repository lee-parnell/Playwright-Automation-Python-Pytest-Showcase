# Playwright Automation with Python and Pytest Showcase

**Written by Brian McCarthy**

A complete hands-on Playwright automation guide using **Python**, **Pytest**, `pytest-playwright`, Page Object Model design, fixtures, web-first assertions, API testing, network interception, CI execution, data-driven testing, behavior-driven development, and supplemental advanced automation topics.

This README is organized as a numbered tutorial. Existing sections cover the main Python Playwright/Pytest modules. Supplemental modules were added only for subject matter from the additional course outline that was not already covered or not covered in enough depth.

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
27. [Supplemental Module 22 - Playwright vs Cypress](#27-supplemental-module-22---playwright-vs-cypress)
28. [Supplemental Module 23 - Development Environment, Test Application, and JavaScript TypeScript Fundamentals](#28-supplemental-module-23---development-environment-test-application-and-javascript-typescript-fundamentals)
29. [Supplemental Module 24 - DOM Terminology and Advanced Locator Architecture](#29-supplemental-module-24---dom-terminology-and-advanced-locator-architecture)
30. [Supplemental Module 25 - Advanced UI Widgets and Complex Interactions](#30-supplemental-module-25---advanced-ui-widgets-and-complex-interactions)
31. [Supplemental Module 26 - Advanced Page Object Architecture](#31-supplemental-module-26---advanced-page-object-architecture)
32. [Supplemental Module 27 - Advanced API State, Mocking, Authentication, and Cleanup](#32-supplemental-module-27---advanced-api-state-mocking-authentication-and-cleanup)
33. [Supplemental Module 28 - Advanced Framework Configuration, Environment Variables, Retries, Tags, and Test Data](#33-supplemental-module-28---advanced-framework-configuration-environment-variables-retries-tags-and-test-data)
34. [Supplemental Module 29 - Reporting, Screenshots, Videos, and Visual Testing](#34-supplemental-module-29---reporting-screenshots-videos-and-visual-testing)
35. [Supplemental Module 30 - Docker, GitHub Actions, and Argos CI](#35-supplemental-module-30---docker-github-actions-and-argos-ci)
36. [Playwright Automation Top 20 Interview Questions and Answers](#36-playwright-automation-top-20-interview-questions-and-answers)
37. [Best Practices and Troubleshooting](#37-best-practices-and-troubleshooting)
38. [Author](#38-author)

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
15. Add supplemental coverage for environment setup, JavaScript/TypeScript fundamentals, advanced widgets, framework architecture, reporting, Docker, and visual validation.

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
| JavaScript / TypeScript concepts | Supplemental understanding for Playwright users who read JS/TS examples or migrate frameworks |
| Docker | Containerized test execution |
| Visual comparison tools | Screenshot comparison and visual regression workflows |

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

---

## 7. Module 2 - Locators

**Subtopics covered:** Role locators, input locators, text locators, alt text, title, CSS selectors, hierarchy, pseudo-classes, XPath, XPath functions, and other locator strategies.

```python
from playwright.sync_api import Page, expect

def test_locator_examples(page: Page):
    page.goto("https://playwright.dev/python/")
    expect(page.get_by_role("heading", name="Playwright")).to_be_visible()
    page.get_by_role("link", name="Docs").click()
    expect(page).to_have_url(lambda url: "docs" in url)
```

```python
def test_css_and_xpath(page: Page):
    page.goto("https://example.com")
    page.locator("main nav a:first-child").click()
    page.locator("xpath=//button[contains(., 'Save')]").click()
```

**Expected result:** Elements are found by accessibility role, text, CSS hierarchy, pseudo-class, or XPath function and then interacted with.

---

## 8. Module 3 - Actions

**Subtopics covered:** Mouse actions, text input, radio buttons, checkboxes, switches, select options, dropdown menus, file upload, and keyboard shortcuts.

```python
from playwright.sync_api import Page, expect

def test_form_actions(page: Page):
    page.goto("https://example.com/form")
    page.get_by_label("First Name").fill("Brian")
    page.get_by_label("Subscribe").check()
    page.get_by_label("Country").select_option("US")
    page.locator("input[type='file']").set_input_files("tests/data/sample.txt")
    page.keyboard.press("Control+S")
    page.get_by_role("button", name="Submit").click()
    expect(page.get_by_text("Form submitted")).to_be_visible()
```

**Expected result:** Text fields are filled, checkbox-style controls are selected, dropdowns change, a file is attached, keyboard shortcuts are sent, and the form is submitted.

---

## 9. Module 4 - Events

**Subtopics covered:** Auto-waiting, navigation waiting, custom waits, event listeners, dialogs, downloads, sync vs. async Playwright.

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
    download_info.value.save_as("downloaded-report.pdf")
```

**Expected result:** Dialogs are handled and downloads are captured safely using Playwright event APIs.

---

## 10. Module 5 - Authentication

**Subtopics covered:** Sign-in concepts, saving authentication state, reusing authentication state, and login problems.

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

**Expected result:** The first script creates `auth_state.json`; the test reuses it and skips repetitive login steps.

---

## 11. Module 6 - Automated Mail Checker

**Subtopics covered:** Project setup, locating new emails, locating email data, combining locators, and checking email data from terminal execution.

```python
from playwright.sync_api import Page, expect

def test_locate_email(page: Page):
    page.goto("https://example-mail-app.test/inbox")
    email = page.locator(".email-row").filter(has_text="Password reset")
    expect(email).to_be_visible()
    expect(email.locator(".subject")).to_contain_text("Password reset")
```

**Expected result:** The test finds the target email row and verifies the subject.

---

## 12. Module 7 - Pytest

**Subtopics covered:** Writing tests, running tests, type hints, test state, fixtures, fixture usage, and fixture scope.

```python
import pytest

@pytest.fixture
def user_data() -> dict:
    return {"username": "brian", "role": "qa"}

def test_user_role(user_data: dict):
    assert user_data["role"] == "qa"
```

**Expected result:** Pytest injects the fixture and reports the test as passed.

```text
1 passed
```

---

## 13. Module 8 - pytest-playwright Plugin

**Subtopics covered:** Installing the plugin, writing Playwright tests with plugin fixtures, Pytest config, running tests, and hooks.

```python
from playwright.sync_api import Page, expect

def test_homepage(page: Page):
    page.goto("https://playwright.dev/python/")
    expect(page).to_have_title(lambda title: "Playwright" in title)
```

```ini
[pytest]
addopts = --browser chromium
```

**Expected result:** The plugin creates the `page` fixture automatically and runs the browser test.

---

## 14. Module 9 - Playwright Tools

**Subtopics covered:** Codegen, inspector, headed mode, slow motion, screenshots, tracing, trace viewer, videos, and reports.

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

**Expected result:** Screenshots, trace files, and generated locator code help debug and author tests.

---

## 15. Module 10 - Web-First Assertions

**Subtopics covered:** Page assertions, element state, text, attributes, input fields, checkboxes, option menu assertions, generic assertions, locator assertions, and soft assertions.

```python
from playwright.sync_api import expect

def test_assertions(page):
    page.goto("https://example.com/settings")
    expect(page).to_have_url(lambda url: "settings" in url)
    expect(page.get_by_role("heading", name="Settings")).to_be_visible()
    expect(page.get_by_label("Email")).to_have_value("user@example.com")
```

```python
import pytest

def test_soft_assertion_style():
    pytest.assume(1 == 1)
    pytest.assume("qa" in "automation qa")
```

**Expected result:** Playwright waits for UI states automatically; soft assertion plugins can collect multiple assertion failures before ending a test.

---

## 16. Module 11 - UI Testing Playground

**Subtopics covered:** Dynamic IDs, class attributes, hidden layers, load delay, Ajax request, click actions, input fields, scrollbars, dynamic tables, text verification, progress bars, visibility, app login, mouse hover, NBSP, and overlapped elements.

```python
from playwright.sync_api import expect

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

**Expected result:** Tests handle dynamic UI behavior without brittle sleeps or unstable IDs.

---

## 17. Module 12 - Playwright Fixtures

**Subtopics covered:** Function scope fixtures, session scope fixtures, browser selection, launch arguments, and context arguments.

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

**Expected result:** Tests receive preconfigured pages without repeating setup logic.

---

## 18. Module 13 - Page Object Model

**Subtopics covered:** POM concept, implementation, usage, Playwright homepage POM, and POM tests.

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
```

**Expected result:** Tests call meaningful methods instead of repeating locator code.

---

## 19. Module 14 - Network Events

**Subtopics covered:** Network events, request inspection, request handling, and response modification.

```python
def test_mock_user_api(page):
    page.route("**/api/user", lambda route: route.fulfill(
        status=200,
        content_type="application/json",
        body='{"name":"Brian","role":"QA"}'
    ))
    page.goto("https://example.com/profile")
```

**Expected result:** The browser receives mocked API data instead of the real backend response.

---

## 20. Module 15 - API Testing

**Subtopics covered:** API calls, request context, query string, CRUD operations, and mock API.

```python
from playwright.sync_api import Playwright

def test_get_post(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://jsonplaceholder.typicode.com")
    response = api.get("/posts/1")
    assert response.ok
    assert response.json()["id"] == 1
    api.dispose()
```

**Expected result:** The API returns post `1`, the response is OK, and the JSON body contains `id == 1`.

---

## 21. Module 16 - Optimization

**Subtopics covered:** Intercept requests, disabling JavaScript, and parallel execution.

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

```bash
pytest -n auto
```

**Expected result:** Nonessential resources are blocked and tests can run in parallel when `pytest-xdist` is installed.

---

## 22. Module 17 - Tips and Tricks

**Subtopics covered:** CLI arguments, debugger, device emulation, JavaScript evaluation, and reports.

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

**Expected result:** JavaScript executes in the browser page and mobile emulation opens the page with a mobile viewport/user-agent profile.

---

## 23. Module 18 - GitHub API

**Subtopics covered:** GitHub API introduction, project setup, token usage, authorized context, writing tests, and running tests.

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

**Expected result:** A valid token returns the authenticated GitHub user; a missing or invalid token returns unauthorized.

---

## 24. Module 19 - Continuous Integration

**Subtopics covered:** GitHub CI introduction, repository setup, writing tests, GitHub Actions, and running automated tests.

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

**Expected result:** GitHub Actions installs dependencies, installs Playwright browsers, runs tests, and marks the workflow pass/fail.

---

## 25. Module 20 - Data-Driven Testing

**Subtopics covered:** Data-driven testing, Pytest parametrization, and running the same test with multiple data rows.

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

**Expected result:** Pytest executes the test three times.

```text
3 passed
```

---

## 26. Module 21 - Behavior-Driven Development

**Subtopics covered:** BDD concepts, project setup, feature files, step definitions, hooks, and Behave execution.

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

**Expected result:** Behave maps feature steps to Python functions and reports the scenario as passed.

---

## 27. Supplemental Module 22 - Playwright vs Cypress

**Why this was added:** The additional table of contents includes Playwright vs Cypress comparison material that was not previously covered.

**What to know:** Playwright and Cypress both automate browsers, but their architecture and strengths differ.

| Topic | Playwright | Cypress |
|---|---|---|
| Browser support | Chromium, Firefox, WebKit | Primarily Chromium-family and Firefox support depending on version/config |
| Multi-tab/multi-context | Strong browser context support | More constrained by Cypress architecture |
| API testing | Built-in request context | Available through Cypress request commands |
| Auto-waiting | Built into actions and assertions | Built into Cypress command chain |
| Language style | Python, TypeScript, JavaScript, Java, .NET | JavaScript / TypeScript |
| Best fit | Cross-browser E2E, API + UI, complex browser flows | Front-end developer workflow, fast component/E2E workflows |

```python
# Playwright-style Python test
from playwright.sync_api import expect

def test_playwright_style(page):
    page.goto("https://example.com")
    expect(page.locator("h1")).to_be_visible()
```

```javascript
// Cypress-style JavaScript comparison
it('checks heading', () => {
  cy.visit('https://example.com')
  cy.get('h1').should('be.visible')
})
```

**Expected result:** Both tests open a page and validate a heading, but the syntax and runtime model differ.

---

## 28. Supplemental Module 23 - Development Environment, Test Application, and JavaScript TypeScript Fundamentals

**Why this was added:** The additional outline includes VS Code, Git, Node.js, cloning a test app, JavaScript fundamentals, and TypeScript vs JavaScript material.

**What to know:** This Python repository does not require JavaScript to write tests, but many Playwright examples online use JavaScript or TypeScript. Understanding basic JS/TS helps users read broader Playwright documentation and compare implementations.

```bash
# Environment checks
python --version
git --version
node --version
code --version

# Clone a test app or automation repo
git clone https://github.com/example/pw-test-app.git
cd pw-test-app
```

```javascript
// JavaScript variables, constants, arrays, objects, and functions
const user = { name: 'Brian', role: 'QA' }
const skills = ['Playwright', 'Pytest', 'API Testing']

function formatUser(profile) {
  return `${profile.name} works in ${profile.role}`
}

console.log(formatUser(user))
console.log(skills.join(', '))
```

```typescript
// TypeScript adds static typing
interface UserProfile {
  name: string
  role: string
}

const user: UserProfile = { name: 'Brian', role: 'QA' }
console.log(user.name)
```

**Expected result:** The environment commands confirm installed tools. JavaScript and TypeScript examples show how variables, arrays, objects, functions, imports/exports, classes, and types relate to Playwright examples written in JS/TS.

---

## 29. Supplemental Module 24 - DOM Terminology and Advanced Locator Architecture

**Why this was added:** The uploaded outline includes DOM terminology, parent/child locators, filters, extracting values, timeouts, and soft assertions as specific topics.

**What to know:** The DOM is the browser's structured representation of HTML. Elements have tags, attributes, IDs, classes, text, parent/child relationships, and sometimes hidden or dynamic state.

```html
<section id="profile" class="card">
  <h2>Profile</h2>
  <button data-testid="save-profile">Save</button>
</section>
```

```python
from playwright.sync_api import expect

def test_dom_and_advanced_locators(page):
    page.set_content('''
      <section id="profile" class="card">
        <h2>Profile</h2>
        <button data-testid="save-profile">Save</button>
      </section>
    ''')

    card = page.locator("section.card").filter(has_text="Profile")
    button = card.get_by_test_id("save-profile")
    expect(button).to_have_text("Save")
```

```python
def test_extract_values(page):
    page.set_content('<input id="email" value="user@example.com"><p class="status">Ready</p>')
    email_value = page.locator("#email").input_value()
    status_text = page.locator(".status").inner_text()
    assert email_value == "user@example.com"
    assert status_text == "Ready"
```

```python
def test_timeout_configuration(page):
    page.set_default_timeout(5000)
    page.set_default_navigation_timeout(10000)
    page.goto("https://example.com")
```

**Expected result:** Tests select elements by DOM structure, parent/child relationships, filtered text, test IDs, extracted values, and explicit timeout settings.

---

## 30. Supplemental Module 25 - Advanced UI Widgets and Complex Interactions

**Why this was added:** The additional outline includes tooltips, web tables, date pickers, sliders, drag-and-drop, iframes, and overlapped elements.

### Tooltip Example

```python
from playwright.sync_api import expect

def test_tooltip(page):
    page.goto("https://example.com/tooltips")
    page.get_by_role("button", name="Help").hover()
    expect(page.get_by_role("tooltip")).to_contain_text("Helpful information")
```

**Expected result:** Hovering displays the tooltip and the assertion validates the tooltip text.

### Web Table Example

```python
def test_table_row_by_column(page):
    page.goto("https://example.com/users")
    row = page.get_by_role("row").filter(has_text="brian@example.com")
    expect(row).to_contain_text("Active")
    row.get_by_role("button", name="Edit").click()
```

**Expected result:** The test finds the correct table row by known column text and interacts with a button inside that row.

### Date Picker Example

```python
from datetime import date, timedelta

def test_date_picker(page):
    future_date = date.today() + timedelta(days=7)
    page.goto("https://example.com/date-picker")
    page.get_by_label("Date").click()
    page.get_by_text(str(future_date.day), exact=True).click()
    expect(page.get_by_label("Date")).not_to_have_value("")
```

**Expected result:** The test selects a future day and confirms the input has a selected value.

### Slider Example

```python
def test_slider(page):
    page.goto("https://example.com/slider")
    slider = page.locator("input[type='range']")
    slider.evaluate("element => element.value = 75")
    slider.dispatch_event("input")
    assert slider.input_value() == "75"
```

**Expected result:** JavaScript evaluation changes the slider value and dispatches the input event.

### iFrame and Drag-and-Drop Example

```python
def test_iframe_drag_drop(page):
    page.goto("https://example.com/iframe-dragdrop")
    frame = page.frame_locator("iframe[name='demo-frame']")
    source = frame.locator("#source")
    target = frame.locator("#target")
    source.drag_to(target)
```

**Expected result:** Playwright switches into the iframe with `frame_locator()` and performs drag-and-drop inside the frame.

---

## 31. Supplemental Module 26 - Advanced Page Object Architecture

**Why this was added:** The additional outline includes page object manager, helper base class, private helper methods, parametrized methods, and final framework architecture.

**What to know:** Basic POM centralizes one page. Advanced POM architecture adds shared helpers and a page manager that initializes all page objects in one place.

```python
from playwright.sync_api import Page, expect

class BasePage:
    def __init__(self, page: Page):
        self.page = page

    def open(self, path: str):
        self.page.goto(f"https://example.com{path}")

    def expect_heading(self, name: str):
        expect(self.page.get_by_role("heading", name=name)).to_be_visible()

class NavigationPage(BasePage):
    def open_menu_item(self, menu: str, item: str):
        menu_button = self.page.get_by_role("button", name=menu)
        if menu_button.get_attribute("aria-expanded") != "true":
            menu_button.click()
        self.page.get_by_role("link", name=item).click()

class DatePickerPage(BasePage):
    def select_day(self, day: int):
        self.page.get_by_text(str(day), exact=True).click()

class PageManager:
    def __init__(self, page: Page):
        self.navigation = NavigationPage(page)
        self.date_picker = DatePickerPage(page)
```

```python
def test_page_manager(page):
    app = PageManager(page)
    app.navigation.open("/")
    app.navigation.open_menu_item("Forms", "Date Picker")
    app.date_picker.select_day(15)
```

**Expected result:** Tests use high-level objects instead of directly managing every page class or locator.

---

## 32. Supplemental Module 27 - Advanced API State, Mocking, Authentication, and Cleanup

**Why this was added:** The outline includes API mock, response modification, API preconditions, API authentication, sharing auth state, and cleanup using intercepted browser responses.

### API Authentication Precondition

```python
import json
from playwright.sync_api import Playwright

def create_auth_state_with_api(playwright: Playwright):
    api = playwright.request.new_context(base_url="https://example.com")
    token_response = api.post("/api/login", data={"email": "user@example.com", "password": "password"})
    token = token_response.json()["token"]

    with open("auth_token.json", "w") as file:
        json.dump({"token": token}, file)

    api.dispose()
```

**Expected result:** The API login returns a token and stores it in a JSON file that later tests can use.

### Create Precondition with API, Validate with UI

```python
def test_create_article_api_then_delete_ui(playwright, page):
    api = playwright.request.new_context(base_url="https://example.com/api")
    created = api.post("/articles", data={"title": "Playwright API Setup"})
    article_id = created.json()["id"]

    page.goto(f"https://example.com/articles/{article_id}")
    page.get_by_role("button", name="Delete").click()

    api.dispose()
```

**Expected result:** Test data is created quickly through the API and then exercised through the UI.

### Intercept Browser Response and Clean Up with API

```python
def test_ui_create_then_api_cleanup(page, playwright):
    with page.expect_response("**/api/articles") as response_info:
        page.goto("https://example.com/articles/new")
        page.get_by_label("Title").fill("Temporary Article")
        page.get_by_role("button", name="Save").click()

    article_id = response_info.value.json()["id"]
    api = playwright.request.new_context(base_url="https://example.com/api")
    api.delete(f"/articles/{article_id}")
    api.dispose()
```

**Expected result:** The UI creates data, the test captures the created ID from the browser API response, and the API deletes the data during cleanup.

---

## 33. Supplemental Module 28 - Advanced Framework Configuration, Environment Variables, Retries, Tags, and Test Data

**Why this was added:** The outline includes custom scripts, Faker data generation, retries, parallelism, environment variables, configuration files, custom fixtures, project setup/teardown, global setup/teardown, and tags.

### Environment Variables with `.env`

```python
import os
from dotenv import load_dotenv

load_dotenv()
BASE_URL = os.getenv("BASE_URL", "https://example.com")
TEST_USER = os.getenv("TEST_USER")
```

**Expected result:** Values can be configured without hard-coding secrets or URLs.

### Faker Test Data

```python
from faker import Faker

fake = Faker()

def test_generated_user_data():
    email = fake.email()
    username = fake.user_name()
    assert "@" in email
    assert len(username) > 0
```

**Expected result:** Each run can create unique data and reduce collisions in test environments.

### Retries and Tags in Pytest

```ini
# pytest.ini
[pytest]
markers =
    smoke: critical smoke tests
    regression: broader regression tests
addopts = --maxfail=1
```

```python
import pytest

@pytest.mark.smoke
def test_smoke_login():
    assert True
```

```bash
pytest -m smoke
pytest --reruns 2
pytest -n 2
```

**Expected result:** Tests can be filtered by marker, retried when configured with retry plugins, and distributed across workers when `pytest-xdist` is installed.

### Global Setup/Teardown Style Fixture

```python
import pytest

@pytest.fixture(scope="session", autouse=True)
def global_test_setup():
    print("Starting automation suite")
    yield
    print("Ending automation suite")
```

**Expected result:** Setup runs before the test session and teardown runs after all tests finish.

---

## 34. Supplemental Module 29 - Reporting, Screenshots, Videos, and Visual Testing

**Why this was added:** The outline includes screenshots, videos, reporting, built-in visual testing, component visual checks, accuracy adjustment, snapshot updates, and third-party reports.

### Screenshot and Buffer Example

```python
def test_page_and_element_screenshot(page):
    page.goto("https://example.com")
    page.screenshot(path="artifacts/page.png", full_page=True)
    logo = page.locator("img").first
    image_bytes = logo.screenshot()
    assert len(image_bytes) > 0
```

**Expected result:** A full-page screenshot is saved, and an element screenshot is stored in memory as bytes.

### Video Recording Context

```python
def test_video_recording(browser):
    context = browser.new_context(record_video_dir="videos/", record_video_size={"width": 1280, "height": 720})
    page = context.new_page()
    page.goto("https://example.com")
    context.close()
```

**Expected result:** Playwright records a video for the browser context and saves it after context close.

### Visual Snapshot Testing

```python
from playwright.sync_api import expect

def test_visual_snapshot(page):
    page.goto("https://example.com")
    expect(page).to_have_screenshot("home-page.png", max_diff_pixel_ratio=0.01)
```

```bash
pytest --update-snapshots
```

**Expected result:** Playwright compares the current screenshot to the baseline image. The update command refreshes baseline snapshots when UI changes are intentional.

### Reporting Commands

```bash
pytest --junitxml=reports/junit.xml
pytest --html=reports/report.html
allure generate allure-results -o allure-report --clean
```

**Expected result:** Test results are exported for CI dashboards, HTML reports, or Allure reporting.

---

## 35. Supplemental Module 30 - Docker, GitHub Actions, and Argos CI

**Why this was added:** The outline includes running Playwright in Docker, Dockerfile, docker-compose, saving reports from a container, GitHub Actions for pull requests, and Argos CI visual validation.

### Dockerfile Example

```dockerfile
FROM mcr.microsoft.com/playwright/python:v1.45.0-jammy

WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["pytest", "--junitxml=reports/junit.xml"]
```

**Expected result:** The container has browser dependencies and runs the Pytest suite inside a consistent environment.

### docker-compose Example

```yaml
services:
  tests:
    build: .
    volumes:
      - ./reports:/app/reports
    environment:
      - BASE_URL=https://example.com
```

```bash
docker compose up --build
```

**Expected result:** Tests run in the container and reports are saved back to the host `reports` folder.

### GitHub Actions with Visual Report Upload

```yaml
name: Playwright Tests

on:
  pull_request:
  push:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt
      - run: playwright install --with-deps
      - run: pytest --junitxml=reports/junit.xml
      - uses: actions/upload-artifact@v4
        with:
          name: playwright-reports
          path: reports/
```

**Expected result:** Every push or pull request runs the tests and stores report artifacts.

### Argos CI Concept

```bash
# Conceptual example for visual validation workflow
npx argos upload screenshots
```

**Expected result:** Screenshots are uploaded to a visual review service for baseline comparison and pull-request validation.

---

## 36. Playwright Automation Top 20 Interview Questions and Answers

### 1. What is Playwright?

Playwright is an end-to-end automation framework for testing web applications across Chromium, Firefox, and WebKit. It supports browser automation, UI testing, API testing, tracing, screenshots, videos, network interception, and multiple languages including Python.

### 2. Why use Playwright instead of Selenium?

Playwright has built-in auto-waiting, modern locator strategies, browser contexts for isolation, native network interception, trace viewer, API testing support, and strong handling for modern single-page applications.

### 3. What is a browser context?

A browser context is an isolated browser session. Each context has its own cookies, local storage, session storage, permissions, and viewport.

### 4. What is the difference between `browser`, `context`, and `page`?

`browser` is the launched browser process. `context` is an isolated session inside the browser. `page` is a browser tab inside a context.

### 5. What are Playwright locators?

Locators are Playwright objects used to find and interact with elements. They auto-wait and re-query the DOM.

### 6. Which locator strategy is preferred?

Prefer user-facing and accessibility-based locators such as `get_by_role`, `get_by_label`, `get_by_text`, and `get_by_placeholder`.

### 7. What is auto-waiting?

Auto-waiting means Playwright waits for elements to be actionable before performing actions.

### 8. What are web-first assertions?

Web-first assertions automatically wait until an expected condition is met or a timeout occurs.

### 9. How do you handle alerts or dialogs?

Use the `dialog` event with `page.on("dialog", handler)`.

### 10. How do you handle downloads?

Wrap the download-triggering action with `page.expect_download()`.

### 11. How do you save authentication state?

After login, call `context.storage_state(path="auth_state.json")` and reuse the file in future contexts.

### 12. What is Page Object Model?

POM is a design pattern that stores locators and page behavior inside page classes.

### 13. How does Pytest integrate with Playwright?

Pytest runs the tests, while Playwright controls browser behavior. `pytest-playwright` provides browser fixtures.

### 14. What is a Pytest fixture?

A fixture is reusable setup/teardown logic used by tests.

### 15. How do you perform API testing in Playwright?

Use `playwright.request.new_context()` to create an API client.

### 16. How do you intercept network requests?

Use `page.route()` to continue, abort, or fulfill matching requests.

### 17. How do you mock an API response?

Use `route.fulfill()` to provide a custom response.

### 18. How do you run Playwright tests in CI?

Install dependencies, install Playwright browsers, and run Pytest inside the CI workflow.

### 19. How do you debug flaky Playwright tests?

Use headed mode, slow motion, screenshots, videos, traces, console logs, network logs, and web-first assertions.

### 20. What is data-driven testing?

Data-driven testing runs the same test logic with multiple input values and expected results.

---

## 37. Best Practices and Troubleshooting

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

## 38. Author

**Brian McCarthy**  
Playwright Automation with Python and Pytest Showcase
