# Python Coding Standards

## Overview
Python coding standards for AI agents to follow when writing Python code. These guidelines ensure consistency, maintainability, and best practices across all Python projects.

---

## Code Style (PEP 8)

### Formatting Basics
- **Indentation**: 4 spaces (never tabs)
- **Line length**: Maximum 88 characters (Black formatter standard)
- **Imports**: Group in order (standard library, third-party, local)
- **Naming conventions**:
  - `snake_case` for functions and variables
  - `PascalCase` for classes
  - `UPPER_CASE` for constants
  - `_leading_underscore` for internal/private

### Import Organization
```python
# Standard library imports
import os
import sys
from pathlib import Path

# Third-party imports
import requests
import pandas as pd

# Local application imports
from myapp.models import User
from myapp.utils import format_date
```

---

## Type Hints

### Required Type Hints
- **All function signatures** must include type hints
- **Class attributes** should be typed
- Use `typing` module for complex types

### Type Hint Examples
```python
from typing import List, Dict, Optional, Union, Tuple

def process_data(
    items: List[str],
    config: Dict[str, any],
    limit: Optional[int] = None
) -> Tuple[List[str], int]:
    """Process items according to config."""
    processed: List[str] = []
    count: int = 0
    
    for item in items:
        processed.append(item.strip())
        count += 1
        if limit and count >= limit:
            break
    
    return processed, count


class DataProcessor:
    """Handles data processing operations."""
    
    name: str
    max_items: int
    results: List[str]
    
    def __init__(self, name: str, max_items: int = 100) -> None:
        self.name = name
        self.max_items = max_items
        self.results = []
```

### Do's
- Always type function parameters and return values
- Use `Optional[T]` for nullable values
- Use `List[T]`, `Dict[K, V]` instead of `list`, `dict`
- Use `any` sparingly - prefer specific types

### Don'ts
- Don't omit type hints from function signatures
- Don't use bare `list` or `dict` without type parameters
- Don't use string literals for types unless necessary (forward references)

---

## Error Handling

### Exception Patterns
- **Be specific**: Catch specific exceptions, not bare `except`
- **Fail fast**: Validate inputs early
- **Raise custom exceptions**: Create domain-specific error types
- **Log errors**: Always log before re-raising

### Error Handling Examples
```python
class ValidationError(Exception):
    """Raised when data validation fails."""
    pass


class DataProcessingError(Exception):
    """Raised when data processing fails."""
    pass


def process_user_data(data: Dict[str, any]) -> User:
    """Process and validate user data.
    
    Args:
        data: Raw user data dictionary
        
    Returns:
        Validated User object
        
    Raises:
        ValidationError: If data validation fails
        DataProcessingError: If processing fails
    """
    # Validate input early
    if not data:
        raise ValidationError("Data cannot be empty")
    
    if "email" not in data:
        raise ValidationError("Email field is required")
    
    try:
        # Process data
        user = User(
            email=data["email"],
            name=data.get("name", ""),
        )
        return user
        
    except KeyError as e:
        raise ValidationError(f"Missing required field: {e}") from e
    
    except Exception as e:
        # Log and re-raise as domain exception
        logger.error(f"Failed to process user data: {e}")
        raise DataProcessingError(f"Processing failed: {e}") from e
```

### Do's
- Create custom exception classes for domain errors
- Use `try`/`except` for expected errors
- Chain exceptions with `raise ... from e`
- Include helpful error messages
- Validate inputs at function boundaries

### Don'ts
- Don't use bare `except:` - always specify exception types
- Don't silently catch and ignore exceptions
- Don't use exceptions for control flow
- Don't catch `Exception` unless you re-raise it

---

## Documentation Style

### Docstring Format
Use **Google-style docstrings** for all functions, classes, and modules.

### Docstring Examples
```python
"""Module for handling user authentication.

This module provides functions and classes for user login,
logout, and session management.
"""


def calculate_discount(
    price: float,
    discount_percent: float,
    max_discount: Optional[float] = None
) -> float:
    """Calculate the discounted price.
    
    Args:
        price: Original price before discount
        discount_percent: Discount percentage (0-100)
        max_discount: Maximum discount amount allowed (optional)
        
    Returns:
        The final price after applying discount
        
    Raises:
        ValueError: If price is negative or discount_percent is invalid
        
    Examples:
        >>> calculate_discount(100.0, 20.0)
        80.0
        >>> calculate_discount(100.0, 50.0, max_discount=30.0)
        70.0
    """
    if price < 0:
        raise ValueError("Price cannot be negative")
    
    if not 0 <= discount_percent <= 100:
        raise ValueError("Discount must be between 0 and 100")
    
    discount_amount = price * (discount_percent / 100)
    
    if max_discount:
        discount_amount = min(discount_amount, max_discount)
    
    return price - discount_amount


class UserRepository:
    """Repository for user data access operations.
    
    Provides methods for creating, reading, updating, and deleting
    user records from the database.
    
    Attributes:
        db_connection: Database connection instance
        cache_enabled: Whether to use caching for queries
    """
    
    def __init__(self, db_connection: any, cache_enabled: bool = True) -> None:
        """Initialize the user repository.
        
        Args:
            db_connection: Active database connection
            cache_enabled: Enable query result caching
        """
        self.db_connection = db_connection
        self.cache_enabled = cache_enabled
```

### Do's
- Write docstrings for all public functions, classes, and modules
- Include `Args`, `Returns`, and `Raises` sections
- Provide examples for complex functions
- Keep docstrings up to date with code changes

### Don'ts
- Don't write docstrings for obvious private methods
- Don't repeat information that's clear from type hints
- Don't use single-line docstrings for complex functions

---

## Quick Reference

| Category | Standard |
|----------|----------|
| **Style** | PEP 8, 88 char line length |
| **Naming** | `snake_case`, `PascalCase`, `UPPER_CASE` |
| **Type Hints** | Required for all function signatures |
| **Exceptions** | Specific exceptions, custom error classes |
| **Docstrings** | Google-style for all public APIs |
| **Imports** | Grouped: stdlib, third-party, local |

---

## Additional Best Practices

### Code Organization
```python
# Module-level docstring first
"""Module description."""

# Imports second
import os
from typing import List

# Constants third
MAX_RETRIES: int = 3
DEFAULT_TIMEOUT: float = 30.0

# Classes and functions last
class MyClass:
    pass

def my_function() -> None:
    pass
```

### Context Managers
```python
# Use context managers for resources
with open("file.txt", "r") as f:
    content = f.read()

# Use contextlib for custom contexts
from contextlib import contextmanager

@contextmanager
def temporary_setting(setting: str, value: any):
    """Temporarily change a setting."""
    old_value = get_setting(setting)
    set_setting(setting, value)
    try:
        yield
    finally:
        set_setting(setting, old_value)
```

### List Comprehensions
```python
# Prefer comprehensions for simple transformations
squares = [x**2 for x in range(10)]
evens = [x for x in numbers if x % 2 == 0]

# Use generator expressions for large datasets
sum_of_squares = sum(x**2 for x in range(1000000))
```
