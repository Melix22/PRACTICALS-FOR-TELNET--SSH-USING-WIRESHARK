# Quick Reference

Use only commands supported by your lab environment and instructor's instructions.

## Connection examples
```bash
telnet <LAB_DEVICE_IP>
ssh <LAB_USERNAME>@<LAB_DEVICE_IP>
```

## Wireshark display filters
```text
telnet
ssh
tcp.port == 23
tcp.port == 22
```

Port filters are useful only when the lab uses the standard Telnet (TCP/23) and SSH (TCP/22) ports.

## Git Bash
```bash
git --version
git init
git branch -M main
git status
git add .
git commit -m "Add Telnet and SSH Wireshark lab workflow"
git remote -v
git push -u origin main
```

## Common Git troubleshooting
- **`fatal: remote origin already exists`:** run `git remote -v`, then use `git remote set-url origin <REPOSITORY_URL>` if the existing URL is wrong.
- **`nothing to commit`:** run `git status`; files may already be committed or ignored.
- **Authentication failed:** complete GitHub's browser/credential-manager sign-in or configure an approved authentication method. Do not paste a password or token into the repository.
- **Capture file is too large or sensitive:** keep the raw capture locally and commit a sanitized report/screenshots only if permitted by your course.
