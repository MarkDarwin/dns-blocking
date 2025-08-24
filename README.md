
# 🛡️ DNS Blocking

Automated workflows to fetch, filter, and maintain DNS blocklists for privacy and security. The originaly lists worked but used too much memory. The adjustments below clean up the lists, but I am retaining functionality by adding the TLDs directly to the DNS server.

---

## 🚦 Workflow Status

| Blocklist Source | Workflow Status |
|------------------|:--------------:|
| NRD 14-day mini  | <img src="https://github.com/MarkDarwin/dns-blocking/actions/workflows/nrd-shrink.yml/badge.svg?style=for-the-badge&logo=githubactions&logoColor=white&label=✔️%20NRD%20Workflow&color=green" alt="✔️ NRD Workflow Status" /> |
| Fakenews-Gambling-Porn | <img src="https://github.com/MarkDarwin/dns-blocking/actions/workflows/fakenews-gambling-porn-shrink.yml/badge.svg?style=for-the-badge&logo=githubactions&logoColor=white&label=✔️%20Fakenews%20Workflow&color=green" alt="✔️ Fakenews Workflow Status" /> |

---

## 📋 Overview

This project processes and maintains two DNS blocklists:

- **NRD 14-day mini domains-only** ([source](https://raw.githubusercontent.com/xRuffKez/NRD/refs/heads/main/lists/14-day-mini/domains-only/nrd-14day-mini.txt))
	- Filters out domains ending with `.ru`, `.cn`, `.kp`, `.zip`, `.by` to reduce memory footprint.
	- The filtered list is saved as `lists/nrd-14day-mini-shrink.txt`.

- **StevenBlack Fakenews-Gambling-Porn-Only hosts** ([source](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling-porn-only/hosts))
	- Removes comment lines and the `0.0.0.0 ` prefix.
	- The cleaned list is saved as `lists/fakenews-gambling-porn-only-shrink.txt`.

---

## � How it works

### NRD Blocklist
1. Download the source list.
2. Filter out domains ending with specified TLDs:
	 ```
	 .ru .cn .kp .zip .by
	 ```
3. Save the result to `lists/nrd-14day-mini-shrink.txt`.

### Fakenews-Gambling-Porn-Only Blocklist
1. Download the source hosts file.
2. Remove comment lines and strip the `0.0.0.0 ` prefix.
3. Save the result to `lists/fakenews-gambling-porn-only-shrink.txt`.

---

## 📁 Output Files

- `lists/nrd-14day-mini-shrink.txt` — NRD blocklist (TLDs removed)
- `lists/fakenews-gambling-porn-only-shrink.txt` — Fakenews-Gambling-Porn-Only blocklist (comments removed, prefix stripped)

---

## 🖥️ Example Usage

Use these blocklists with your DNS server or ad-blocking solution to block unwanted domains efficiently.

---

## 🔗 Sources

- [xRuffKez/NRD](https://github.com/xRuffKez/NRD)
- [StevenBlack/hosts](https://github.com/StevenBlack/hosts)