# Playwright Automation with Python and Pytest Showcase

**Written by Brian McCarthy**

A complete hands-on Playwright automation guide using **Python**, **Pytest**, `pytest-playwright`, Page Object Model design, fixtures, web-first assertions, API testing, network interception, login testing, CI/CD execution, data-driven testing, behavior-driven development, Docker, visual testing, and framework architecture.

This README is organized as a numbered tutorial. Each module explains the main purpose, what the user needs to know, code examples, and expected results. Supplemental modules add framework-building guidance, framework-selection guidance, advanced CI/CD, API testing, and login testing material.

---

## Table of Contents

| Section / Module | Contents Covered |
|---|---|
| [1. Project Overview](#1-project-overview) | Explains the purpose of the repository and the Playwright/Python/Pytest automation topics covered. |
| [2. Repository Goals](#2-repository-goals) | Lists the portfolio and learning objectives for UI automation, API testing, fixtures, POM, CI/CD, login testing, and framework design. |
| [3. Languages, Tools, and Frameworks](#3-languages-tools-and-frameworks) | Summarizes Python, Playwright, Pytest, pytest-playwright, Behave, GitHub API, GitHub Actions, Docker, visual tools, and JavaScript/TypeScript concepts. |
| [4. Project File Links](#4-project-file-links) | Links to the repository’s S01-S21 sections and describes each folder’s main focus. |
| [5. Core Commands](#5-core-commands) | Provides setup and execution commands for dependencies, browsers, Pytest, tracing, and Behave. |
| [6. Module 1 - Getting Started](#6-module-1---getting-started) | Covers installation, browser launch, first navigation, link clicking, and basic script structure. |
| [7. Module 2 - Locators](#7-module-2---locators) | Covers role, input, text, alt text, title, CSS, hierarchy, pseudo-class, XPath, test ID, and filtering locator strategies. |
| [8. Module 3 - Actions](#8-module-3---actions) | Covers mouse actions, keyboard actions, text input, radio buttons, checkboxes, switches, select options, dropdowns, and uploads. |
| [9. Module 4 - Events](#9-module-4---events) | Covers auto-waiting, navigation waits, event listeners, dialogs, downloads, popups, and sync/async usage. |
| [10. Module 5 - Authentication](#10-module-5---authentication) | Covers login flows, saved storage state, auth reuse, edge cases, MFA limitations, and credential handling. |
| [11. Module 6 - Automated Mail Checker](#11-module-6---automated-mail-checker) | Covers mailbox automation, locating new emails, extracting sender/subject/body data, and terminal checks. |
| [12. Module 7 - Pytest](#12-module-7---pytest) | Covers writing/running tests, type hints, test state, fixtures, fixture usage, fixture scope, and assertions. |
| [13. Module 8 - pytest-playwright Plugin](#13-module-8---pytest-playwright-plugin) | Covers plugin setup, `page`/`browser` fixtures, Pytest config, hooks, and browser CLI options. |
| [14. Module 9 - Playwright Tools](#14-module-9---playwright-tools) | Covers codegen, inspector, headed mode, slow motion, screenshots, traces, videos, and debugging. |
| [15. Module 10 - Web-First Assertions](#15-module-10---web-first-assertions) | Covers page, element, text, attribute, input, checkbox, option menu, generic assertion, and soft assertion patterns. |
| [16. Module 11 - UI Testing Playground](#16-module-11---ui-testing-playground) | Covers dynamic IDs, hidden layers, Ajax, dynamic tables, progress bars, visibility, hover, NBSP, and overlays. |
| [17. Module 12 - Playwright Fixtures](#17-module-12---playwright-fixtures) | Covers function/session fixtures, browser selection, launch args, context args, and reusable setup. |
| [18. Module 13 - Page Object Model](#18-module-13---page-object-model) | Covers POM design, reusable page classes, locator encapsulation, page methods, and readable tests. |
| [19. Module 14 - Network Events](#19-module-14---network-events) | Covers request/response inspection, routing, interception, mocked responses, blocking resources, and response modification. |
| [20. Module 15 - API Testing](#20-module-15---api-testing) | Covers API request contexts, GET/POST/PUT/PATCH/DELETE, query strings, response assertions, auth headers, and cleanup. |
| [21. Module 16 - Optimization](#21-module-16---optimization) | Covers blocking images/fonts, disabling JavaScript, parallel execution, selective runs, and performance-friendly patterns. |
| [22. Module 17 - Tips and Tricks](#22-module-17---tips-and-tricks) | Covers CLI args, debugger usage, device emulation, JavaScript evaluation, reports, and local debugging. |
| [23. Module 18 - GitHub API](#23-module-18---github-api) | Covers GitHub API testing, token usage, authorized request contexts, public repo metadata, and environment variables. |
| [24. Module 19 - Continuous Integration](#24-module-19---continuous-integration) | Covers GitHub Actions setup, browser installation, CI-safe execution, artifacts, reports, and PR validation. |
| [25. Module 20 - Data-Driven Testing](#25-module-20---data-driven-testing) | Covers Pytest parametrization, multiple input rows, expected results, and coverage expansion. |
| [26. Module 21 - Behavior-Driven Development](#26-module-21---behavior-driven-development) | Covers Behave, Gherkin feature files, Given/When/Then steps, hooks, and scenario execution. |
| [27. Supplemental Module 22 - Playwright vs Cypress](#27-supplemental-module-22---playwright-vs-cypress) | Compares Playwright and Cypress architecture, browser support, API testing, locator style, and best-fit scenarios. |
| [28. Supplemental Module 23 - Development Environment, Test Application, and JavaScript TypeScript Fundamentals](#28-supplemental-module-23---development-environment-test-application-and-javascript-typescript-fundamentals) | Covers environment checks, VS Code/Git/Node/Python setup, JavaScript basics, and TypeScript concepts. |
| [29. Supplemental Module 24 - DOM Terminology and Advanced Locator Architecture](#29-supplemental-module-24---dom-terminology-and-advanced-locator-architecture) | Covers DOM structure, attributes, IDs, classes, parent/child locators, filters, extracted values, test IDs, and timeouts. |
| [30. Supplemental Module 25 - Advanced UI Widgets and Complex Interactions](#30-supplemental-module-25---advanced-ui-widgets-and-complex-interactions) | Covers tooltips, tables, date pickers, sliders, iframes, drag-and-drop, and overlapped elements. |
| [31. Supplemental Module 26 - Advanced Page Object Architecture](#31-supplemental-module-26---advanced-page-object-architecture) | Covers base pages, helper methods, page managers, reusable components, and scalable framework architecture. |
| [32. Supplemental Module 27 - Advanced API State, Mocking, Authentication, and Cleanup](#32-supplemental-module-27---advanced-api-state-mocking-authentication-and-cleanup) | Covers API preconditions, UI/API hybrid flows, API login, mocked state, browser response capture, and teardown cleanup. |
| [33. Supplemental Module 28 - Advanced Framework Configuration, Environment Variables, Retries, Tags, and Test Data](#33-supplemental-module-28---advanced-framework-configuration-environment-variables-retries-tags-and-test-data) | Covers `.env`, Faker, Pytest markers, retries, parallel workers, global setup/teardown, and test data strategy. |
| [34. Supplemental Module 29 - Reporting, Screenshots, Videos, and Visual Testing](#34-supplemental-module-29---reporting-screenshots-videos-and-visual-testing) | Covers screenshots, element screenshots, videos, snapshot testing, report export, Allure-style reports, and visual diffing. |
| [35. Supplemental Module 30 - Docker, GitHub Actions, and Argos CI](#35-supplemental-module-30---docker-github-actions-and-argos-ci) | Covers Dockerfile setup, docker-compose, report volume mapping, GitHub Actions artifacts, and Argos visual validation. |
| [36. Supplemental Module 31 - Building a Playwright Framework from Scratch](#36-supplemental-module-31---building-a-playwright-framework-from-scratch) | Explains when to build a custom framework, required files, required dependencies, folder structure, setup steps, and starter code. |
| [37. Supplemental Module 32 - Custom Framework vs Out-of-the-Box Framework](#37-supplemental-module-32---custom-framework-vs-out-of-the-box-framework) | Explains when a custom framework is worth it and when to use popular existing Playwright tooling or templates. |
| [38. Supplemental Module 33 - Best and Popular Playwright Framework Options by Scenario](#38-supplemental-module-33---best-and-popular-playwright-framework-options-by-scenario) | Describes recommended Playwright framework approaches for UI testing, API testing, BDD, visual testing, CI, Docker, enterprise use, and quick projects. |
| [39. Supplemental Module 34 - Thorough CI/CD Strategy for Playwright](#39-supplemental-module-34---thorough-cicd-strategy-for-playwright) | Adds detailed CI/CD pipeline stages, artifacts, secrets, browser install, matrix runs, quality gates, and GitHub Actions examples. |
| [40. Supplemental Module 35 - Thorough API Testing Strategy](#40-supplemental-module-35---thorough-api-testing-strategy) | Adds detailed API testing design, request clients, fixtures, schemas, auth headers, CRUD tests, cleanup, negative tests, and expected results. |
| [41. Supplemental Module 36 - Thorough Login Testing Strategy](#41-supplemental-module-36---thorough-login-testing-strategy) | Adds login test coverage for valid login, invalid login, locked users, session reuse, storage state, logout, MFA notes, and secure credentials. |
| [42. Playwright Automation Top 20 Interview Questions and Answers](#42-playwright-automation-top-20-interview-questions-and-answers) | Provides top Playwright interview Q&A covering framework concepts, contexts, locators, auto-waiting, assertions, POM, API testing, network mocking, CI, and debugging. |
| [43. Best Practices and Troubleshooting](#43-best-practices-and-troubleshooting) | Summarizes Playwright best practices and fixes for missing browsers, flaky locators, login failures, 401s, downloads, and CI differences. |
| [44. Author](#44-author) | Lists author credit for Brian McCarthy and the Playwright automation showcase. |

---

## 1. Project Overview

This repository demonstrates browser automation and test engineering with Playwright for Python. It starts with installation and browser launch scripts, then progresses into locators, actions, event handling, authentication, automated email checking, Pytest, plugin fixtures, Playwright debugging tools, web-first assertions, UI challenge automation, custom fixtures, Page Object Model, network events, API testing, performance optimization, GitHub API automation, CI/CD, data-driven testing, BDD, Docker, and visual validation.

The repository is designed as a practical learning and portfolio project. It shows that the author can create reliable UI tests, API tests, login tests, reusable fixtures, maintainable page objects, CI-ready automation, Docker-compatible runs, and scalable framework patterns.

---

## 2. Repository Goals

1. Demonstrate Playwright automation in Python.
2. Show reliable locator strategies for modern web apps.
3. Use realistic user actions: clicks, text input, file upload, dropdowns, keyboard shortcuts, hover, and drag-and-drop.
4. Handle auto-waiting, navigation, dialogs, downloads, asynchronous operations, and events.
5. Save and reuse authentication state.
6. Build Pytest test cases with fixtures and scoped setup.
7. Use `pytest-playwright` fixtures such as `page`, `context`, and `browser`.
8. Apply web-first assertions to reduce flaky test behavior.
9. Organize UI automation with Page Object Model.
10. Test APIs with Playwright request contexts.
11. Mock and intercept network requests.
12. Improve runtime with optimization patterns.
13. Run tests in CI/CD using GitHub Actions.
14. Expand coverage using data-driven and BDD techniques.
15. Build or evaluate custom Playwright framework architecture.
16. Add supplemental coverage for environment setup, JavaScript/TypeScript fundamentals, advanced widgets, reporting, Docker, and visual validation.

---

## 3. Languages, Tools, and Frameworks

| Tool / Language | Purpose |
|---|---|
| Python | Main automation language |
| Playwright for Python | Browser automation, UI assertions, event handling, API request contexts, tracing, screenshots, and network mocking |
| Pytest | Test discovery, test execution, fixtures, parametrization, and reporting |
| pytest-playwright | Plugin-provided browser/page/context fixtures and command-line browser options |
| Behave | BDD feature files and Given/When/Then step definitions |
| Faker | Test data generation |
| python-dotenv | Environment configuration from `.env` files |
| pytest-xdist | Parallel test execution |
| pytest-rerunfailures | Controlled retry behavior for unstable external dependencies |
| GitHub API | Authenticated API automation practice |
| GitHub Actions | Continuous integration and delivery execution |
| Docker | Containerized test execution |
| Visual comparison tools | Screenshot comparison and visual regression workflows |
| JavaScript / TypeScript concepts | Supplemental understanding for users who read JS/TS Playwright examples or migrate frameworks |

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
pip install pytest playwright pytest-playwright behave faker python-dotenv pytest-xdist pytest-rerunfailures
playwright install
pytest
pytest --headed
pytest --browser chromium
pytest path/to/test_file.py
pytest -k login
pytest -m smoke
pytest -n auto
pytest --tracing on
playwright show-trace trace.zip
behave
```

**Expected result:** Dependencies install, Playwright browsers are downloaded, Pytest/Behave discover tests, and pass/fail results are printed in the terminal.

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

**Expected result:** Playwright waits for UI states automatically and fails only if expected conditions are not met within timeout.

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
from playwright.sync_api import Page

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

**Expected result:** Tests call meaningful page methods instead of repeating locator code.

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

**Why this was added:** Playwright and Cypress are both popular browser automation tools, but they fit different scenarios.

| Topic | Playwright | Cypress |
|---|---|---|
| Browser support | Chromium, Firefox, WebKit | Best known for Chromium-family browsers; Firefox support also exists |
| Multi-context support | Strong isolated browser contexts | More constrained architecture |
| Language ecosystem | Python, TypeScript, JavaScript, Java, .NET | JavaScript and TypeScript |
| API testing | Built-in request context | `cy.request()` |
| Best fit | Cross-browser E2E, UI + API, complex auth, network mocking | Front-end developer workflow and JS/TS app testing |

```python
from playwright.sync_api import expect

def test_playwright_style(page):
    page.goto("https://example.com")
    expect(page.locator("h1")).to_be_visible()
```

```javascript
it('checks heading', () => {
  cy.visit('https://example.com')
  cy.get('h1').should('be.visible')
})
```

**Expected result:** Both tests validate a heading, but Playwright and Cypress use different runtime models and syntax.

---

## 28. Supplemental Module 23 - Development Environment, Test Application, and JavaScript TypeScript Fundamentals

```bash
python --version
git --version
node --version
code --version
```

```javascript
const user = { name: 'Brian', role: 'QA' }
const skills = ['Playwright', 'Pytest', 'API Testing']
function formatUser(profile) {
  return `${profile.name} works in ${profile.role}`
}
console.log(formatUser(user))
console.log(skills.join(', '))
```

```typescript
interface UserProfile {
  name: string
  role: string
}
const user: UserProfile = { name: 'Brian', role: 'QA' }
console.log(user.name)
```

**Expected result:** The environment commands confirm installed tools. JavaScript and TypeScript examples help users understand Playwright examples written in JS/TS.

---

## 29. Supplemental Module 24 - DOM Terminology and Advanced Locator Architecture

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
    assert page.locator("#email").input_value() == "user@example.com"
    assert page.locator(".status").inner_text() == "Ready"
```

**Expected result:** Tests select elements by DOM structure, parent/child relationships, filtered text, test IDs, and extracted values.

---

## 30. Supplemental Module 25 - Advanced UI Widgets and Complex Interactions

```python
from playwright.sync_api import expect

def test_tooltip(page):
    page.goto("https://example.com/tooltips")
    page.get_by_role("button", name="Help").hover()
    expect(page.get_by_role("tooltip")).to_contain_text("Helpful information")
```

```python
def test_table_row_by_column(page):
    page.goto("https://example.com/users")
    row = page.get_by_role("row").filter(has_text="brian@example.com")
    expect(row).to_contain_text("Active")
    row.get_by_role("button", name="Edit").click()
```

```python
def test_iframe_drag_drop(page):
    page.goto("https://example.com/iframe-dragdrop")
    frame = page.frame_locator("iframe[name='demo-frame']")
    frame.locator("#source").drag_to(frame.locator("#target"))
```

**Expected result:** The examples demonstrate hover, table-row targeting, iframe handling, and drag-and-drop interactions.

---

## 31. Supplemental Module 26 - Advanced Page Object Architecture

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

class PageManager:
    def __init__(self, page: Page):
        self.navigation = NavigationPage(page)
```

```python
def test_page_manager(page):
    app = PageManager(page)
    app.navigation.open("/")
    app.navigation.open_menu_item("Forms", "Date Picker")
```

**Expected result:** Tests use high-level objects instead of directly managing every page class or locator.

---

## 32. Supplemental Module 27 - Advanced API State, Mocking, Authentication, and Cleanup

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

**Expected result:** API calls create state quickly, UI tests validate user-facing behavior, and cleanup removes generated data.

---

## 33. Supplemental Module 28 - Advanced Framework Configuration, Environment Variables, Retries, Tags, and Test Data

```python
import os
from dotenv import load_dotenv

load_dotenv()
BASE_URL = os.getenv("BASE_URL", "https://example.com")
TEST_USER = os.getenv("TEST_USER")
```

```python
from faker import Faker
fake = Faker()

def test_generated_user_data():
    email = fake.email()
    assert "@" in email
```

```ini
[pytest]
markers =
    smoke: critical smoke tests
    regression: broader regression tests
addopts = --maxfail=1
```

```bash
pytest -m smoke
pytest --reruns 2
pytest -n 2
```

**Expected result:** Tests can use environment-specific configuration, generated test data, filtered test execution, retries, and parallel workers.

---

## 34. Supplemental Module 29 - Reporting, Screenshots, Videos, and Visual Testing

```python
def test_page_and_element_screenshot(page):
    page.goto("https://example.com")
    page.screenshot(path="artifacts/page.png", full_page=True)
    image_bytes = page.locator("img").first.screenshot()
    assert len(image_bytes) > 0
```

```python
def test_video_recording(browser):
    context = browser.new_context(record_video_dir="videos/", record_video_size={"width": 1280, "height": 720})
    page = context.new_page()
    page.goto("https://example.com")
    context.close()
```

```python
from playwright.sync_api import expect

def test_visual_snapshot(page):
    page.goto("https://example.com")
    expect(page).to_have_screenshot("home-page.png", max_diff_pixel_ratio=0.01)
```

```bash
pytest --junitxml=reports/junit.xml
pytest --html=reports/report.html
pytest --update-snapshots
```

**Expected result:** Screenshots, videos, visual baselines, and machine-readable reports are produced for debugging and CI evidence.

---

## 35. Supplemental Module 30 - Docker, GitHub Actions, and Argos CI

```dockerfile
FROM mcr.microsoft.com/playwright/python:v1.45.0-jammy
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["pytest", "--junitxml=reports/junit.xml"]
```

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
npx argos upload screenshots
```

**Expected result:** Tests run in a consistent container, reports are mapped back to the host, and visual screenshots can be uploaded to a visual validation service.

---

## 36. Supplemental Module 31 - Building a Playwright Framework from Scratch

A Playwright framework is needed when a team wants reusable structure beyond one-off scripts. A good framework standardizes setup, browser configuration, fixtures, page objects, test data, reporting, CI/CD, retries, artifacts, environment switching, login state, and API helpers.

### When to Build a Custom Framework

Build a custom framework when:

- The test suite will grow beyond a few simple tests.
- Multiple QA engineers or developers will contribute tests.
- The project needs common login, data setup, cleanup, and reporting.
- The team must support multiple environments such as dev, QA, staging, and production smoke checks.
- The app needs Page Object Model or Screenplay-style abstraction.
- Tests must run in CI/CD with artifacts and quality gates.
- API and UI tests need shared fixtures and authentication.

Avoid building a heavy framework when:

- The project only needs a few smoke tests.
- The team is still exploring Playwright basics.
- A generated Playwright/Pytest starter is sufficient.
- Maintenance cost would exceed the value of abstraction.

### Required Files and Folder Structure

```text
playwright-python-framework/
├── README.md
├── requirements.txt
├── pytest.ini
├── .env.example
├── .gitignore
├── conftest.py
├── pages/
│   ├── __init__.py
│   ├── base_page.py
│   ├── login_page.py
│   └── dashboard_page.py
├── tests/
│   ├── ui/
│   │   └── test_login.py
│   ├── api/
│   │   └── test_users_api.py
│   └── smoke/
│       └── test_homepage.py
├── utils/
│   ├── __init__.py
│   ├── config.py
│   ├── data_factory.py
│   └── api_client.py
├── test_data/
│   └── users.json
├── artifacts/
│   ├── screenshots/
│   ├── videos/
│   └── traces/
└── .github/
    └── workflows/
        └── playwright-tests.yml
```

### Requirements File

```text
pytest
playwright
pytest-playwright
python-dotenv
faker
pytest-xdist
pytest-rerunfailures
pytest-html
```

### Step-by-Step Framework Build

1. Create the repository and virtual environment.
2. Install dependencies.
3. Install Playwright browsers.
4. Add `pytest.ini` for markers and default options.
5. Add `.env.example` for environment variables.
6. Create `utils/config.py` for environment configuration.
7. Create `conftest.py` for fixtures.
8. Create `pages/base_page.py` for shared page methods.
9. Create page objects for each major application screen.
10. Create UI tests under `tests/ui/`.
11. Create API tests under `tests/api/`.
12. Add screenshots, traces, and videos for failure evidence.
13. Add smoke/regression markers.
14. Add GitHub Actions workflow.
15. Add README instructions for setup and execution.

### `pytest.ini`

```ini
[pytest]
addopts = -ra --browser chromium --tracing retain-on-failure
markers =
    smoke: critical smoke tests
    regression: full regression tests
    login: login and authentication tests
    api: API tests
    ui: UI tests
```

### `.env.example`

```text
BASE_URL=https://example.com
API_BASE_URL=https://example.com/api
TEST_USER_EMAIL=user@example.com
TEST_USER_PASSWORD=password
GITHUB_TOKEN=replace_me
```

### `utils/config.py`

```python
import os
from dotenv import load_dotenv

load_dotenv()

class Settings:
    BASE_URL = os.getenv("BASE_URL", "https://example.com")
    API_BASE_URL = os.getenv("API_BASE_URL", "https://example.com/api")
    TEST_USER_EMAIL = os.getenv("TEST_USER_EMAIL", "user@example.com")
    TEST_USER_PASSWORD = os.getenv("TEST_USER_PASSWORD", "password")

settings = Settings()
```

### `conftest.py`

```python
import pytest
from utils.config import settings

@pytest.fixture(scope="session")
def base_url():
    return settings.BASE_URL

@pytest.fixture
def authenticated_page(page):
    page.goto(f"{settings.BASE_URL}/login")
    page.get_by_label("Email").fill(settings.TEST_USER_EMAIL)
    page.get_by_label("Password").fill(settings.TEST_USER_PASSWORD)
    page.get_by_role("button", name="Sign in").click()
    return page

@pytest.fixture(scope="session")
def api_base_url():
    return settings.API_BASE_URL
```

### `pages/base_page.py`

```python
from playwright.sync_api import Page, expect

class BasePage:
    def __init__(self, page: Page):
        self.page = page

    def open(self, path: str = ""):
        self.page.goto(path)

    def expect_title_contains(self, text: str):
        expect(self.page).to_have_title(lambda title: text in title)

    def click_by_role(self, role: str, name: str):
        self.page.get_by_role(role, name=name).click()
```

### `pages/login_page.py`

```python
from playwright.sync_api import Page, expect
from pages.base_page import BasePage

class LoginPage(BasePage):
    def __init__(self, page: Page):
        super().__init__(page)
        self.email = page.get_by_label("Email")
        self.password = page.get_by_label("Password")
        self.submit = page.get_by_role("button", name="Sign in")
        self.error = page.get_by_role("alert")

    def open_login(self, base_url: str):
        self.page.goto(f"{base_url}/login")

    def login(self, email: str, password: str):
        self.email.fill(email)
        self.password.fill(password)
        self.submit.click()

    def expect_error(self, message: str):
        expect(self.error).to_contain_text(message)
```

### `tests/ui/test_login.py`

```python
import pytest
from pages.login_page import LoginPage
from utils.config import settings

@pytest.mark.login
@pytest.mark.ui
def test_valid_login(page, base_url):
    login = LoginPage(page)
    login.open_login(base_url)
    login.login(settings.TEST_USER_EMAIL, settings.TEST_USER_PASSWORD)
    assert "dashboard" in page.url

@pytest.mark.login
@pytest.mark.ui
def test_invalid_login(page, base_url):
    login = LoginPage(page)
    login.open_login(base_url)
    login.login("bad@example.com", "wrong")
    login.expect_error("Invalid")
```

**Expected result:** The framework can run UI tests, API tests, login tests, smoke tests, and regression tests consistently locally and in CI/CD.

---

## 37. Supplemental Module 32 - Custom Framework vs Out-of-the-Box Framework

### Use a Custom Framework When

| Scenario | Why Custom Helps |
|---|---|
| Large enterprise app | Requires shared patterns, environment switching, custom reporting, and test data management |
| Complex login/auth | Needs storage state, API auth, multiple roles, and secure secret handling |
| UI + API hybrid tests | Needs API setup/cleanup combined with UI validation |
| Regulated QA evidence | Needs artifacts, traces, screenshots, reports, and repeatable evidence |
| Multiple teams | Needs standardized POM, naming conventions, tags, and fixtures |

### Use Out-of-the-Box Tooling When

| Scenario | Better Option |
|---|---|
| Small smoke suite | `pytest-playwright` defaults are enough |
| Learning Playwright | Simple scripts or generated code are faster |
| Front-end JS/TS team | Official Playwright Test runner in TypeScript may be more natural |
| BDD collaboration | Behave + Playwright or Playwright-BDD style framework |
| Visual regression focus | Playwright screenshots + Argos, Percy, or Applitools |

### Decision Rule

Use the simplest framework that supports the real requirement. A custom framework should solve repeated problems, not create unnecessary abstraction.

---

## 38. Supplemental Module 33 - Best and Popular Playwright Framework Options by Scenario

| Scenario | Recommended Framework / Approach | Why |
|---|---|---|
| Python UI testing | `pytest-playwright` | Best fit for Python teams using Pytest fixtures and assertions |
| TypeScript/JavaScript UI testing | Official Playwright Test | Most feature-complete Playwright runner, strong config/projects/reporting support |
| API testing in Python | Playwright `APIRequestContext` + Pytest | Fast backend validation with shared fixtures |
| BDD in Python | Behave + Playwright | Good for Given/When/Then collaboration and readable acceptance tests |
| BDD in TypeScript | Playwright-BDD / Cucumber-style approach | Good for JS/TS teams needing Gherkin |
| Visual testing | Playwright screenshots + Argos/Percy/Applitools | Best for detecting UI regressions through screenshots |
| Enterprise smoke/regression | Custom Pytest framework + POM + CI/CD | Supports tagging, environment control, artifacts, and standard test patterns |
| Fast PR validation | Official Playwright Test or Pytest markers | Run only smoke/high-risk tests on pull requests |
| Dockerized automation | Playwright Docker image | Consistent browser dependencies and reproducible runs |
| Cross-browser validation | Playwright projects or Pytest browser matrix | Validate Chromium, Firefox, and WebKit behavior |

### Popular Framework Choices

1. **Official Playwright Test for TypeScript/JavaScript**: Best all-around Playwright-native test runner.
2. **pytest-playwright for Python**: Best for Python QA automation teams and Pytest-based test suites.
3. **Behave + Playwright Python**: Best when stakeholders want Gherkin scenarios.
4. **Playwright + Page Object Model**: Best maintainability pattern for medium/large UI suites.
5. **Playwright + APIRequestContext**: Best for API + UI hybrid automation.
6. **Playwright + Docker + GitHub Actions**: Best for reproducible CI execution.
7. **Playwright + Argos/Percy/Applitools**: Best for visual regression workflows.

---

## 39. Supplemental Module 34 - Thorough CI/CD Strategy for Playwright

A strong CI/CD pipeline makes Playwright tests repeatable, observable, and useful as a quality gate.

### Recommended CI/CD Stages

1. **Checkout source code**.
2. **Set up Python**.
3. **Install Python dependencies**.
4. **Install Playwright browsers and OS dependencies**.
5. **Run linting or formatting checks**.
6. **Run smoke tests first**.
7. **Run regression tests or browser matrix if needed**.
8. **Upload artifacts: traces, screenshots, videos, reports**.
9. **Publish test results**.
10. **Fail the workflow when critical tests fail**.

### GitHub Actions Workflow

```yaml
name: Playwright Python CI

on:
  pull_request:
  push:
    branches: [ main ]

jobs:
  smoke:
    runs-on: ubuntu-latest
    env:
      BASE_URL: ${{ secrets.BASE_URL }}
      TEST_USER_EMAIL: ${{ secrets.TEST_USER_EMAIL }}
      TEST_USER_PASSWORD: ${{ secrets.TEST_USER_PASSWORD }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt
      - run: playwright install --with-deps
      - run: pytest -m smoke --tracing retain-on-failure --junitxml=reports/smoke-results.xml
      - uses: actions/upload-artifact@v4
        if: always()
        with:
          name: smoke-artifacts
          path: |
            reports/
            test-results/
            artifacts/

  regression:
    needs: smoke
    runs-on: ubuntu-latest
    strategy:
      fail-fast: false
      matrix:
        browser: [chromium, firefox, webkit]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt
      - run: playwright install --with-deps
      - run: pytest -m regression --browser ${{ matrix.browser }} --tracing retain-on-failure
      - uses: actions/upload-artifact@v4
        if: always()
        with:
          name: regression-${{ matrix.browser }}-artifacts
          path: |
            test-results/
            reports/
            artifacts/
```

### CI/CD Best Practices

- Run smoke tests on every PR.
- Run full regression on scheduled builds or before releases.
- Store secrets in GitHub repository secrets.
- Never commit `.env`, passwords, tokens, or real auth state.
- Upload traces and screenshots on failure.
- Use browser matrix only when cross-browser coverage is valuable.
- Keep CI tests independent so they can run in parallel.
- Use API setup/cleanup instead of manual test data dependencies.
- Use stable test accounts and dedicated test environments.

---

## 40. Supplemental Module 35 - Thorough API Testing Strategy

API tests validate backend behavior quickly and can also support UI tests by creating setup data and cleaning up test data.

### Recommended API Test Structure

```text
tests/api/
├── test_auth_api.py
├── test_users_api.py
├── test_tasks_api.py
└── test_negative_api.py
utils/
├── api_client.py
└── schemas.py
```

### API Client Helper

```python
from playwright.sync_api import Playwright, APIRequestContext

class ApiClient:
    def __init__(self, playwright: Playwright, base_url: str, token: str | None = None):
        headers = {"Accept": "application/json"}
        if token:
            headers["Authorization"] = f"Bearer {token}"
        self.context: APIRequestContext = playwright.request.new_context(
            base_url=base_url,
            extra_http_headers=headers
        )

    def get_user(self, user_id: int):
        return self.context.get(f"/users/{user_id}")

    def create_user(self, payload: dict):
        return self.context.post("/users", data=payload)

    def delete_user(self, user_id: int):
        return self.context.delete(f"/users/{user_id}")

    def dispose(self):
        self.context.dispose()
```

### API Fixture

```python
import pytest
from utils.api_client import ApiClient
from utils.config import settings

@pytest.fixture
def api_client(playwright):
    client = ApiClient(playwright, settings.API_BASE_URL)
    yield client
    client.dispose()
```

### CRUD Test

```python
def test_create_read_delete_user(api_client):
    payload = {"name": "Brian", "role": "QA"}
    created = api_client.create_user(payload)
    assert created.status in [200, 201]
    created_body = created.json()
    user_id = created_body["id"]

    fetched = api_client.get_user(user_id)
    assert fetched.ok
    assert fetched.json()["name"] == "Brian"

    deleted = api_client.delete_user(user_id)
    assert deleted.status in [200, 202, 204]
```

### Negative API Test

```python
def test_create_user_missing_required_name(api_client):
    response = api_client.create_user({"role": "QA"})
    assert response.status in [400, 422]
```

### API Testing Checklist

| Area | What to Validate |
|---|---|
| Status codes | 200, 201, 204, 400, 401, 403, 404, 409, 422, 500 handling |
| Response body | Required fields, correct values, correct types |
| Headers | Content type, auth, caching, correlation IDs if used |
| Auth | Missing token, invalid token, expired token, role-based access |
| Query strings | Filtering, sorting, pagination, limits |
| CRUD | Create, read, update, patch, delete, cleanup |
| Negative tests | Missing fields, invalid values, invalid IDs, duplicate records |
| Data cleanup | Delete generated data after tests |
| Contract checks | Schema expectations and required fields |

---

## 41. Supplemental Module 36 - Thorough Login Testing Strategy

Login testing is one of the most important workflows because many applications depend on authenticated user sessions.

### Login Scenarios to Cover

| Scenario | Expected Result |
|---|---|
| Valid username/password | User reaches dashboard or authenticated landing page |
| Invalid password | Error message is displayed and user remains logged out |
| Invalid username | Error message is displayed and user remains logged out |
| Empty username/password | Required field validation appears |
| Locked user | Locked-account message appears |
| Disabled user | Access denied or account disabled message appears |
| Logout | Session ends and protected pages redirect to login |
| Session reuse | Saved storage state opens authenticated pages without logging in again |
| Expired session | User is redirected to login or receives session-expired message |
| Role-based login | User sees only permissions allowed for the role |

### Page Object for Login Testing

```python
from playwright.sync_api import Page, expect

class LoginPage:
    def __init__(self, page: Page):
        self.page = page
        self.email = page.get_by_label("Email")
        self.password = page.get_by_label("Password")
        self.sign_in = page.get_by_role("button", name="Sign in")
        self.error = page.get_by_role("alert")

    def open(self, base_url: str):
        self.page.goto(f"{base_url}/login")

    def login(self, email: str, password: str):
        self.email.fill(email)
        self.password.fill(password)
        self.sign_in.click()

    def expect_error(self, message: str):
        expect(self.error).to_contain_text(message)
```

### Valid Login Test

```python
from utils.config import settings
from pages.login_page import LoginPage


def test_valid_login(page, base_url):
    login = LoginPage(page)
    login.open(base_url)
    login.login(settings.TEST_USER_EMAIL, settings.TEST_USER_PASSWORD)
    assert "dashboard" in page.url
```

**Expected result:** The user lands on the dashboard or another authenticated page.

### Invalid Login Test

```python
def test_invalid_login_shows_error(page, base_url):
    login = LoginPage(page)
    login.open(base_url)
    login.login("bad@example.com", "wrong-password")
    login.expect_error("Invalid")
```

**Expected result:** The app displays an invalid-login message and does not enter the authenticated area.

### Logout Test

```python
def test_logout_ends_session(authenticated_page):
    authenticated_page.get_by_role("button", name="Account").click()
    authenticated_page.get_by_role("menuitem", name="Logout").click()
    assert "login" in authenticated_page.url
```

**Expected result:** The user is redirected to login and protected pages should no longer be accessible.

### Storage State Login Reuse

```python
# One-time setup after successful login
context.storage_state(path="auth_state.json")

# Reuse in tests
context = browser.new_context(storage_state="auth_state.json")
page = context.new_page()
page.goto("https://example.com/dashboard")
```

**Expected result:** Tests start authenticated without repeating UI login.

### Login Testing Best Practices

- Use test-only accounts, not personal accounts.
- Store credentials in secrets or `.env` files ignored by Git.
- Avoid testing real MFA unless a test MFA bypass or automation-safe method exists.
- Keep one or two UI login tests, then reuse storage state for most authenticated tests.
- Test authorization separately from authentication.
- Use API login where possible for fast setup.
- Validate both success and failure paths.
- Confirm logout destroys or invalidates the active session.

---

## 42. Playwright Automation Top 20 Interview Questions and Answers

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

## 43. Best Practices and Troubleshooting

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
11. Use custom frameworks only when repeated complexity justifies the maintenance cost.
12. Keep smoke tests fast and regression tests broader.

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
| Custom framework becomes hard to maintain | Too much abstraction | Simplify fixtures, remove unused helpers, and keep tests readable |

---

## 44. Author

**Brian McCarthy**  
Playwright Automation with Python and Pytest Showcase
