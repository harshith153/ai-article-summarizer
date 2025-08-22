# 🤖 AI Article Summarizer & Auto-Poster  

[![GitHub Repo](https://img.shields.io/badge/GitHub-harshith153-blue?logo=github)](https://github.com/harshith153)  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Harshith%20Basa-blue?logo=linkedin)](https://www.linkedin.com/in/sri-sai-durga-harshith-basa-b8a20724b)  
[![Twitter](https://img.shields.io/badge/Twitter-@Harshith153-blue?logo=twitter)](https://x.com/Harshith153)  

---

## 📌 Project Overview
This project automates the process of *fetching AI-related articles, generating social-media-ready summaries, and posting them directly to LinkedIn and Twitter (X)* using **n8n workflows**.

---

## ⚙ Features
✅ Automated article fetching  
✅ AI-powered summarization (OpenAI)  
✅ Social media auto-posting (LinkedIn + X)  
✅ Google Sheets integration for logging  
✅ Fully customizable via *n8n*  

---

## 🛠 Tech Stack
- *n8n* (workflow automation)  
- *OpenAI GPT* (summarization)  
- *LinkedIn API* (auto-posting)  
- *Twitter API* (auto-posting)  
- *Google Sheets API* (data storage)  

---

## 📊 Workflow

🔗 [View Workflow File](https://drive.google.com/file/d/1JZa2l5YQvQBwMVDSYafrgUj2PRN6g58M/view?usp=sharing)  

![Workflow Screenshot](workflow.png)

---

## 🔑 Setup Instructions
1. Clone this repository  
   ```bash
   git clone https://github.com/harshith153/ai-article-summarizer.git
   cd ai-article-summarizer

2. Create a .env file OPENAI_API_KEY=your_openai_key LINKEDIN_ACCESS_TOKEN=your_linkedin_token X_BEARER_TOKEN=your_twitter_token 3. Import the provided workflow.json into n8n. 4. Start your n8n instance: n8n start --- 🌐 Example Articles Used Microsoft Build 2025 – The Age of AI Agents IBM – Generative AI Topics --- 📢 Social Media Posts 🔗 LinkedIn Post 🐦 Twitter/X Post --- 📌 Author 👤 Sri Sai Durga Harshith Basa 📧 harshithbasa2005@gmail.com 🔗 LinkedIn
