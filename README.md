# 🤖 AI Article Summarizer & Auto-Poster  

[![GitHub Repo](https://img.shields.io/badge/GitHub-harshith153-blue?logo=github)](https://github.com/harshith153)  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Harshith%20Basa-blue?logo=linkedin)](https://www.linkedin.com/in/sri-sai-durga-harshith-basa-b8a20724b)  
[![Twitter](https://img.shields.io/badge/Twitter-@Harshith153-blue?logo=twitter)](https://x.com/Harshith153)  

---

## 📌 Project Overview
This project automates the process of fetching AI-related articles, generating social-media-ready summaries, and posting them directly to LinkedIn and Twitter (X) using **n8n workflows**.

It helps professionals save time while maintaining an active presence on social platforms with consistent, high-quality AI insights.  

---

## ⚙ Features
✅ Automated article fetching  
✅ AI-powered summarization (OpenAI)  
✅ Social media auto-posting (LinkedIn + X)  
✅ Google Sheets integration for logging  
✅ Fully customizable via *n8n*  

---

## 🛠 Tech Stack
- **n8n** (workflow automation)  
- **OpenAI GPT** (summarization)  
- **LinkedIn API** (auto-posting)  
- **Twitter API** (auto-posting)  
- **Google Sheets API** (data storage)  

---

## 📊 Workflow  

Below is the exported `workflow.json` that you can directly import into **n8n**.  

<details>
<summary>📂 Click to view workflow.json</summary>

```json
{
  "name": "AI Article Summarizer & Auto-Poster",
  "nodes": [
    {
      "parameters": {
        "url": "https://blogs.microsoft.com/blog/2025/05/19/microsoft-build-2025-the-age-of-ai-agents-and-building-the-open-agentic-web/"
      },
      "name": "Fetch Microsoft Article",
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 1
    },
    {
      "parameters": {
        "url": "https://www.ibm.com/think/topics/generative-ai"
      },
      "name": "Fetch IBM Article",
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 1
    },
    {
      "parameters": {
        "model": "gpt-4",
        "prompt": "Summarize the following article in a crisp, professional way suitable for LinkedIn and Twitter posts:\n\n{{$json[\"body\"]}}"
      },
      "name": "AI Summarizer",
      "type": "n8n-nodes-base.openAi",
      "typeVersion": 1
    },
    {
      "parameters": {
        "resource": "post",
        "operation": "create",
        "content": "{{$json[\"text\"]}}"
      },
      "name": "Post to LinkedIn",
      "type": "n8n-nodes-base.linkedin",
      "typeVersion": 1
    },
    {
      "parameters": {
        "resource": "tweet",
        "operation": "create",
        "text": "{{$json[\"text\"]}}"
      },
      "name": "Post to Twitter",
      "type": "n8n-nodes-base.twitter",
      "typeVersion": 1
    },
    {
      "parameters": {
        "operation": "append",
        "sheetId": "your_google_sheet_id",
        "range": "Posts!A:C",
        "valueInputMode": "RAW",
        "values": [
          [
            "{{$json[\"url\"]}}",
            "{{$json[\"summary\"]}}",
            "{{$json[\"timestamp\"]}}"
          ]
        ]
      },
      "name": "Log in Google Sheets",
      "type": "n8n-nodes-base.googleSheets",
      "typeVersion": 1
    }
  ],
  "connections": {}
}
</details>
🔑 Setup Instructions
Clone this repository

bash
Copy
Edit
git clone https://github.com/harshith153/ai-article-summarizer.git
cd ai-article-summarizer
