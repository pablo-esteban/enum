enum
====

A fork of the robust [enum 0.4.4](https://pypi.python.org/pypi/enum/) package by Ben Finney

An enumeration object is created with a sequence of string arguments to the Enum() constructor:

    >>> from enum import Enum
    >>> Colours = Enum('red', 'blue', 'green')
    >>> Weekdays = Enum('mon', 'tue', 'wed', 'thu', 'fri', 'sat', 'sun')

The return value is an immutable sequence object with a value for each of the string arguments. Each value is also available as an attribute named from the corresponding string argument:

    >>> pizza_night = Weekdays[4]
    >>> shirt_colour = Colours.green

The values are constants that can be compared only with values from the same enumeration; comparison with other values will invoke Python's fallback comparisons:

    >>> pizza_night == Weekdays.fri
    True
    >>> shirt_colour > Colours.red
    True
    >>> shirt_colour == "green"
    False

Each value from an enumeration exports its sequence index as an integer, and can be coerced to a simple string matching the original arguments used to create the enumeration:

    >>> str(pizza_night)
    'fri'
    >>> shirt_colour.index
    2
