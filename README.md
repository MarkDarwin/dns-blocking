# 🛡️ DNS Blocking

## 📋 Overview

This project processes a domain blocklist for DNS filtering. We take the list from [xRuffKez/NRD 14-day mini domains-only](https://raw.githubusercontent.com/xRuffKez/NRD/refs/heads/main/lists/14-day-mini/domains-only/nrd-14day-mini.txt) and remove domains ending with the following TLDs:

```
.ru .cn .kp .zip .by
```

We remove these TLDs from the blocklist to reduce the memory footprint on the DNS server. However, we block the entire TLD zones (e.g., `.ru`, `.cn`, etc.) directly on the DNS server, so the net result is the same: all domains from these TLDs are still blocked, just more efficiently.

The filtered list is saved as:

`lists/nrd-14day-mini-shrink.txt`

## 🚀 How it works

1. Download the source list from the URL above.
2. Filter out any domains ending with the specified TLDs.
3. Save the result to `lists/nrd-14day-mini-shrink.txt`.

## 📁 Files

- `lists/nrd-14day-mini-shrink.txt` — Filtered blocklist (TLDs removed)

## 🖥️ Example usage

You can use the filtered blocklist with your DNS server or ad-blocking solution to avoid unwanted domains from the specified TLDs.

---
🔗 Source: [xRuffKez/NRD](https://github.com/xRuffKez/NRD)