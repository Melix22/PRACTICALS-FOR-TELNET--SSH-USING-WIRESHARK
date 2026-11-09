# Findings Template

Copy your completed observations into `reports/findings.md`.

## Environment
- VM/workstation:
- Lab device/model (if required by course):
- Capture interface:
- Date of capture:
- Test account used (never include its password):

## Part 1 — Telnet
- Display filter used:
- What packet/protocol details were visible?
- Could test input be read as plain text? Describe your observation without publishing secrets.
- Screenshot filenames:
- Capture filename or local-only location:

## Part 2 — SSH
- Display filter used:
- What was visible during protocol negotiation?
- Could application commands be read as plain text after encryption was established?
- Screenshot filenames:
- Capture filename or local-only location:

## Comparison
| Observation | Telnet | SSH |
|---|---|---|
| Standard TCP port (if used) | 23 | 22 |
| Application data encrypted | No | Yes, after SSH encryption is established |
| Credentials/session content visible as plain text | Can be, depending on the captured exchange | Should not be after encryption is established |
| Recommended for secure remote administration | No | Yes |

## Conclusion
Write 3–5 sentences explaining what your own capture showed, why encryption matters, and why SSH is preferred over Telnet for remote administration.

## Limitations / notes
- Note any capture, permission, or topology limitations.
- Confirm that no real passwords, private keys, or customer data are included in the public repository.
