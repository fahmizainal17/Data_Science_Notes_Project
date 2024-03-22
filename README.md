# Data Science Footnote

## Basic Plot using matplotlib.

```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4])
plt.ylabel('some numbers in y')
plt.xlabel('some numbers in x')
plt.show()
```

## Basic Histogram Plot

```python
import matplotlib.pyplot as plt

x = [21, 23, 4, 5, 6, 7, 8, 3, 4, 17, 18]
num_bins = 5
plt.hist(x, num_bins, facecolor='red')
plt.show()
```

## No Free Lunch Theorem

There is no single algorithm that will work well for all tasks.

## Machine Learning Types

- **Supervised:** Involves labeled data, e.g., regression.
- **Unsupervised:** Involves unlabeled data, e.g., clustering and anomaly detection.
- **Reinforcement:** Involves rewarding desired behaviors and punishing undesired ones.

## Data Mining

It refers to the extraction of useful information from raw data. Another term for it is KDD (Knowledge Discovery in Data).

## Digital Ads and CTR

Digital ads are expected to have a higher CTR (Click-Through Rate) compared to traditional advertisements.

## Checking Consecutive Meals

We explored a Python function designed to identify if the same meal has been served on consecutive days in a list of meals. The implementation utilizes a `for` loop and indexing (`meals[i]`) to iterate through the list.

```python
def menu_is_boring(meals):
    for i in range(1, len(meals)):
        if meals[i] == meals[i - 1]:
            return True
    return False
```

## `len()` Function and Indexing

- The `len()` function in Python is used to determine the length of a sequence or collection.
- `meals[i]` is employed to access the element at index `i` in the list `meals`.

## Monte Carlo Method

- The Monte Carlo method, a statistical technique using random sampling, was discussed for estimating complex mathematical outcomes or solving challenging problems. The process involves defining a problem, creating a mathematical model, generating random samples, running simulations, analyzing results, and drawing conclusions.

## Example: Estimate Average Slot Payout

We implemented a Python function (`estimate_average_slot_payout`) using the Monte Carlo method to simulate a slot machine and estimate the average net profit per run.

```python
import random

def estimate_average_slot_payout(n_runs):
    total_net_profit = 0

    for _ in range(n_runs):
        outcome = random.randint(0, 9)
        net_profit = -1 if outcome != 0 else 9
        total_net_profit += net_profit

    average_net_profit = total_net_profit / n_runs
    return average_net_profit

# Example usage:
result = estimate_average_slot_payout(1000000)
print(result)
```

## String Manipulation

We delved into string manipulation in Python, emphasizing the immutability of strings. For example:

```python
planet = "Earth"
planet = "B" + planet[1:]  # Modifying the first character
planet += " and Mars"  # Appending to the string
```

# Python Strings and Dictionaries Overview

This lesson covers two fundamental Python types: strings and dictionaries.

## Strings

Strings in Python are versatile for manipulation, particularly in the context of data science work. Key concepts include:

### String Syntax

Strings can be defined with either single or double quotations. Double quotes are useful when the string contains a single quote character.

```python
x = 'Pluto is a planet'
y = "Pluto is a planet"
x == y  # Evaluates to True
```

### Escaping Characters

To include a single quote inside a single-quoted string, use the backslash character for escaping.

```python
'Pluto\'s a planet!'
```

### String Methods

Python provides various string methods for manipulation:

```python
claim = "Pluto is a planet!"
claim.upper()  # 'PLUTO IS A PLANET!'
claim.lower()  # 'pluto is a planet!'
claim.index('plan')  # 11
claim.startswith('Pluto')  # True
claim.endswith('planet')  # False
```

### Going Between Strings and Lists

Use `str.split()` to convert a string into a list of smaller strings, and `str.join()` to concatenate a list of strings into one string.

```python
words = claim.split()
'/'.join(words)  # 'Pluto/is/a/planet!'
```

### String Formatting with `.format()`

The `.format()` method is a powerful way to concatenate strings with placeholders.

```python
position = 9
"{}, you'll always be the {}th planet to me.".format(planet, position)
```

