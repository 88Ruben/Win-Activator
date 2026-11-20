````markdown
# 🪟 Decrypt Empire

> A PowerShell tool to **activate Windows with a legitimate license** and check activation status.

![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📖 Overview

**Decrypt Empire** simplifies Windows activation by relying on Microsoft's official tools (`slmgr.vbs`, `DISM`). It lets you:

- 🔑 Install and activate an **official product key** (retail, OEM, MAK)
- 🏢 Connect to an **organization's KMS server** (volume licensing)
- 🔍 Display the **license status** (type, channel, expiration)
- 🧾 Generate an **activation report**

> ⚠️ This project **does not bypass** Windows protection. A valid license is required.

---

## 📋 Requirements

- Windows 10 or 11
- PowerShell 5.1 or higher
- **Administrator** rights
- A **valid Windows license**

---

## 🚀 Installation

```powershell
git clone https://github.com/your-username/DecryptEmpire.git
cd DecryptEmpire
```

---

## 🛠️ Usage

Open PowerShell **as Administrator**:

```powershell
# Check activation status
.\DecryptEmpire.ps1 -Action status

# Activate with a product key
.\DecryptEmpire.ps1 -Action activate-key -ProductKey "XXXXX-XXXXX-XXXXX-XXXXX-XXXXX"

# Activate via your organization's KMS server
.\DecryptEmpire.ps1 -Action activate-kms -KmsServer "kms.your-company.local"

# Generate a report
.\DecryptEmpire.ps1 -Action report -Output report.json
```

---

## ⚙️ How It Works

The script only calls official commands:

```text
slmgr /ipk <key>      → installs the product key
slmgr /skms <server>  → sets the KMS server
slmgr /ato            → triggers activation
slmgr /dlv            → displays detailed license information
```

---

## 🧯 Troubleshooting

| Error | Likely Cause | Solution |
|---|---|---|
| `0xC004F050` | Invalid key for this edition | Check your edition and key |
| `0xC004F074` | KMS server unreachable | Check network, DNS, and port 1688 |
| `0xC004C003` | Key blocked or already used | Contact Microsoft support |

---

## 🤝 Contributing

1. Fork the repository
2. Create a branch: `git checkout -b feature/my-feature`
3. Commit and push your changes
4. Open a **Pull Request**

---

## 📄 License

Distributed under the **MIT** license. See the `LICENSE` file.

## ⚖️ Disclaimer

This project is not affiliated with or endorsed by Microsoft. "Windows" is a registered trademark of Microsoft Corporation. Users are responsible for holding a valid license for the software they activate.
````
