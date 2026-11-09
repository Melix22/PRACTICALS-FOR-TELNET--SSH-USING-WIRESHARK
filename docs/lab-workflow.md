# Lab Workflow: Examining Telnet and SSH in Wireshark

## 1. Prepare the lab
1. Start the CyberOps Workstation VM and the router/device or lab topology specified by your instructor.
2. Confirm connectivity and record the lab IP addresses and interface name in your notes.
3. Use test-only credentials. Do not use production systems or real account passwords.
4. Open Wireshark and select the interface that carries traffic between the workstation and lab device.

> **Important:** This guide does not assume a particular router model, interface name, IP address, or topology. Follow your supplied lab handout for those details.

## 2. Part 1 — Capture a Telnet session
1. In Wireshark, start capturing on the correct interface.
2. From the workstation, connect to the lab device using the Telnet command required by your course environment, for example:
   ```bash
   telnet <LAB_DEVICE_IP>
   ```
3. Log in with test credentials if prompted. Type a harmless test command, then exit the session.
4. Stop the capture.
5. Apply this Wireshark display filter:
   ```text
   telnet
   ```
   If your lab uses TCP port 23 and Wireshark does not automatically decode it, inspect the TCP conversation and use **Analyze → Decode As** only if appropriate for your lab.
6. Select a Telnet packet and inspect **Packet Details** and **Packet Bytes**. In an authorized test session, observe whether typed test data appears in readable form.
7. Save the capture as `evidence/telnet/telnet-session.pcapng` if course rules permit. Otherwise keep it local and document the filename in your report.
8. Save screenshots in `screenshots/telnet/`, showing the filter, relevant packet details, and readable test data only if it is safe and permitted.

## 3. Part 2 — Capture an SSH session
1. Start a fresh Wireshark capture on the same relevant interface.
2. Connect to the same lab device using SSH, as supported by the course setup:
   ```bash
   ssh <LAB_USERNAME>@<LAB_DEVICE_IP>
   ```
3. Authenticate using a lab-only account and run a harmless test command.
4. Exit the SSH session and stop the capture.
5. Apply the display filter:
   ```text
   ssh
   ```
   You may also inspect the TCP conversation if needed.
6. Inspect the initial SSH protocol/key-exchange packets and subsequent traffic. SSH application data should not be readable as plain-text commands in the capture after encryption is established.
7. Save the capture as `evidence/ssh/ssh-session.pcapng` if permitted, or retain it locally and record the filename in the report.
8. Save screenshots in `screenshots/ssh/`.

## 4. Compare and document
Complete `reports/findings.md` using your own observations. Include:
- Capture interface and lab endpoint details allowed by your course policy
- Filters used
- What you could and could not read in each capture
- How encryption changes confidentiality
- Screenshot filenames and any limitations

## 5. Evidence checklist
- [ ] Telnet capture completed
- [ ] Telnet display-filter screenshot saved
- [ ] Telnet packet details/bytes screenshot saved, with test data only
- [ ] SSH capture completed
- [ ] SSH display-filter screenshot saved
- [ ] SSH packet details screenshot saved
- [ ] Findings report completed
- [ ] Sensitive information removed or kept out of the public repository

## 6. Push to GitHub using Git Bash
### A. Create an empty GitHub repository
Create a repository named `telnet-ssh-wireshark-lab`. Do not initialize it with a README, license, or `.gitignore`, because these are already included in this project.

### B. Extract and open the project
Extract the downloaded ZIP file. In File Explorer, open the extracted folder, right-click and choose **Open Git Bash here** (or navigate to it with `cd`).

Example path (replace with your actual folder path):
```bash
cd "/c/Users/YourUser/Downloads/telnet-ssh-wireshark-lab"
```

### C. Initialize and commit
Run these commands one at a time:
```bash
git --version
git init
git branch -M main
git status
git add README.md docs evidence screenshots reports .gitignore .github
git status
git commit -m "Add Telnet and SSH Wireshark lab workflow"
```
If Git asks you to configure your identity, use your own GitHub name and email:
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
Then repeat the commit command. Do not use someone else's identity.

### D. Connect and push
Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username:
```bash
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/telnet-ssh-wireshark-lab.git
git push -u origin main
```
GitHub may prompt you to authenticate in a browser or with an approved credential method. Do not put passwords or tokens directly in commands or files.

If you already configured a remote, check it first:
```bash
git remote -v
```
If `origin` already exists, do not repeat `git remote add origin`; update it only if necessary:
```bash
git remote set-url origin https://github.com/YOUR_GITHUB_USERNAME/telnet-ssh-wireshark-lab.git
```

## 7. Verify
Refresh your GitHub repository page and confirm the README, docs, screenshots/evidence folders, and report are present. Empty folders are represented by `.gitkeep` files until you add evidence.
