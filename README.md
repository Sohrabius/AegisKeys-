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

- **Option B: Direct File**  
  Simply double-click `index.html` to open it directly in your browser.  
  > ⚠️ **Note:** Clipboard auto-clear and some cryptographic features may be restricted by browser security policies when using the `file://` protocol. For full functionality, Option A is recommended.

### 2. Create Your Vault
1. Enter a strong **Master Password** (minimum 6 characters, 12+ highly recommended).
2. Click **Create New Vault**.
3. ⚠️ **CRITICAL:** Click the 💾 icon in the sidebar to download your `api-vault.json` file.  
   > **If you lose this file and forget your password, your data is gone forever.** There is no recovery mechanism.

---

## 🛠️ Usage Guide

### ➕ Adding an API Key
1. Click **+ New API** in the left sidebar.
2. Fill in the required details:
   - **Name:** e.g., `OpenAI Production`
   - **Base URL:** e.g., `https://api.openai.com/v1`
   - **API Token:** Your secret key.
3. *(Optional)* Fill in additional metadata: **Provider**, **Model**, **Tags**, and **Notes**.
4. Click 💾 **Save**.
5. Click the 💾 **Export** icon in the sidebar to update and save your local JSON file.

### 🔑 Using a Key
1. Click on an API entry in the left sidebar to view its details.
2. Click **Copy** next to the token.  
   > 📋 The token is now in your clipboard and will **auto-clear in 30 seconds** for your security.
3. Click **📋 Copy cURL** to generate a ready-to-use `curl` command for quick testing.
4. Click **🧪 Test** to ping the API endpoint and verify that the key is valid and active.

---

## ⚠️ Security Best Practices
- Always back up your `api-vault.json` file in a secure location (e.g., encrypted drive or secure password manager).
- Never share your Master Password or your `api-vault.json` file.
- Use the local server method (`localhost`) whenever possible to ensure all browser security features function correctly.