## Dictionaries

Dictionaries are a built-in data structure in Python for mapping keys to values.

```python
numbers = {'one': 1, 'two': 2, 'three': 3}
```

### Dictionary Operations

Access values, add new key-value pairs, and change existing values using square bracket syntax.

```python
numbers['eleven'] = 11
numbers['one'] = 'Pluto'
```

### Dictionary Comprehensions

Create dictionaries with comprehensions, similar to list comprehensions.

```python
planet_to_initial = {planet: planet[0] for planet in planets}
```

### Iterating Over Dictionaries

Use `for` loops to iterate over keys, values, or both using `dict.items()`.

```python
for planet, initial in planet_to_initial.items():
    print("{} begins with \"{}\"".format(planet.rjust(10), initial))
```

# Python Imports: A Gateway to Extended Functionality

In this tutorial, we will explore the concept of imports in Python, providing insights into working with custom libraries, understanding unfamiliar objects, and navigating operator overloading.

## Imports Unleashed

Python, renowned for its versatility, boasts an extensive collection of custom libraries beyond its built-in types and functions. These libraries, whether part of the standard library or external additions, significantly enhance Python's capabilities, especially in domains like data science.

To tap into the power of these libraries, we employ imports. Let's kick off with a simple example by importing the `math` module from the standard library:

```python
import math

print("It's math! It has type {}".format(type(math)))
```

The `math` module, a reservoir of variables and functions, serves various mathematical purposes. To explore its contents, we turn to the `dir()` function:

```python
print(dir(math))
```

This reveals a plethora of functions and constants, such as `pi`. Accessing these elements is straightforward using dot syntax:

```python
print("pi to 4 significant digits = {:.4}".format(math.pi))
```

## Diving Deeper into Imports

### Alias Magic

For frequently used modules, creating aliases can save typing efforts. Consider the following:

```python
import math as mt
print(mt.pi)
```

This introduces the alias `mt` for the `math` module, streamlining subsequent references.

### Selective Imports

While the `import *` approach grants direct access to all module variables, it may lead to naming conflicts. A cleaner alternative involves importing only what's needed:

```python
from math import log, pi
```

This ensures clarity and avoids unintended clashes between variable names.

## Submodules: Navigating the Module Maze

Modules may contain submodules, paving the way for structured organization. For instance, in the `numpy` module:

```python
import numpy
print("numpy.random is a", type(numpy.random))
```

Here, `numpy.random` signifies a submodule, extending functionality beyond the primary module.

## The Realm of Unfamiliar Objects

As you delve into specialized libraries, encountering novel types becomes inevitable. Three indispensable tools aid in understanding such objects:

1. **`type()`**: Reveals the type of an object.

```python
type(rolls)
```

2. **`dir()`**: Provides a list of attributes and methods associated with an object.

```python
print(dir(rolls))
```

3. **`help()`**: Offers comprehensive documentation on an object or its specific attributes.

```python
help(rolls.ravel)
```

## Operator Overloading: Beyond Basic Arithmetic

Python's leniency towards operator overloading allows custom types to define their behavior. While lists prohibit direct addition with numbers, numpy arrays embrace it:

```python
rolls + 10
```

Understanding how operators interact with custom types is crucial. For instance, numpy arrays introduce unexpected behaviors, like element-wise comparisons:

```python
rolls <= 3
```

## The Intricacies of TensorFlow

Certain libraries, such as TensorFlow, leverage operator overloading extensively. Exploring TensorFlow's symbolic handling showcases the profound impact on expressions:

```python
a = tf.constant(1)
b = tf.constant(1)
a + b
```

This symbolic representation emphasizes TensorFlow's role in computations within a session.

## Tools for the Inquisitive

As you navigate diverse libraries, questions about mysterious names with double underscores may arise. Exploring the `dir()` of a list unveils the world of special methods, paving the way for a deeper understanding of operator overloading.

```python
print(dir(list))
```

Python's official documentation elaborates on these special "underscores" methods, providing a comprehensive guide for those venturing into type definition.


