# Examining Telnet and SSH in Wireshark

**Suggested repository name:** `telnet-ssh-wireshark-lab`

## Project overview
This lab compares a Telnet session with an SSH session by capturing traffic in Wireshark and examining what the packet data reveals about confidentiality. Telnet sends session data without encryption; SSH encrypts the session after negotiation, so application data is not readable as plain text in the capture.

> **Lab safety:** Perform captures only in your own authorized, isolated lab environment. Use test credentials, never real passwords, and do not capture other people's traffic.

## Objectives
- Capture and inspect a Telnet session in Wireshark.
- Identify Telnet protocol traffic and observe readable session data where applicable.
- Capture and inspect an SSH session.
- Identify SSH negotiation/traffic and compare visibility with Telnet.
- Record findings with screenshots and a short conclusion.

## Repository layout
```text
telnet-ssh-wireshark-lab/
├── README.md
├── .gitignore
├── .github/
│   └── workflows/
│       └── markdown-check.yml
├── docs/
│   ├── lab-workflow.md
│   ├── findings-template.md
│   └── commands-reference.md
├── evidence/
│   ├── README.md
│   ├── telnet/
│   │   └── .gitkeep
│   └── ssh/
│       └── .gitkeep
├── screenshots/
│   ├── README.md
│   ├── telnet/
│   │   └── .gitkeep
│   └── ssh/
│       └── .gitkeep
└── reports/
    └── findings.md
```

## Requirements
- CyberOps Workstation virtual machine (as specified by the lab handout)
- Wireshark
- An authorized router/device or lab endpoint configured to accept Telnet and SSH
- Git and Git Bash
- A GitHub account and an empty repository

The exact interface names, IP addresses, router credentials, and topology depend on your course lab. Use the values given by your instructor; examples in the workflow are placeholders.

## Start here
1. Read [`docs/lab-workflow.md`](docs/lab-workflow.md).
2. Follow your course topology and capture Telnet traffic in Wireshark.
3. Save your own capture as `evidence/telnet/telnet-session.pcapng`.
4. Capture SSH traffic and save it as `evidence/ssh/ssh-session.pcapng`.
5. Add screenshots to the matching folders and complete [`reports/findings.md`](reports/findings.md).
6. Follow the Git Bash instructions in the workflow document to push the project to GitHub.

## Evidence and privacy
Before committing a capture, inspect it for real usernames, passwords, IP addresses, or other sensitive information. Use only test credentials. If course policy prohibits publishing packet captures, keep the `.pcapng` files locally and commit only sanitized screenshots and written findings. Never commit passwords, private keys, tokens, or real customer data.

## Expected outcome
A well-organized repository containing the procedure, sanitized screenshots/captures where permitted, and a comparison of Telnet versus SSH. Do not claim a step is completed until you have performed it and recorded your own evidence.
