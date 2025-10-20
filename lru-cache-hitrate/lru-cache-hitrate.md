# LRU Cache with Hit Rate Tracking

## What is an LRU Cache?

An LRU (Least Recently Used) cache is a data structure that stores a limited number of items. When the cache is full and you need to add a new item, it removes the item that hasn't been used for the longest time. Think of it like a small bookshelf - when it's full and you want to add a new book, you remove the book you haven't read in the longest time.

For example, if you have a cache that holds 3 items:

- Add "A", "B", "C" → cache contains [A, B, C]
- Access "A" → "A" becomes most recently used
- Add "D" → "B" gets removed (least recently used), cache becomes [A, C, D]

## Problem Statement

Build a Least Recently Used (LRU) cache that stores string keys and values, and tracks performance metrics.

## Requirements

### Core LRU Functionality

- `LRUCache(capacity)` - Constructor that creates cache with specified size
- `get(key)` - Retrieve string value by string key, return None if not found
- `put(key, value)` - Insert or update string key-value pair
- fixed capacity - When cache is full, evict the least recently used item
- O(1) time complexity for both get and put operations

**Note:** All keys and values should be strings (we're building a string cache).

### Hit Rate Tracking

- Track cache hits and misses
- `get_hit_rate()` - Return hit rate as float (0.0 to 1.0)
- `get_stats()` - Return dict with hits, misses, total_requests, current_size
- `reset_stats()` - Reset hit/miss counters to zero
