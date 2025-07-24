
# 🧭 Linux Navigation Guide

Navigation is essential—much like using a mouse in Windows. It allows us to move across the system, work within directories and files, and retrieve exactly what we need. Using a combination of commands and tools, we can efficiently explore and manage our Linux environment.

---

## 📍 Current Directory: `pwd`

To find out where you are in the system:

```bash
cry0l1t3@htb[~]$ pwd
/home/cry0l1t3
```

---

## 📂 Listing Directory Contents: `ls`

To list the contents of the current directory:

```bash
cry0l1t3@htb[~]$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

### 🔍 Long Listing Format: `ls -l`

```bash
cry0l1t3@htb[~]$ ls -l
```

#### Example Output:
```
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:37 Desktop
```

| Column | Description |
|--------|-------------|
| `drwxr-xr-x` | Type and permissions |
| `2` | Number of hard links |
| `cry0l1t3` | Owner |
| `htbacademy` | Group |
| `4096` | Size (in bytes or blocks) |
| `Nov 13 17:37` | Last modified date/time |
| `Desktop` | Directory/File name |

### 🕶️ Showing Hidden Files: `ls -la`

```bash
cry0l1t3@htb[~]$ ls -la
```

This displays **all** files, including hidden ones starting with `.` like `.bashrc`.

---

## 📁 Listing a Specific Path

You don’t have to be inside a directory to list its contents:

```bash
cry0l1t3@htb[~]$ ls -l /var/
```

---

## 🚶 Changing Directories: `cd`

You can move to a directory by specifying its name or full path:

```bash
cry0l1t3@htb[~]$ cd /dev/shm
```

### 🔙 Return to Previous Directory

```bash
cry0l1t3@htb[/dev/shm]$ cd -
```

---

## ⚡ Auto-completion with [TAB]

Using the `[TAB]` key helps auto-complete paths:

```bash
cry0l1t3@htb[~]$ cd /dev/s[TAB][TAB]
shm/ snd/
```

Type more letters to narrow it down:

```bash
cd /dev/shm
```

---

## 📌 Special Directory Entries

Inside a directory:

```bash
cry0l1t3@htb[/dev/shm]$ ls -la
```

You’ll often see:

- `.` → current directory
- `..` → parent directory

### 🔝 Move to Parent Directory

```bash
cry0l1t3@htb[/dev/shm]$ cd ..
```

---

## 🧼 Cleaning Up: `clear`

Return to `/dev/shm` and clean the terminal:

```bash
cry0l1t3@htb[/dev]$ cd shm && clear
```

### 💡 Shortcut

Use `[Ctrl] + [L]` to clear the terminal screen.

---

## ⏮️ Command History

- Use `↑` and `↓` arrows to scroll through command history.
- Use `[Ctrl] + [R]` to **search** through command history.

---

## 🧪 Tips

- Experiment often to get comfortable with commands.
- Use a **snapshot** of your VM before major changes.
- Explore different flags and options with commands like `ls`, `cd`, etc.

---

## ✅ Summary Commands

| Command | Description |
|--------|-------------|
| `pwd` | Show current directory |
| `ls` | List contents |
| `ls -l` | Long list format |
| `ls -la` | Show all, including hidden |
| `cd <dir>` | Change directory |
| `cd -` | Return to previous directory |
| `cd ..` | Move to parent directory |
| `clear` | Clear terminal screen |
| `[Ctrl] + [L]` | Clear terminal screen (shortcut) |
| `[Ctrl] + [R]` | Search command history |
| `[TAB]` | Auto-complete paths/files |

---

📘 **Practice makes perfect. Keep exploring, and don’t be afraid to try new things.**