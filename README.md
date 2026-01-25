# EZ DateTime Library

A professional, object-oriented library for handling dates and times in the EZ language.

## Features

- **High Precision**: Native millisecond-accurate timestamps.
- **OO Design**: Encapsulated logic within the `DateTime` model.
- **Easy Formatting**: Flexible formatting using standard patterns (e.g., `YYYY-MM-DD`).
- **Date Arithmetic**: Easy manipulation of dates (add days, calculate differences).

## Installation

Install via the EZ package manager:

```bash
ez install datetime
```

Include it in your script:

```ez
use "datetime"
```

## API Reference

### `DateTime` Model

#### `now()`
Returns a `DateTime` instance for the current moment.

#### `fromTimestamp(ms)`
Creates a `DateTime` instance from a millisecond timestamp.

#### `format(pattern)`
Returns a formatted string. Supported tokens: `YYYY`, `MM`, `DD`, `HH`, `mm`, `ss`.

#### `addDays(n)`
Adds (or subtracts) `n` days from the current date. Returns `self`.

#### `diffInDays(other)`
Calculates the difference in days between two `DateTime` objects.

## Examples

```ez
use "src/datetime.ez"

// Get current time
dt = DateTime().now()
out "Current: " + dt.format("YYYY-MM-DD HH:mm:ss")

// Date arithmetic
tomorrow = DateTime().now().addDays(1)
out "Tomorrow: " + tomorrow.format("DD/MM/YYYY")

// Timestamps
ts = dt.timestamp
out "MS since epoch: " + str(ts)
```
