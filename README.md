# 🧠 n8n Workflows – Git Versioned Setup

This project contains n8n workflows stored locally and versioned with Git.  
Anyone can clone, run, and contribute using branches.

---

## 🚀 How to Run It Locally

### 1. Clone the repo

```bash
git clone https://github.com/JulioMProyecto1/n8n_project.git
cd n8n_project
```

### 2. Create a local folder for workflows

(If not already present after cloning)

```bash
mkdir n8n_data
```

### 3. Run n8n with Docker

```bash
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -v $PWD/n8n_data:/home/node/.n8n \
  -e N8N_BASIC_AUTH_ACTIVE=true \
  -e N8N_BASIC_AUTH_USER=admin \
  -e N8N_BASIC_AUTH_PASSWORD=secret \
  -e N8N_ENCRYPTION_KEY=mySuperSecretKey123 \
  docker.n8n.io/n8nio/n8n
```

Then open your browser: [http://localhost:5678](http://localhost:5678)

---

## 🛠 Versioning Workflows with Git

Workflows are saved in `n8n_data/` and automatically updated as you build.

### Basic Git Flow

```bash
git checkout -b feature/my-new-flow
# build your workflow in n8n
git add .
git commit -m "Add: My new flow"
git push origin feature/my-new-flow
```

Then open a pull request 🚀

---

## 👥 Collaborating

- Always create a new branch before editing workflows
- Keep sensitive info out of Git (we use `.gitignore`)
- Protect your encryption key if shared

---

## 📦 .gitignore (already included)

```gitignore
n8nEventLog.log
crash.journal
binaryData/
database.sqlite
config/
ssh/
```

---

## ✅ Requirements

- Docker
- Git
- [ngrok (optional)](https://ngrok.com/) – for sharing your local n8n with others

---

## 🤝 Contributors

- @yourname

PRs welcome!
```