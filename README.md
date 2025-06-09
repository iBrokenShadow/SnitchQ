# SnitchQ
SnitchQ – A Telegram bot that uses LLMs to detect scams in forwarded messages. 🔍 No cloud. No logs. Just pure AI-powered scam sniffing. Built with Node.js + Telegraf.js + Mistral.



<p align="center">
  <img src="https://raw.githubusercontent.com/ibrokenshadow/SnitchQ/main/assets/snitchq-logo.png" alt="SnitchQ Logo" width="120" />
  <h1 align="center">SnitchQ</h1>
  <p align="center">🕵️‍♂️ The Telegram Scam-Snitch Bot — by iBrokenShadow</p>
</p>

<p align="center">
  <a href="https://github.com/ibrokenshadow/SnitchQ/releases"><img src="https://img.shields.io/github/v/release/ibrokenshadow/SnitchQ?style=for-the-badge" alt="Release" /></a>
  <a href="https://github.com/ibrokenshadow/SnitchQ/blob/main/LICENSE"><img src="https://img.shields.io/github/license/ibrokenshadow/SnitchQ?style=for-the-badge" alt="License" /></a>
  <a href="https://nodejs.org/"><img src="https://img.shields.io/badge/Node.js-18.x-green?style=for-the-badge" alt="Node.js" /></a>
  <a href="https://telegraf.js.org/"><img src="https://img.shields.io/badge/Telegraf-4.x-blue?style=for-the-badge" alt="Telegraf" /></a>
</p>

---

## 🚀 Table of Contents
1. [About](#about)  
2. [Features](#features)  
3. [Tech Stack](#tech-stack)  
4. [Installation](#installation)  
5. [Configuration](#configuration)  
6. [Usage](#usage)  
7. [Prompt Design](#prompt-design)  
8. [Error Handling](#error-handling)  
9. [Roadmap](#roadmap)  
10. [Contributing](#contributing)  
11. [License](#license)  
12. [Author](#author)  

---

## 🤖 About
SnitchQ is your trusty Telegram sidekick that sniffs out scams, phishing, and shady shenanigans in forwarded chats.  
Using Telegraf.js, Node.js, and a local LLM (via [Ollama](https://ollama.com/)), SnitchQ classifies messages into:
- Legit ✅  
- Scam ❌  
- Suspicious ⚠️  

All computation happens locally—no third-party API bills, no data leaks. Just pure, private AI-powered scam detection.

---

## ✨ Features
- 📨 Forward-to-Analyze: Simply forward any Telegram message to SnitchQ.  
- 🧠 On-Prem LLM: Powered by lightweight models like Mistral, Phi or TinyLlama via Ollama.  
- 🔍 Clear Verdict: Returns “Legit”, “Scam”, or “Suspicious” with concise reasoning.  
- 🚨 User-Friendly Errors: Informs you if something goes sideways.  
- 🛠️ Modular Design: Easily extendable—add logging, dashboards, voice support, and more!  

---

## 🛠️ Tech Stack
<p align="center">
  <img src="https://img.shields.io/badge/Node.js-18.x-green?style=flat-square" />  
  <img src="https://img.shields.io/badge/Telegraf-4.x-blue?style=flat-square" />  
  <img src="https://img.shields.io/badge/Ollama-Local%20LLM-orange?style=flat-square" />  
  <img src="https://img.shields.io/badge/Mistral/Phi/TinyLlama-gray?style=flat-square" />  
  <img src="https://img.shields.io/badge/SQLite-optional-yellow?style=flat-square" />  
</p>

---

## 🧩 Installation

`bash
# 1. Clone this repo
git clone https://github.com/ibrokenshadow/SnitchQ.git
cd SnitchQ

# 2. Install dependencies
npm install

# 3. (Optional) Install & start Ollama and pull your LLM
#    https://ollama.com/docs/installation
ollama daemon &
ollama pull mistral

# 4. Copy .env.example → .env and set your variables
cp .env.example .env


---

⚙️ Configuration

Edit your .env:

BOT_TOKEN=YOUR_TELEGRAM_BOT_TOKEN
OLLAMA_URL=http://localhost:11434/api/generate
MODEL_NAME=mistral   # or phi, tinyllama, etc.
PORT=3000


---

📦 Usage

# Start your bot
npm start

1. Open Telegram and chat with @YourBotUsername.


2. Send /start to wake it up.


3. Forward any message you want SnitchQ to scan.


4. Receive your scam verdict in seconds.




---

📝 Prompt Design

We use a concise template to stay within tight model contexts:

Classify the following Telegram message as Legit, Scam, or Suspicious:

Message:
"{forwarded_text}"

Answer with the label and a one-sentence reasoning.


---

🚧 Error Handling
No forward detected? → “Please forward a message for scam analysis.”

Empty text? → “Forwarded message contains no text to analyze.”

LLM timeout/fail? → “Failed to get a response from the scam detection model.”

All wrapped in try/catch for graceful user feedback.



---

📈 Roadmap

[ ] Verdict logging (SQLite / JSON)

[ ] “Trusted Users” whitelist

[ ] User feedback & report command

[ ] Express.js / Next.js Dashboard

[ ] Voice message support (Whisper)

[ ] Rate-limiting & abuse protection



---

🤝 Contributing

Fork it → git@github.com:ibrokenshadow/SnitchQ.git


---

📜 License

This project is licensed under the MIT License. See LICENSE for details.


---

🦸 Author

Broken Shadow (@iBrokenShadow)

Business-P & Investor

Freelance Web Dev ❤️‍

Ethical Hacker & Programmer

🌐 https://ibrokenshadow.com

✉️ Reach me on Telegram: @iBrokenShadow



---

<p align="center">
  <em>SnitchQ — Because scammers don’t rest, and neither should your security.</em>
</p>
