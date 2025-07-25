
# Regular Expressions (RegEx) Summary

Regular expressions (RegEx) are powerful tools used for searching, matching, and manipulating text based on specific patterns. They are supported in many programming languages and command-line tools like `grep` and `sed`.

---

## 📌 What is RegEx?

RegEx is a sequence of characters that defines a search pattern. It can be used for:

- Searching text
- Replacing text
- Validating input (e.g., emails, phone numbers)
- Analyzing data

Metacharacters in RegEx allow defining the structure of the pattern rather than matching exact text.

---

## 🧩 Grouping & Operators

RegEx provides grouping mechanisms using various brackets and symbols:

| Operator     | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `(a)`        | Groups parts of a RegEx to process together                                 |
| `[a-z]`      | Character class – matches any character in the specified range              |
| `{1,10}`     | Quantifier – specifies how often the previous element should occur          |
| `|`          | OR operator – matches if either expression is found                         |
| `.*`         | Greedy match – matches any character (AND-like behavior in some cases)      |

---

## 🧪 Examples

### OR Operator (`|`)

Searches for lines that contain **either** "my" **or** "false":

```bash
grep -E "(my|false)" /etc/passwd
```

**Example Output:**

```bash
lxd:x:105:65534::/var/lib/lxd/:/bin/false
pollinate:x:109:1::/var/cache/pollinate:/bin/false
mysql:x:116:120:MySQL Server,,:/nonexistent:/bin/false
```

---

### AND Operator Simulation (`.*` or piped grep)

Searches for lines that contain **both** "my" **and** "false" in order:

```bash
grep -E "(my.*false)" /etc/passwd
```

**Example Output:**

```bash
mysql:x:116:120:MySQL Server,,:/nonexistent:/bin/false
```

Alternatively, use two `grep` commands:

```bash
grep -E "my" /etc/passwd | grep -E "false"
```

**Same Output:**

```bash
mysql:x:116:120:MySQL Server,,:/nonexistent:/bin/false
```

---

## ✅ Summary

- Use `()` for grouping patterns.
- Use `[]` for matching character ranges.
- Use `{}` for specifying repetition.
- Use `|` for OR conditions.
- Combine expressions or pipe `grep` for AND-like behavior.

RegEx is an essential tool for developers, system admins, and data analysts. Practice is key to mastering its syntax and power.

---

**Tip**: Use online tools like [regex101.com](https://regex101.com/) to test and learn RegEx patterns.
