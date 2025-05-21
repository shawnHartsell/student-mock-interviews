# Mock Technical Interview: Unique Words Counter

Welcome to your mock technical interview! This exercise is designed to simulate a real technical interview environment and give you experience with pair programming, problem-solving, and communicating your thought process. You may use any programming language of your choice. The interviewer will act as your pair and guide you through the process.

---

## Assignment: Unique Words Counter

### Objective

Write a function that receives a string of text and returns a count of each unique word in the string. The function should return a data structure where the keys are words and the values are their counts.

### Requirements

- **Ignore punctuation** (e.g., commas, periods, exclamation marks).
- **Treat words as case-insensitive** (e.g., "The" and "the" are the same word).
- **Return a mapping** of each unique word to its count.

#### Example

**Input:**
```
"Hello, world! Hello bootcamp students."
```

**Expected Output:**
```json
{
  "hello": 2,
  "world": 1,
  "bootcamp": 1,
  "students": 1
}
```

#### Bonus

- Handle unicode strings (e.g. `Café au lait 😊 café Café! Straße straße`)
- Refactor the function to return the top N most frequent words
- How could we handle extrememly large sequences of text?
