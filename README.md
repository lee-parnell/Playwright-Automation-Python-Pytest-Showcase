# Playwright Python and Pytest for Web Automation Testing

A comprehensive guide to test automation using **Playwright**, **Python**, and **Pytest**. This repository covers everything from basic setup to advanced testing techniques including UI automation, API testing, and continuous integration.

**Written by Brian McCarthy**

---

## Table of Contents

- [Project Overview](#project-overview)
- [Languages & Technologies](#languages--technologies)
- [Project Methodologies](#project-methodologies)
- [File Structure](#file-structure)
- [Core Concepts & Code Examples](#core-concepts--code-examples)
  - [Basic Test Structure](#basic-test-structure)
  - [Page Object Model (POM)](#page-object-model-pom)
  - [Web-First Assertions](#web-first-assertions)
  - [Pytest Fixtures](#pytest-fixtures)
  - [API Testing](#api-testing)
  - [Data-Driven Testing](#data-driven-testing)
  - [Behavior Driven Development (BDD)](#behavior-driven-development-bdd)
- [API Testing Guide & Tutorial](#api-testing-guide--tutorial)
- [Tips & Best Practices](#tips--best-practices)
- [Getting Started](#getting-started)
- [Project Functions Overview](#project-functions-overview)

---

## Project Overview

This project demonstrates end-to-end test automation strategies using Playwright for both UI and API testing. It includes 21 comprehensive sections covering topics from basic locators to advanced CI/CD integration.

---

## Languages & Technologies

| Technology | Version | Percentage |
|------------|---------|------------|
| **Python** | 3.x | 94.7% |
| **HTML** | - | 5.3% |

### Key Libraries & Frameworks

- **Playwright** - Cross-browser automation framework
- **Pytest** - Python testing framework with fixtures and plugins
- **pytest-playwright** - Pytest plugin for Playwright integration
- **pytest-bdd** - Behavior Driven Development support
- **Requests** - HTTP library for API testing

---

## Project Methodologies

### 1. **Page Object Model (POM)**
Encapsulates web page elements and actions into reusable classes, improving maintainability and reducing code duplication.

### 2. **Test-Driven Development (TDD)**
Write tests first, then implement functionality to pass those tests.

### 3. **Data-Driven Testing**
Parameterize tests to run with multiple data sets, maximizing test coverage.

### 4. **Behavior-Driven Development (BDD)**
Write tests in plain language using Gherkin syntax that bridges business and technical teams.

### 5. **Fixture-Based Testing**
Use Pytest fixtures for setup, teardown, and dependency injection.

### 6. **Web-First Assertions**
Assertions that automatically wait for conditions to be true, increasing test reliability.

### 7. **API-First Testing**
Test backend APIs before UI to catch issues early.

### 8. **Continuous Integration (CI)**
Automated test execution in pipelines using GitHub Actions.

---

## File Structure

```
Playwright-Automation-Python-Pytest/
│
├── S01 - Getting Started/              # Introduction and setup
├── S02 - Locators/                    # Element locator strategies (CSS, XPath, role-based)
├── S04 - Events/                      # Event handling and listeners
├── S05 - Authentication/              # Login, session management
├── S06 - Automated Mail Checker/      # Email automation testing
├── S07 - pytest/                      # Pytest fundamentals
├── S08 - pytest-playwright Plugin/    # Pytest-Playwright plugin usage
├── S09 - Playwright Tools/            # Inspector, codegen, trace viewer
├── S10 - Web-First Assertions/        # Expect library and assertions
├── S11 - UI Testing Playground/       # Real-world UI test examples
├── S12 - Playwright Fixtures/         # Custom fixtures for tests
├── S13 - Page Object Model/           # POM design pattern implementation
├── S15 - API Testing/                 # REST API testing with Playwright
├── S16 - Optimization/                # Performance and optimization tips
├── S17 - Tips and Tricks/             # Best practices and workarounds
├── S18 - GitHub API/                  # Testing GitHub REST API
├── S19 - Continuous Integration/      # GitHub Actions workflows
├── S20 - Data Driven Testing/         # Parameterized tests
├── S21 - Behaviour Driven Development/# BDD with pytest-bdd
│
└── README.md                           # This file
```

---

## Core Concepts & Code Examples

### Basic Test Structure

#### Simple Test Example:
```python
from playwright.sync_api import Page, expect

def test_example_com(page: Page):
    # Navigate to website
    page.goto("https://example.com")
    
    # Find element by role
    link = page.get_by_role("link", name="Docs")
    
    # Assert element is visible
    expect(link).to_be_visible()
    
    # Perform action
    link.click()
    
    # Verify result
    expect(page).to_have_title("Documentation")
```

**Key Components:**
- `page: Page` - Injected fixture representing the browser page
- `page.goto()` - Navigate to URL
- `page.get_by_role()` - Locate elements by accessibility role
- `expect()` - Web-first assertion that waits up to 5 seconds

---

### Page Object Model (POM)

#### LoginPage Class Example:
```python
from playwright.sync_api import Page

class LoginPage:
    def __init__(self, page: Page):
        self.page = page
        self.page.goto("http://uitestingplayground.com/sampleapp")
        
        # Define locators
        self.username_input = self.page.get_by_placeholder("User Name")
        self.password_input = self.page.get_by_placeholder("********")
        self.login_btn = self.page.get_by_role("button", name="Log In")
        self.label = self.page.locator("label#loginstatus")
    
    def login(self, username, password):
        """Perform login action"""
        self.username_input.fill(username)
        self.password_input.fill(password)
        self.login_btn.click()
    
    def get_status_message(self):
        """Get login status message"""
        return self.label.text_content()
```

#### Using POM in Tests:
```python
def test_successful_login(page: Page):
    login_page = LoginPage(page)
    login_page.login("testuser", "password123")
    
    status = login_page.get_status_message()
    assert "Welcome" in status
```

**Benefits:**
- Centralized element definitions
- Easy maintenance - update locators in one place
- Improved readability and reusability
- Reduced test code duplication

---

### Advanced Page Object Example:
```python
from playwright.sync_api import Page, Locator

class PlaywrightPage:
    def __init__(self, page: Page):
        self.page = page
        self.page.goto("https://playwright.dev/python")
        
        self.docs_link = self.page.get_by_role("link", name="Docs")
        self.search_input = self.page.get_by_placeholder("Search docs")
    
    def visit_docs(self):
        """Click on Docs link"""
        self.docs_link.click()
    
    def search(self, query):
        """Search with keyboard shortcut"""
        self.page.keyboard.press("Control+KeyK")
        self.search_input.fill(query)
    
    def search_results(self) -> Locator:
        """Get and display search results"""
        print("Search Results:")
        for result in self.page.locator("span.DocSearch-Hit-title").all():
            print(result.inner_text())
        
        return self.page.locator("div.DocSearch-Dropdown")
```

---

### Web-First Assertions

```python
from playwright.sync_api import Page, expect
import re

def test_attribute_assertions(page: Page):
    page.goto("https://playwright.dev/python")
    
    docs_link = page.get_by_role("link", name="Docs")
    
    # Exact class value
    expect(docs_link).to_have_class("navbar__item navbar__link")
    
    # Partial class match with regex
    expect(docs_link).to_have_class(re.compile(r"navbar__link"))
    
    # Verify attribute exists
    expect(docs_link).to_have_attribute("href")
    
    # Verify attribute value
    expect(docs_link).to_have_attribute("href", "/python/docs/intro")
    
    # Verify text content
    expect(docs_link).to_contain_text("Docs")
    
    # Verify visibility
    expect(docs_link).to_be_visible()
    
    # Verify is enabled
    expect(docs_link).to_be_enabled()
    
    # Count elements
    expect(page.locator("a.navbar__link")).to_have_count(5)
```

**Common Assertions:**
- `to_be_visible()` - Element is visible
- `to_be_hidden()` - Element is hidden
- `to_be_enabled()` - Element is enabled
- `to_be_disabled()` - Element is disabled
- `to_be_checked()` - Checkbox is checked
- `to_have_text()` - Text content matches
- `to_have_attribute()` - Attribute value matches
- `to_have_class()` - Class attribute matches
- `to_have_count()` - Number of elements matches

---

### Pytest Fixtures

```python
import pytest
from playwright.sync_api import sync_playwright, Page

@pytest.fixture(scope="session")
def browser():
    """Create browser instance for entire test session"""
    p = sync_playwright().start()
    browser = p.chromium.launch(headless=True)
    yield browser
    browser.close()
    p.stop()

@pytest.fixture
def context(browser):
    """Create new context for each test"""
    context = browser.new_context()
    yield context
    context.close()

@pytest.fixture
def page(context) -> Page:
    """Create new page for each test"""
    return context.new_page()

@pytest.fixture
def api_context(playwright):
    """Create API context for API testing"""
    api_context = playwright.request.new_context(
        base_url="https://dummyjson.com",
        extra_http_headers={'Content-Type': 'application/json'},
    )
    yield api_context
    api_context.dispose()

def test_with_fixtures(page: Page):
    """Test using injected fixtures"""
    page.goto("https://example.com")
    assert page.title() != ""
```

**Fixture Scopes:**
- `function` - New instance per test (default)
- `class` - Shared per test class
- `module` - Shared per module
- `session` - Shared for entire test session

---

### API Testing

#### Basic API Test Example:
```python
from playwright.sync_api import Page

def test_users_api(page: Page):
    """Test API endpoint and parse JSON response"""
    response = page.goto("https://dummyjson.com/users/1")
    
    user_data = response.json()
    
    # Assertions on API response
    assert "firstName" in user_data
    assert "lastName" in user_data
    assert user_data["firstName"] == "Terry"
    assert user_data["lastName"] == "Medhurst"
```

#### API Context for Multiple Requests:
```python
import pytest
from playwright.sync_api import Playwright, APIRequestContext

@pytest.fixture
def api_context(playwright: Playwright) -> APIRequestContext:
    api_context = playwright.request.new_context(
        base_url="https://dummyjson.com",
        extra_http_headers={'Content-Type': 'application/json'},
    )
    yield api_context
    api_context.dispose()

def test_create_user(api_context: APIRequestContext):
    """Test POST request"""
    response = api_context.post(
        "users/add",
        data={
            "firstName": "Damien",
            "lastName": "Smith",
            "age": 27
        }
    )
    user_data = response.json()
    
    assert user_data["id"] == 101
    assert user_data["firstName"] == "Damien"

def test_update_user(api_context: APIRequestContext):
    """Test PUT request"""
    response = api_context.put(
        "users/1",
        data={
            "lastName": "Smith",
            "age": 20,
        }
    )
    user_data = response.json()
    
    assert user_data["lastName"] == "Smith"
    assert user_data["age"] == 20

def test_remove_user(api_context: APIRequestContext):
    """Test DELETE request"""
    response = api_context.delete("users/1")
    user_data = response.json()
    
    assert user_data["isDeleted"] is True
```

#### API Testing with Search Parameters:
```python
def test_users_search(api_context: APIRequestContext):
    """Test API with query parameters"""
    query = "John"
    response = api_context.get(f"/users/search?q={query}")
    
    users_data = response.json()
    
    print(f"Users found: {users_data['total']}")
    
    for user in users_data["users"]:
        print(f"Checking user: {user['firstName']}")
        assert query in user["firstName"]
```

---

## API Testing Guide & Tutorial

### Getting Started with API Testing

#### 1. **Understanding HTTP Methods**

| Method | Purpose | Use Case |
|--------|---------|----------|
| GET | Retrieve data | Fetch user info, list items |
| POST | Create new resource | Add new user, submit form |
| PUT | Update entire resource | Replace user data |
| PATCH | Partial update | Update specific fields |
| DELETE | Remove resource | Delete user, remove item |

#### 2. **Setting Up API Context**

```python
from playwright.sync_api import Playwright, APIRequestContext

@pytest.fixture
def api(playwright: Playwright):
    """Fixture for API testing"""
    context = playwright.request.new_context(
        base_url="https://api.example.com/v1",
        extra_http_headers={
            'Content-Type': 'application/json',
            'Authorization': f'Bearer {TOKEN}',
        }
    )
    yield context
    context.dispose()
```

#### 3. **Common API Testing Patterns**

**Pattern 1: Test Response Status**
```python
def test_api_status(api_context):
    response = api_context.get("/users/1")
    assert response.status == 200  # OK
```

**Pattern 2: Validate Response Structure**
```python
def test_response_structure(api_context):
    response = api_context.get("/users/1")
    data = response.json()
    
    required_fields = ["id", "firstName", "lastName", "email"]
    for field in required_fields:
        assert field in data, f"Missing field: {field}"
```

**Pattern 3: Test Error Handling**
```python
def test_user_not_found(api_context):
    response = api_context.get("/users/99999")
    assert response.status == 404  # Not Found
```

**Pattern 4: Validate Array Responses**
```python
def test_user_list(api_context):
    response = api_context.get("/users")
    users = response.json()
    
    assert isinstance(users, list)
    assert len(users) > 0
    
    for user in users:
        assert "id" in user
        assert "firstName" in user
```

#### 4. **API Testing Best Practices**

1. **Use Base URLs** - Reduce duplication
```python
api_context = playwright.request.new_context(
    base_url="https://api.example.com"
)
response = api_context.get("/users")  # Full URL: https://api.example.com/users
```

2. **Set Default Headers** - For authentication and content-type
```python
api_context = playwright.request.new_context(
    base_url="https://api.example.com",
    extra_http_headers={
        'Content-Type': 'application/json',
        'Authorization': f'Bearer {AUTH_TOKEN}',
    }
)
```

3. **Validate Response Headers**
```python
def test_response_headers(api_context):
    response = api_context.get("/users")
    assert response.headers["content-type"] == "application/json"
    assert "x-ratelimit-remaining" in response.headers
```

4. **Test Edge Cases**
```python
def test_empty_query(api_context):
    response = api_context.get("/users/search?q=")
    assert response.status in [200, 400]

def test_special_characters(api_context):
    response = api_context.get("/users/search?q=John@#$%")
    assert response.status in [200, 400]
```

#### 5. **Mocking API Responses**

```python
from playwright.sync_api import Route

def handle_route(route: Route):
    """Mock API response"""
    response = route.fetch()
    user_data = response.json()
    
    # Modify response
    user_data["firstName"] = "Mocked"
    
    route.fulfill(
        response=response,
        json=user_data,
    )

def test_mock_api(page: Page):
    page.route("https://dummyjson.com/users/1", handle_route)
    
    response = page.goto("https://dummyjson.com/users/1")
    data = response.json()
    
    assert data["firstName"] == "Mocked"
```

#### 6. **Testing Authentication APIs**

```python
def test_user_login(api_context: APIRequestContext):
    """Test login API endpoint"""
    response = api_context.post(
        "/auth/login",
        data={
            "username": "testuser",
            "password": "password123"
        }
    )
    
    assert response.status == 200
    
    data = response.json()
    assert "token" in data
    assert "user" in data
    assert data["user"]["username"] == "testuser"

def test_token_refresh(api_context: APIRequestContext):
    """Test token refresh endpoint"""
    response = api_context.post(
        "/auth/refresh",
        data={"refreshToken": "old_token_123"}
    )
    
    assert response.status == 200
    
    data = response.json()
    assert "accessToken" in data
    assert data["accessToken"] != "old_token_123"
```

#### 7. **API Testing with File Upload**

```python
def test_upload_file(api_context: APIRequestContext):
    """Test file upload endpoint"""
    response = api_context.post(
        "/files/upload",
        files={
            "file": ("test.txt", b"Hello World", "text/plain")
        }
    )
    
    assert response.status == 200
    data = response.json()
    assert "fileId" in data
    assert data["filename"] == "test.txt"
```

#### 8. **Complete API Test Suite Example**

```python
import pytest
from playwright.sync_api import Playwright, APIRequestContext

@pytest.fixture
def api(playwright: Playwright):
    context = playwright.request.new_context(
        base_url="https://jsonplaceholder.typicode.com"
    )
    yield context
    context.dispose()

class TestAPIOperations:
    """Test suite for REST API operations"""
    
    def test_get_posts(self, api):
        response = api.get("/posts")
        assert response.status == 200
        
        posts = response.json()
        assert isinstance(posts, list)
        assert len(posts) > 0
        assert "userId" in posts[0]
        assert "title" in posts[0]
        assert "body" in posts[0]
    
    def test_create_post(self, api):
        response = api.post(
            "/posts",
            data={
                "title": "Test Post",
                "body": "This is a test",
                "userId": 1
            }
        )
        assert response.status == 201  # Created
        
        post = response.json()
        assert post["title"] == "Test Post"
        assert post["userId"] == 1
    
    def test_get_single_post(self, api):
        response = api.get("/posts/1")
        assert response.status == 200
        
        post = response.json()
        assert post["id"] == 1
        assert "title" in post
    
    def test_update_post(self, api):
        response = api.put(
            "/posts/1",
            data={
                "title": "Updated Title",
                "body": "Updated body",
                "userId": 1
            }
        )
        assert response.status == 200
        
        post = response.json()
        assert post["title"] == "Updated Title"
    
    def test_delete_post(self, api):
        response = api.delete("/posts/1")
        assert response.status == 200
```

---

### Data-Driven Testing

```python
import pytest
from playwright.sync_api import Page

@pytest.mark.parametrize("username,password,expected_result", [
    ("user1", "pass123", True),
    ("user2", "pass456", True),
    ("invalid", "wrong", False),
    ("", "", False),
])
def test_login_multiple_users(page: Page, username, password, expected_result):
    """Test login with multiple data sets"""
    page.goto("http://example.com/login")
    
    page.get_by_placeholder("Username").fill(username)
    page.get_by_placeholder("Password").fill(password)
    page.get_by_role("button", name="Log In").click()
    
    if expected_result:
        assert page.url == "http://example.com/dashboard"
    else:
        assert "login" in page.url
```

---

### Behavior Driven Development (BDD)

```python
# features/login.feature
Feature: User Login
  Scenario: Successful login
    Given user navigates to login page
    When user enters valid credentials
    And user clicks login button
    Then user should see dashboard
```

```python
# tests/test_login_bdd.py
import pytest
from pytest_bdd import given, when, then, scenarios

scenarios("../features")

@given("user navigates to login page")
def user_on_login_page(page):
    page.goto("http://example.com/login")
    yield page

@when("user enters valid credentials")
def enter_credentials(page):
    page.get_by_placeholder("Username").fill("testuser")
    page.get_by_placeholder("Password").fill("password123")

@when("user clicks login button")
def click_login(page):
    page.get_by_role("button", name="Log In").click()

@then("user should see dashboard")
def verify_dashboard(page):
    assert page.url == "http://example.com/dashboard"
```

---

### Locator Strategies

```python
# By text
element = page.get_by_text("Click me")

# By role
button = page.get_by_role("button", name="Submit")
link = page.get_by_role("link", name="Home")

# By placeholder
input_field = page.get_by_placeholder("Enter name")

# By label
input_field = page.get_by_label("Username")

# By test ID (requires data-testid attribute)
element = page.get_by_test_id("user-card")

# CSS selector
element = page.locator(".button.primary")
element = page.locator("#submit-btn")

# XPath
element = page.locator("//button[contains(@class, 'btn-primary')]")
element = page.locator("//input[@type='email']")

# By attribute
element = page.locator("[data-id='123']")
element = page.locator("[aria-label='Close']")
```

---

## Tips & Best Practices

### 1. **Use Meaningful Wait Strategies**
```python
# Good: Uses built-in waiting
expect(page.get_by_text("Success")).to_be_visible()

# Avoid: Hard coding wait times
import time
time.sleep(5)  # ❌ Fragile and slow
```

### 2. **Avoid Brittle Selectors**
```python
# Good: Role-based selectors
page.get_by_role("button", name="Submit")

# Avoid: CSS selectors dependent on structure
page.locator("div > div > div > button")  # ❌ Brittle
```

### 3. **Use Proper Assertions**
```python
# Good: Web-first assertions
expect(page).to_have_url("https://example.com")

# Avoid: Manual checking
assert page.url == "https://example.com"  # No automatic waiting
```

### 4. **Organize Tests by Feature**
```
tests/
├── auth/
│   ├── test_login.py
│   ├── test_signup.py
│   └── test_password_reset.py
├── products/
│   ├── test_search.py
│   └── test_details.py
└── conftest.py
```

### 5. **Use Descriptive Test Names**
```python
# Good
def test_user_can_login_with_valid_credentials():
    pass

# Avoid
def test_1():  # ❌ Not descriptive
    pass
```

### 6. **Capture Screenshots on Failure**
```python
@pytest.fixture
def page_with_screenshot(page):
    yield page
    if page.context.browser_type.name == "chromium":
        page.screenshot(path="failure.png")
```

### 7. **Use Soft Assertions for Multiple Checks**
```python
# Check multiple conditions without failing immediately
expect(page).to_have_title("Expected Title")
expect(page).to_have_url("https://example.com")
expect(page.get_by_text("Success")).to_be_visible()
```

---

## Getting Started

### Prerequisites
- Python 3.8+
- pip (Python package manager)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/BrianGator/Playwright-Automation-Python-Pytest.git
cd Playwright-Automation-Python-Pytest
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Install Playwright browsers**
```bash
playwright install
```

### Running Tests

```bash
# Run all tests
pytest

# Run specific test file
pytest tests/test_login.py

# Run with verbose output
pytest -v

# Run tests with headless browser
pytest --headed=False

# Run tests in parallel
pytest -n auto

# Generate HTML report
pytest --html=report.html

# Run with tracing enabled
pytest --tracing=on
```

### Configuration

Create `pytest.ini` for configuration:
```ini
[pytest]
testpaths = tests
python_files = test_*.py
python_classes = Test*
python_functions = test_*
addopts = -v --tb=short
```

---

## Project Functions Overview

### Navigation Functions
| Function | Purpose |
|----------|---------|
| `page.goto(url)` | Navigate to URL |
| `page.go_back()` | Navigate back |
| `page.go_forward()` | Navigate forward |
| `page.reload()` | Reload page |

### Locator Functions
| Function | Purpose |
|----------|---------|
| `page.locator(selector)` | CSS/XPath selector |
| `page.get_by_role(role, name)` | Find by accessibility role |
| `page.get_by_text(text)` | Find by text content |
| `page.get_by_placeholder(text)` | Find by placeholder |
| `page.get_by_label(text)` | Find by label |
| `page.get_by_test_id(id)` | Find by test ID |

### Interaction Functions
| Function | Purpose |
|----------|---------|
| `locator.click()` | Click element |
| `locator.fill(text)` | Fill input field |
| `locator.type(text)` | Type text (with events) |
| `locator.select_option(value)` | Select option |
| `locator.check()` | Check checkbox |
| `locator.uncheck()` | Uncheck checkbox |
| `locator.hover()` | Hover over element |
| `locator.drag_to(target)` | Drag and drop |

### Assertion Functions
| Function | Purpose |
|----------|---------|
| `expect(locator).to_be_visible()` | Verify visibility |
| `expect(locator).to_be_hidden()` | Verify hidden state |
| `expect(locator).to_have_text(text)` | Verify text |
| `expect(locator).to_have_attribute(attr, value)` | Verify attribute |
| `expect(locator).to_have_class(class)` | Verify CSS class |
| `expect(page).to_have_url(url)` | Verify page URL |
| `expect(page).to_have_title(title)` | Verify page title |

### API Functions
| Function | Purpose |
|----------|---------|
| `api_context.get(endpoint)` | GET request |
| `api_context.post(endpoint, data)` | POST request |
| `api_context.put(endpoint, data)` | PUT request |
| `api_context.patch(endpoint, data)` | PATCH request |
| `api_context.delete(endpoint)` | DELETE request |
| `response.json()` | Parse JSON response |
| `response.status` | HTTP status code |

---

## Project Sections Overview

- **S01** - Getting Started with Playwright
- **S02** - Locator Strategies (CSS, XPath, Accessibility)
- **S04** - Event Handling
- **S05** - Authentication & Session Management
- **S06** - Automated Email Testing
- **S07** - Pytest Fundamentals
- **S08** - Pytest-Playwright Plugin
- **S09** - Playwright Tools (Inspector, Trace Viewer)
- **S10** - Web-First Assertions
- **S11** - Real-world UI Testing Examples
- **S12** - Custom Fixtures
- **S13** - Page Object Model Pattern
- **S15** - REST API Testing
- **S16** - Performance Optimization
- **S17** - Pro Tips & Tricks
- **S18** - GitHub API Testing
- **S19** - CI/CD Integration
- **S20** - Data-Driven Testing
- **S21** - Behavior-Driven Development

---

## Resources

- [Playwright Documentation](https://playwright.dev/python/)
- [Pytest Documentation](https://docs.pytest.org/)
- [Pytest-BDD Documentation](https://pytest-bdd.readthedocs.io/)

---

**Written by Brian McCarthy**

Licensed under the MIT License.
