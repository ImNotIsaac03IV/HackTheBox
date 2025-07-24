
# Linux Filtering and Viewing Tools

This guide summarizes key Linux tools used to filter and view file contents and command output.

---

## 📄 Viewing File Contents: `more` and `less`

### `more`

- Views file contents one screen at a time.
- Leaves output in the terminal.
  
```bash
cat /etc/passwd | more
```

### `less`

- More feature-rich than `more`.
- Output does **not** stay in terminal after exiting.
  
```bash
less /etc/passwd
```

---

## 🔍 Head & Tail

### `head`

- Shows first 10 lines by default.
  
```bash
head /etc/passwd
```

### `tail`

- Shows last 10 lines.
  
```bash
tail /etc/passwd
```

---

## 🔠 Sorting with `sort`

- Alphabetically sorts file content.
  
```bash
cat /etc/passwd | sort
```

---

## 🔎 Searching with `grep`

### Basic search

```bash
cat /etc/passwd | grep "/bin/bash"
```

### Exclude lines

```bash
cat /etc/passwd | grep -v "false\|nologin"
```

---

## ✂️ Cutting with `cut`

- Extract specific fields using delimiters.
  
```bash
cat /etc/passwd | grep -v "false\|nologin" | cut -d":" -f1
```

---

## 🔄 Replacing with `tr`

- Replaces characters.
  
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " "
```

---

## 📊 Formatting with `column`

- Neatly formats output in columns.
  
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | column -t
```

---

## 🧠 Parsing with `awk`

- Prints selected fields (`$1` = first, `$NF` = last).
  
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}'
```

---

## ✏️ Editing with `sed`

- Replace text using regular expressions.
  
```bash
... | sed 's/bin/HTB/g'
```

---

## 🔢 Counting with `wc`

- Count lines of output.
  
```bash
... | wc -l
```

---

## ✅ Example: Count Active Bash Users

```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | wc -l
```

---

Study and practice each tool to gain confidence with processing output on the command line!
