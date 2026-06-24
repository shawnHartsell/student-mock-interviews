# 📅 Meeting Scheduler

## Overview

You'll be building the scheduling logic behind a team calendar app. When someone
books a room, the app needs to know whether the room is already taken, what it
conflicts with, and when the next free slot is.

This simulates a common workplace scenario: any time you reserve a shared
resource such as a meeting room, a rental, or an appointment, you have to reason
about overlapping time ranges and answer availability questions correctly.

**Time**: 30-45 minutes

## Problem Statement

Build a `Calendar` (or `Scheduler`) that manages bookings for a **single room**
during a fixed working day and answers questions about availability.

A **booking** has:

- a title (e.g., `"Standup"`)
- a start time
- an end time

The calendar has **working hours** (for example, `09:00`-`17:00`). Bookings only
ever happen inside working hours.

**Note:** Everything happens within a single day, so represent times however is
simplest in your language. Minutes since midnight (`540` for `09:00`) or
`"HH:MM"` strings both work.

## Requirements

1. **Detect conflicts** - Given a proposed start and end time, return whether it
   overlaps any existing booking.
2. **Book a meeting** - Add a booking only if it doesn't conflict and it falls
   within working hours. Otherwise, reject it.
3. **List conflicts** - Given a proposed time range, return all existing
   bookings it overlaps with.
4. **Find the next available slot** - Given a desired duration (e.g., 30
   minutes) and an earliest acceptable start time, return the earliest free slot
   of that length within working hours.

## Expected Interface

Your implementation should support operations similar to:

```javascript
const cal = new Calendar({ workStart: "09:00", workEnd: "17:00" });

cal.book("Standup", "09:00", "09:15");
cal.book("1:1 with Sam", "10:00", "10:30");

cal.hasConflict("09:10", "09:20"); // true
cal.hasConflict("11:00", "11:30"); // false

cal.conflicts("09:00", "11:00"); // ["Standup", "1:1 with Sam"]

cal.book("Lunch", "10:15", "10:45"); // rejected, overlaps "1:1 with Sam"

cal.nextAvailable(30, "09:30"); // "09:30"
```

## Bonus

- **Free/busy report** - Return all free gaps in the working day, not just the
  next one.
- **Multiple rooms** - Given several rooms, find any room that's free for a
  requested slot.
