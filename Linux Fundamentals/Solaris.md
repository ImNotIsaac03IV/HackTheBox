
# Solaris Operating System - Learning Summary

## What is Solaris?

Solaris is a Unix-based operating system developed by Sun Microsystems, now maintained by Oracle. It's designed for enterprise environments requiring:

- **High performance**
- **Security**
- **Stability**
- **Scalability**

It supports advanced technologies like Oracle VM Server for SPARC and is widely used in data centers, financial services, and government systems.

---

## Key Features of Solaris

- **Robust performance on high-end hardware**
- **Virtualization with Oracle VM Server for SPARC**
- **High Availability and Fault Tolerance**
- **RBAC and mandatory access control**
- **Service Management Facility (SMF)**
- **Image Packaging System (IPS)** for package management

---

## Comparison: Solaris vs Linux Distributions

| Feature              | Solaris                                      | Linux Distributions              |
|----------------------|----------------------------------------------|----------------------------------|
| Source Code          | Proprietary (Closed)                         | Open Source                      |
| Package Manager      | IPS, pkgadd                                  | APT, YUM, DNF                    |
| File System Tool     | SMF                                          | ZFS (on some distros), systemd  |
| Security             | RBAC, MAC                                    | Mostly DAC, some RBAC support   |
| Virtualization       | Oracle VM Server for SPARC                   | KVM, QEMU, Docker                |
| Process Debugging    | truss, pfiles                                | strace, lsof                     |

---

## Important Solaris Directories

| Directory     | Description |
|---------------|-------------|
| `/`           | Root directory |
| `/bin`        | Essential binaries |
| `/boot`       | Boot-related files |
| `/dev`        | Device files |
| `/etc`        | Configuration files |
| `/home`       | User home directories |
| `/kernel`     | Kernel modules |
| `/lib`        | Libraries for binaries |
| `/mnt`        | Temporary mount points |
| `/opt`        | Optional software |
| `/proc`       | Process info as files |
| `/sbin`       | System administration binaries |
| `/tmp`        | Temporary files |
| `/usr`        | Read-only data and apps |
| `/var`        | Variable data like logs |

---

## Command Comparisons

### System Information

**Linux (Ubuntu):**

```bash
uname -a
```

**Solaris:**

```bash
showrev -a
```

### Installing Packages

**Linux (Ubuntu):**

```bash
sudo apt-get install apache2
```

**Solaris:**

```bash
pkgadd -d SUNWapchr
```

### Permission Management

**Find SUID Files**

**Linux:**

```bash
find / -perm 4000
```

**Solaris:**

```bash
find / -perm -4000
```

### NFS Sharing

**Solaris Share Directory:**

```bash
share -F nfs -o rw /export/home
```

**Mount NFS Share:**

```bash
mount -F nfs 10.129.15.122:/nfs_share /mnt/local
```

**Config File:**

```bash
cat /etc/dfs/dfstab
```

---

## Process Mapping

**Linux:**

```bash
sudo lsof -c apache2
```

**Solaris:**

```bash
pfiles `pgrep httpd`
```

---

## Tracing System Calls

**Linux:**

```bash
sudo strace -p `pgrep apache2`
```

**Solaris:**

```bash
truss ls
```

- `truss` can trace signals and child processes
- `strace` is limited to the specified process

---

**Learning Tip:** Practice cross-platform comparisons by running the same tasks on both Ubuntu and Solaris virtual machines. Use command documentation (`man <command>`) to dive deeper.
