# Text Analysis using Python (NLP Basics)

A beginner-friendly NLP project that analyzes a given text and calculates the number of **words, characters, vowels, and repeated words** using Python.

> Task 6 · Level 1 · AI & ML Track

## Objective

Practice basic text-processing techniques that are useful in Natural Language Processing (NLP).

## Tools Used

- Python 3
- Jupyter Notebook
- `re` (regular expressions)
- `collections.Counter`

## Approach

1. **Input:** Store the paragraph in a string variable.
2. **Lowercasing:** Convert the text to lowercase so "Machine" and "machine" count as the same word.
3. **Tokenization:** Use `re.findall(r"[a-zA-Z']+", text)` to extract words. This removes punctuation, so `learning.` and `learning` are treated as one word (plain `split()` would count them separately).
4. **Word count:** `len(words)`
5. **Character count:** `len(text)` (with spaces) and `len(text.replace(" ", ""))` (without spaces)
6. **Vowel count:** Count characters present in `"aeiou"`
7. **Repeated words:** Use `Counter(words)` and keep words with a count greater than 1.

## Code

```python
from collections import Counter
import re

text = """Machine learning is a part of AI. Machine learning helps computers learn from data, and data is the key to learning."""

words = re.findall(r"[a-zA-Z']+", text.lower())

print("Words      :", len(words))
print("Characters :", len(text))
print("Chars (no spaces):", len(text.replace(" ", "")))
print("Vowels     :", sum(1 for c in text.lower() if c in "aeiou"))

counts = Counter(words)
repeated = {w: c for w, c in counts.items() if c > 1}
print("Repeated words:", repeated)
```

## Sample Output

| Metric | Result |
|---|---|
| Total words | 21 |
| Characters (with spaces) | 116 |
| Characters (without spaces) | 96 |
| Total vowels | 37 |

**Repeated words:** `learning` (3), `machine` (2), `is` (2), `data` (2)

## Outcome

The program correctly counts words, characters and vowels, and identifies repeated words. The most frequent word, "learning", matches the topic of the paragraph, showing how simple word-frequency analysis can reveal the main theme of a text.

## How to Run

```bash
git clone https://github.com/sanzayjanarthanan/text-analysis-nlp.git
cd text-analysis-nlp
jupyter notebook text_analysis.ipynb
```

No extra libraries are needed. `re` and `collections` are part of Python's standard library.

## Key Learnings

- Text preprocessing (lowercasing, tokenization) and why it matters
- Handling punctuation with regular expressions
- Using `Counter` for frequency analysis
- Foundation for advanced NLP: Bag of Words, TF-IDF, sentiment analysis

## Future Scope

- Remove stop words; apply stemming / lemmatization
- Visualize word frequencies with a bar chart or word cloud
- Build a Streamlit app where users paste any text and get instant analysis

## Author

**J Sanjay**
B.Tech AI & Data Science, Velammal Institute of Technology, Chennai
GitHub: [sanzayjanarthanan](https://github.com/sanzayjanarthanan)
