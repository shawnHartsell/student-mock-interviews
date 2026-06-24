# 🪵 Log Summarizer

## Overview

You'll be building a log analysis tool. A service has produced a large volume of
log lines, and you need to read through them and report on the service's health.

This simulates a common workplace scenario: when a service is misbehaving, you
often need to parse its structured logs and summarize what is happening before
you can act.

**Time**: 30-45 minutes

## Problem Statement

Write a program that reads log lines and produces a summary report. A sample log
file, `sample.log`, is included in this directory.

The logs are structured: each line is a set of `key=value` pairs separated by
spaces, which is the style most modern services emit. Values that contain spaces
are wrapped in double quotes.

Example lines:

```
timestamp=2026-06-24T09:15:01Z level=INFO method=GET route=/api/orders status=200 latency_ms=42
timestamp=2026-06-24T09:15:04Z level=ERROR method=GET route=/api/orders status=500 latency_ms=1203 msg="database timeout"
timestamp=2026-06-24T09:15:03Z level=WARN method=GET route=/api/cart status=200 latency_ms=870 msg="slow response"
```

`level` is one of `INFO`, `WARN`, or `ERROR`. The `msg` field is optional.

## Requirements

1. **Parse the log** - Read the lines and turn each one into its key/value
   fields.
2. **Count by level** - Report how many lines there are at each level.
3. **Error rate** - Report the fraction of all lines that are `ERROR`.
4. **Top errors** - Report the most common `ERROR` messages (`msg`), most
   frequent first.

## Expected Interface

Your implementation should support operations similar to:

```javascript
const lines = readLines("sample.log");
const report = summarize(lines);

report.countsByLevel; // { INFO: 14, WARN: 4, ERROR: 7 }
report.errorRate; // 0.28
report.topErrors(2);
// [ { message: "database timeout", count: 4 },
//   { message: "payment gateway unreachable", count: 3 } ]
```

**Note:** The numbers above are the expected results for the included
`sample.log`.

## Bonus

- **Slow requests** - Use the `latency_ms` field to report the slowest routes,
  or every request over a threshold (e.g., 800ms).
- **Per-route breakdown** - Group counts and error rates by `route`.
