# 📊 Pokemon Stats

## Overview

You'll be building a Pokemon data analysis tool that fetches information from a real API and generates a statistical report. This exercise combines several real-world programming skills:

- **File I/O**: Reading and parsing CSV data
- **HTTP API integration**: Making requests to external web services
- **Error handling**: Dealing with network failures and invalid data
- **Data processing**: Aggregating and analyzing API responses
- **Report generation**: Presenting results in a clear format

This simulates a common workplace scenario where you need to integrate with external data sources, handle unreliable network conditions, and produce actionable insights from the data.

**Time**: 30-45 minutes

## Problem Statement

Given a list of Pokemon in `pokemon.csv` and the `https://pokeapi.co/api/v2/pokemon` API, write a program that calculates the following:

1. Who is the tallest Pokemon?
2. What is the average weight of all the Pokemon?
3. Which Pokemon has the most abilities?
4. **Bonus**: What ability is shared the most between all the Pokemon?

Example request to the API for Pikachu:

```bash
curl -X GET "https://pokeapi.co/api/v2/pokemon/pikachu" -H "accept: application/json"
```

Example response:

```json
{
  "height": 4,
  "weight": 60,
  "abilities": [
    {
      "ability": {
        "name": "static",
        "url": "https://pokeapi.co/api/v2/ability/9/"
      },
      "is_hidden": false,
      "slot": 1
    },
    {
      "ability": {
        "name": "lightning-rod",
        "url": "https://pokeapi.co/api/v2/ability/31/"
      },
      "is_hidden": true,
      "slot": 3
    }
  ],
  ...
}
```

Results can be written to the console(`stdout`) in whatever format you choose.

## Requirements

1. **Parse CSV file** - Read Pokemon names and metadata from the CSV file
2. **Fetch Pokemon data** - Make API calls to get detailed Pokemon information
3. **Handle errors gracefully** - Some Pokemon may not exist or API calls may fail
4. **Calculate statistics** - Only include successfully fetched Pokemon in calculations
