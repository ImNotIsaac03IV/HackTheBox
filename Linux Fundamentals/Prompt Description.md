# Bash Prompt Summary

## What is the Bash Prompt?

- The bash prompt is a line of text in the terminal indicating the system is ready for commands.
- It typically shows:
  - **Username** (who you are)
  - **Hostname** (computer's name)
  - **Current working directory** (folder you're in)
- The prompt ends with a symbol:
  - `$` for a regular user
  - `#` for the root (privileged user)

Example:
- username@hostname[~]$
- root@hostname[/root]#


- The home directory is shown as a tilde `~`.

---

## PS1 Variable

- The **PS1** environment variable controls the appearance of the bash prompt.
- You can customize it to show various information:
  - Username
  - Hostname
  - Current directory (full path or just name)
  - Date and time
  - IP address
  - Status of last command (success/failure)
- This customization helps during tasks like penetration testing by providing useful context directly in the prompt.

---

## Common PS1 Special Characters

| Character | Description                          | Example Output          |
| --------- | ---------------------------------- | -----------------------|
| `\u`      | Current username                   | `user`                 |
| `\h`      | Hostname (short)                  | `hostname`             |
| `\H`      | Full hostname                    | `hostname.domain.com`  |
| `\w`      | Full path of current directory   | `/home/user/projects`  |
| `\d`      | Date (e.g., Mon Feb 6)            | `Mon Feb 6`            |
| `\D{format}` | Date in custom format (e.g., `%Y-%m-%d`) | `2025-07-23`          |
| `\t`      | Current time (24-hour HH:MM:SS)  | `14:30:15`             |
| `\T`      | Current time (12-hour HH:MM:SS)  | `02:30:15`             |
| `\@`      | Current time (12-hour with AM/PM) | `2:30 PM`              |
| `\j`      | Number of jobs managed by shell  | `0`                    |
| `\n`      | Newline                          | *(creates a new line)* |
| `\r`      | Carriage return                  | *(resets cursor to line start)* |
| `\s`      | Name of the shell                | `bash`                 |

---

## When PS1 Is Not Set

- The prompt may appear very simple:
  - `$` for normal users
  - `#` for root users
- This often happens when running shells remotely or via limited shells.

---

## Additional Notes

- Bash prompt can be further enhanced with:
  - Colors
  - Fonts
  - Other visual settings
- Tools to create advanced prompts:
  - **bash-prompt-generator**
  - **powerline**

---

## Summary

- The bash prompt gives important context in the terminal.
- Customizing the PS1 variable helps tailor the prompt to your needs.
- Including time, date, IP, or command status can improve workflow, especially in security testing.
- The home directory is represented as `~`.
- Root user prompt ends with `#`, regular users with `$`.

---