# Data Science Foot Note

## Basic Plot using matplotlib

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

## 1. Checking Consecutive Meals

We explored a Python function designed to identify if the same meal has been served on consecutive days in a list of meals. The implementation utilizes a `for` loop and indexing (`meals[i]`) to iterate through the list.

```python
def menu_is_boring(meals):
    for i in range(1, len(meals)):
        if meals[i] == meals[i - 1]:
            return True
    return False
```

## 2. `len()` Function and Indexing

- The `len()` function in Python is used to determine the length of a sequence or collection.
- `meals[i]` is employed to access the element at index `i` in the list `meals`.

## 3. Monte Carlo Method

- The Monte Carlo method, a statistical technique using random sampling, was discussed for estimating complex mathematical outcomes or solving challenging problems. The process involves defining a problem, creating a mathematical model, generating random samples, running simulations, analyzing results, and drawing conclusions.

## 4. Example: Estimate Average Slot Payout

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

## 5. String Manipulation

We delved into string manipulation in Python, emphasizing the immutability of strings. Example:

```python
planet = "Earth"
planet = "B" + planet[1:]  # Modifying the first character
planet += " and Mars"  # Appending to the string
```

# Additional Notes

Here's an example of implementing the `estimate_average_slot_payout` function to simulate pulling the slot machine `n_runs` times, returning the averaged payout.

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
result = estimate_average_slot_payout(10000000)
print(result)
```


