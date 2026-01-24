# Datetime - Date and Time Library for EZ Language

A robust date and time library for EZ language, handling timestamps, formatting, and arithmetic with support for leap years.

## Installation

```bash
ez install datetime
```

Or manually copy `datetime.ez` to your project folder.

## Quick Start

```ez
use "datetime"

// Get current time
now = dt_now()
out "Current time (UTC): " + dt_format(now)

// Create specific date (UTC)
christmas = dt_make(2025, 12, 25, 10, 0, 0)
out dt_format(christmas) // 2025-12-25 10:00:00

// Arithmetic
tomorrow = dt_add(now, 1, 0, 0, 0)
out "Tomorrow: " + dt_format(tomorrow)
```

## API Reference

### Core Functions

| Function | Description |
|----------|-------------|
| `dt_now()` | Get current UTC timestamp (milliseconds since epoch) |
| `dt_make(y, m, d, h, min, s)` | Create timestamp from components |
| `dt_format(ts)` | Format as "YYYY-MM-DD HH:mm:ss" |
| `dt_date_string(ts)` | Format as "YYYY-MM-DD" |
| `dt_time_string(ts)` | Format as "HH:mm:ss" |
| `dt_components(ts)` | Get struct `{year, month, day, hour, minute, second, weekday}` |

### Arithmetic

| Function | Description |
|----------|-------------|
| `dt_add(ts, days, hours, mins, secs)` | Add duration (can be negative) |
| `dt_diff_ms(ts1, ts2)` | Difference in milliseconds |
| `dt_diff_days(ts1, ts2)` | Difference in days |

### Utilities

| Function | Description |
|----------|-------------|
| `dt_is_leap(year)` | Check if year is leap year (yes/no) |
| `dt_floor_div(a, b)` | Integer division helper `a // b` |

## Notes

- **UTC Based**: The library uses Unix Timestamp which is UTC-based. `dt_now()` typically returns UTC time depending on system clock.
- **Large Numbers**: Timestamps are handled using doubles to avoid 32-bit integer overflow issues common in some environments.
- **Weekday**: 0 = Sunday, 1 = Monday, ..., 6 = Saturday.

## License

MIT License

## Author

Abdullah Masood - [@imabd645](https://github.com/imabd645)
