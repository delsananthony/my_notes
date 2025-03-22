# Python Practices

## Python File
- ```python
    #! /usr/bin/env python3
    # -*- coding: utf-8 -*-
    ##############################################################################
    #    Odoo Proprietary License v1.0
    #    Copyright (C) 2024 Your Company (<your_website.com>)
    #
    #    This program is proprietary software: you can’t redistribute it and/or 
    #    modify it under any circumstances without permission from the author.
    #
    #    Author: Your Name (<your_email@example.com>)
    #    Created: YYYY-MM-DD
    #    Description: Brief description of the module or script.
    ############################################################################## ```

## Docstring
- ```python
    def example_method(self, param1, param2):
    """
    Description:
        Briefly explain what this method does.

    Args:
        param1 (str): Description of param1.
        param2 (int): Description of param2.

    Returns:
        dict: Description of the returned value.

    Raises:
        ValueError: If param1 is empty.
        TypeError: If param2 is not an integer.

    Example:
        self.example_method('test', 10)
    """
    if not param1:
        raise ValueError("param1 cannot be empty.")
    if not isinstance(param2, int):
        raise TypeError("param2 must be an integer.")
```