# Backup and Restore in Linux

Linux offers robust tools to back up and restore data. These tools ensure secure, efficient, and reliable management of information.

---

## 🔧 Common Backup Tools

| Tool       | Description |
|------------|-------------|
| **Rsync**  | Fast, incremental backup tool; great for local and remote backups. |
| **Duplicity** | Builds on rsync with added encryption for secure backups. |
| **Deja Dup** | GUI front-end for duplicity, ideal for simple encrypted backups. |

---

## 🛠️ Installing Rsync

```bash
sudo apt install rsync -y
```

---

## 📁 Rsync Usage

### Backup a Local Directory to a Remote Server

```bash
rsync -av /path/to/mydirectory user@backup_server:/path/to/backup/directory
```

### Incremental Backup with Compression & Delete

```bash
rsync -avz --backup --backup-dir=/path/to/backup/folder --delete /path/to/mydirectory user@backup_server:/path/to/backup/directory
```

### Restore from Backup Server

```bash
rsync -av user@remote_host:/path/to/backup/directory /path/to/mydirectory
```

---

## 🔒 Secure Rsync with SSH

```bash
rsync -avz -e ssh /path/to/mydirectory user@backup_server:/path/to/backup/directory
```

---

## 🔁 Automate Backup with Cron

1. **Generate SSH Key**

```bash
ssh-keygen -t rsa -b 2048
```

2. **Copy Key to Server**

```bash
ssh-copy-id user@backup_server
```

3. **Create Script**

`RSYNC_Backup.sh`:

```bash
#!/bin/bash
rsync -avz -e ssh /path/to/mydirectory user@backup_server:/path/to/backup/directory
```

4. **Make Script Executable**

```bash
chmod +x RSYNC_Backup.sh
```

5. **Schedule with Cron**

```bash
crontab -e
```

Add:

```bash
0 * * * * /path/to/RSYNC_Backup.sh
```

---

## 🧠 Summary

- **Rsync** is efficient and ideal for backups.
- **Duplicity** adds encryption on top of rsync.
- **Deja Dup** is user-friendly with encryption support.
- Secure backups with SSH.
- Automate with cron and key-based SSH.

Always encrypt sensitive data and schedule regular backups to ensure system reliability and disaster recovery readiness.