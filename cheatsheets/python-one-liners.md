# Python One-Liners Cheatsheet

*Things I look up repeatedly — now I don't have to.*

## List Operations

```python
# Filter
evens = [x for x in range(20) if x % 2 == 0]

# Transform
squared = [x**2 for x in range(10)]

# Filter + transform
big_squares = [x**2 for x in range(10) if x > 5]

# Flatten nested list
flat = [item for sublist in nested for item in sublist]

# Sort by key
sorted_list = sorted(people, key=lambda p: p['age'])

# Sort descending
sorted_desc = sorted(nums, reverse=True)

# Remove duplicates (preserving order)
unique = list(dict.fromkeys(my_list))
```

## Dictionary Operations

```python
# Merge two dicts (Python 3.9+)
merged = dict1 | dict2

# Dict comprehension
squared = {k: v**2 for k, v in nums.items()}

# Filter dict
filtered = {k: v for k, v in d.items() if v > 0}

# Get value with default
val = d.get('key', 'default')

# Invert a dict
inverted = {v: k for k, v in d.items()}
```

## String Operations

```python
# Split and strip
words = [w.strip() for w in text.split(',')]

# Join list into string
csv_line = ', '.join(str(x) for x in items)

# Check if all chars are digits
"12345".isdigit()  # True

# Count occurrences
text.count('word')

# f-string with formatting
f"{value:.2f}"     # 2 decimal places
f"{num:,}"         # Thousands separator: 1,234,567
f"{pct:.1%}"       # Percentage: 45.3%
```

## File Operations

```python
# Read file
with open('file.txt') as f:
    content = f.read()

# Read lines
with open('file.txt') as f:
    lines = [line.strip() for line in f]

# Write file
with open('output.txt', 'w') as f:
    f.write(content)

# Check if file exists
from pathlib import Path
Path('file.txt').exists()
```

## Useful Built-ins

```python
zip(list1, list2)              # Pair elements
enumerate(list)                # Index + value pairs
any(x > 0 for x in nums)      # True if any match
all(x > 0 for x in nums)      # True if all match
max(items, key=lambda x: x.score)  # Max by attribute
min(items, key=lambda x: x.score)  # Min by attribute
```

---

*Last updated: 2026-03-27*
