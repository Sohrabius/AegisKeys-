# 🛡️ AegisKeys

**A zero-knowledge, local-first AI API Token Manager.**

AegisKeys is a single-file, browser-based vault for securely storing, managing, and using AI API credentials (OpenAI, Anthropic, Google, Mistral, etc.). It encrypts your data locally using military-grade cryptography and never sends your keys over the network.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Web Crypto](https://img.shields.io/badge/Crypto-AES--256--GCM-blue?style=flat)
![Zero Backend](https://img.shields.io/badge/Backend-None-brightgreen?style=flat)

---

## ✨ Features

- **🔐 Military-Grade Encryption:** AES-256-GCM encryption with PBKDF2 key derivation (250,000 iterations).
- **🕵️ Zero-Knowledge:** Your master password is never stored, logged, or transmitted. It only exists in ephemeral memory.
- **📦 Single File App:** The entire application is one `index.html` file. No build steps, no npm, no dependencies.
- **📂 Portable JSON Storage:** Your encrypted data is saved as a standard `api-vault.json` file. Store it anywhere (Dropbox, Git, USB).
- **👁️ Privacy-First UI:** Tokens are masked by default. "Show" buttons auto-hide after 12 seconds.
- **📋 Safe Clipboard:** Copied tokens are automatically wiped from your clipboard after 30 seconds.
- **🔒 Auto-Lock:** Automatically locks the vault after 5 minutes of inactivity.
- **🧪 Built-in Testing:** One-click API connection testing to verify your keys are working.
- **🏷️ Rich Metadata:** Add tags, notes, default models, and custom auth headers to each key.

---

## 🚀 Getting Started

### 1. Run the App
Because AegisKeys uses the Web Crypto API and Clipboard API, it works best when served over HTTP (even locally). 

**Option A: Quick Local Server (Recommended)**
```bash
# If you have Python installed:
python -m http.server 8000

# Or use Node.js (npx serve):
npx serve .
```

Then open http://localhost:8000 in your browser.
Option B: Direct File
Simply double-click index.html to open it in your browser. (Note: Clipboard auto-clear and some crypto features may be restricted by browser security policies when using the file:// protocol).
2. Create Your Vault
Enter a strong Master Password (minimum 6 characters, 12+ recommended).
Click Create New Vault.
CRITICAL: Click the 💾 icon in the sidebar to download your api-vault.json file. If you lose this file and forget your password, your data is gone forever.
🛠️ Usage Guide
Adding an API Key
Click + New API in the left sidebar.
Fill in the details:
Name: e.g., "OpenAI Production"
Base URL: e.g., https://api.openai.com/v1
API Token: Your secret key.
(Optional) Provider, Model, Tags, and Notes.
Click 💾 Save.
Click the 💾 Export icon in the sidebar to update your JSON file.
Using a Key
Click on an API entry in the sidebar.
Click Copy next to the token. It is now in your clipboard (and will auto-clear in 30s).
Click 📋 Copy cURL to get a ready-to-use curl command for testing.
Click 🧪 Test to ping the API and verify the key is valid.
