# 🤖 DevOps Chatbot (Java + Slack + Jenkins)

A full-stack **DevOps chatbot** built with **Java (Spring Boot)** that integrates with **Slack** to trigger CI/CD operations via **Jenkins**, deployed on **Render** and **Railway** using free-tier resources.

---

## 🚀 Features

- Slash commands in Slack like:
  - `/check_health` → triggers a Jenkins health-check job
  - `/restart frontend` → restarts frontend via Jenkins
  - `/logs user-service` → fetches logs via Jenkins job
- Asynchronous Slack responses to avoid timeouts
- Jenkins integration via remote API trigger with tokens
- Real-time Slack responses with status updates
- Deployed using:
  - 🟦 **Jenkins on Railway** (with persistent storage)
  - 🟨 **Slackbot on Render**

---

## 🛠️ Stack

| Layer          | Tech                          |
|----------------|-------------------------------|
| Language       | Java 17                        |
| Backend        | Spring Boot                    |
| DevOps         | Jenkins                        |
| Messaging      | Slack API + Slash Commands     |
| Hosting        | Render (Slackbot), Railway (Jenkins) |
| Build Tool     | Maven                          |

---

## 📦 Project Structure
```
.
├── scripts/ # Bash scripts triggered by Jenkins
├── src/main/java/com/sops/slackbot
│ ├── controller/ # Slack event and command handlers
│ ├── service/ # Slack and Jenkins service classes
│ └── SlackbotApplication.java
├── application.properties # Injects secrets from env
├── Dockerfile # Containerized Spring app
└── pom.xml # Maven dependencies
```
---

## 🧪 Slash Command Examples

| Command                   | Description                          |
|---------------------------|--------------------------------------|
| `/check_health`           | Checks system health via Jenkins     |
| `/restart frontend`       | Restarts frontend via Jenkins        |
| `/logs user-service`      | Gets logs for user-service component |

---

## 🌐 Deployment URLs

| Service     | URL                                            |
|-------------|------------------------------------------------|
| Slackbot    | [`https://slackbot-vmwi.onrender.com`](https://slackbot-vmwi.onrender.com) |
| Jenkins     | [`https://jenkins-on-railway.onrender.com`](https://jenkins-on-railway.onrender.com) |

---

## 🔐 Environment Variables

Set these in **Render** for the Slackbot:

```env
SLACK_BOT_TOKEN=...
SLACK_SIGNING_SECRET=...

JENKINS_URL=https://jenkins-on-railway.onrender.com
JENKINS_USER=shriyashsawant
JENKINS_TOKEN=...
JENKINS_TRIGGER_TOKEN=...
✨ How It Works
User types /check_health in Slack

Slack sends an HTTP POST to the Spring Boot backend

Backend triggers a Jenkins job via API

Jenkins runs a script (like health_check.sh)

Bot replies back in Slack with job result
```

📸 Screenshots
![image](https://github.com/user-attachments/assets/ba3e8378-3a74-4577-80f6-f378a3f4e632)



| Slack Command        | Bot Response                                               |
|----------------------|------------------------------------------------------------|
| `/check_health`      | ✅ Command received. Processing...<br>⏳ Checking server health... |
| `/restart frontend`  | ♻️ Restarting frontend...                                  |
| `/logs user-service` | 📄 Fetching logs...                                        |


![image](https://github.com/user-attachments/assets/7bb2ad41-91b7-4d0c-bfbe-2b715cc8e17a)


🤝 Contributing
Want to add more commands or integrations (like MS Teams)?
Feel free to fork and raise a PR!

👨‍💻 Author
Shriyash Sawant
🔗 [GitHub](https://github.com/shriyashsawant)| [LinkedIn](https://www.linkedin.com/in/shriyash-sawant-5a6a6120a/)


## 🏷️ Tags

`#DevOps` `#Java` `#SpringBoot` `#SlackBot` `#Jenkins` `#CI/CD` `#Automation` `#Railway` `#Render`


---


