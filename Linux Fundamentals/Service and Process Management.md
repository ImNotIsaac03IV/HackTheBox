
# 🛠️ Linux Service and Process Management

## 🔧 What Are Services (Daemons)?

- **Services (daemons)** run in the background and perform critical system tasks.
- Named with a trailing `d` (e.g., `sshd`, `systemd`).

### Types

1. **System Services** – Essential for system startup (e.g., init, systemd).
2. **User-Installed Services** – Add-ons like web servers (e.g., Apache).

---

## 🚀 Common Service Goals

- Start/Restart
- Stop
- Status check
- Enable/Disable on boot
- Locate services

---

## 🧰 `systemctl` Commands

| Command | Description |
|--------|-------------|
| `systemctl start ssh` | Start SSH service |
| `systemctl status ssh` | Check service status |
| `systemctl enable ssh` | Enable service on boot |
| `systemctl list-units --type=service` | List active services |
| `journalctl -u ssh.service` | View service logs |

---

## 📋 Viewing Processes

```bash
ps aux | grep <process>
```

### Example

```bash
ps aux | grep ssh
```

---

## 🔪 Killing Processes

| Command | Description |
|---------|-------------|
| `kill <PID>` | Send default SIGTERM |
| `kill -9 <PID>` | Force kill (SIGKILL) |
| `kill -l` | List all signals |
| `pkill <name>` | Kill by process name |
| `killall <name>` | Kill all with name |

### Most used signals

- `1` – SIGHUP
- `2` – SIGINT (Ctrl+C)
- `9` – SIGKILL
- `15` – SIGTERM
- `20` – SIGTSTP (Ctrl+Z)

---

## ⏸️ Background/Foreground Process Management

### Suspend a process

`[Ctrl + Z]` → sends `SIGTSTP`

### View jobs

```bash
jobs
```

### Resume in background

```bash
bg
```

### Bring to foreground

```bash
fg <job_id>
```

### Run in background directly

```bash
ping -c 10 example.com &
```

---

## ⛓️ Execute Multiple Commands

| Operator | Description |
|----------|-------------|
| `;` | Run all commands regardless of success |
| `&&` | Only run next if previous succeeds |
| `|` | Pipe output of one to another |

### Examples

```bash
echo '1'; echo '2'; echo '3'
echo '1' && echo '2' && echo '3'
cat file.txt | grep "error"
```

---

## 🧠 Summary

- Use `systemctl` for managing services.
- Use `ps`, `jobs`, `fg`, `bg` for process control.
- Use `kill`, `pkill`, `killall` for process termination.
- Use `&&`, `;`, `|` to chain commands efficiently.

---

Happy Hacking! 🎯
