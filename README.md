
# 🧠 AI-Powered Code Auto-Fixer

A smart, free tool that uses Python’s AST (Abstract Syntax Tree) and Hugging Face Transformers to detect and automatically fix code issues — like unused imports — and enhance your code quality.

## 🚀 Features

* ✅ **Static analysis** using Python's `ast` module.
* 🔍 Detects **unused imports** and variables.
* 🤖 AI-powered **code suggestions** using `CodeBERTa-small-v1`.
* 🧾 **Unified diff** output to see what's changed.
* 🛠 No need for paid tools or plugins — **100% open source and free**!

---

## 📦 Tech Stack

* **Python 3.8+**
* `ast`: Built-in static code parser
* `transformers`: From Hugging Face (`text2text-generation` pipeline)
* `difflib`: Standard library for comparing code versions
* Model: [`huggingface/CodeBERTa-small-v1`](https://huggingface.co/huggingface/CodeBERTa-small-v1)

---

## 🧑‍💻 How It Works

1. **AST-Based Static Analysis**

   * Walks through Python code using `ast.NodeVisitor`.
   * Collects all `import` statements and all used variable names.
   * Flags unused imports by comparing what's imported vs. what's used.

2. **AI-Powered Fixing**

   * Sends the issue and original code to a Hugging Face transformer model.
   * Returns a suggested code fix.

3. **Diff Comparison**

   * Uses `difflib.unified_diff` to show before-and-after comparison of code.

---

## 🧪 Example

### Original Code:

```python
import os
import sys
import math

def example():
    print(math.pi)
```

### Output:

```
Detected Issues: {'unused_imports': ['os', 'sys']}

Suggested Fix:
import math

def example():
    print(math.pi)
```

