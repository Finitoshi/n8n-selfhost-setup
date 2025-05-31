
n8n-selfhost-setup/
├── README.md
├── install_n8n_secure.sh
├── update_n8n.sh
└── uninstall_n8n.sh
📄 Contents of Each File
🔧 install_n8n_secure.sh


🔄 update_n8n.sh
bash
Copy code
#!/bin/bash

echo "[🔄] Updating n8n..."

cd ~/n8n || { echo "❌ Cannot find ~/n8n"; exit 1; }

echo "[↓] Pulling latest Docker image..."
docker compose pull

echo "[🔁] Restarting n8n with new image..."
docker compose up -d

echo "✅ n8n updated and running at: https://n8n.vicestrella.com"
🧨 uninstall_n8n.sh
Already given above

📝 README.md
md
Copy code
# n8n Self-Hosted Setup Scripts

These scripts automate the installation, update, and removal of a fully secure self-hosted [n8n](https://n8n.io) instance on a Linux VPS using Docker and NGINX.

---

## 📦 Scripts

| File | Purpose |
|------|---------|
| `install_n8n_secure.sh` | Installs n8n on a subdomain with HTTPS |
| `update_n8n.sh` | Pulls the latest n8n Docker image and restarts |
| `uninstall_n8n.sh` | Removes the n8n container, config, and user |

---

## 🚀 Usage

### 1. Install (run as root)

```bash
chmod +x install_n8n_secure.sh
./install_n8n_secure.sh
This will:

Create a dedicated user (n8nuser)

Set up Docker, NGINX, SSL

Deploy n8n to https://n8n.yourdomain.com

2. Update (run as n8nuser)
bash
Copy code
chmod +x update_n8n.sh
./update_n8n.sh
3. Uninstall (run as root)
bash
Copy code
chmod +x uninstall_n8n.sh
sudo ./uninstall_n8n.sh
🙏 Credits
Built for fast, secure n8n hosting by @vicestrella

yaml
Copy code

---

## 🐙 Next Step: Publish the Repo

1. Log into GitHub and create a repo:
   - Name: `n8n-selfhost-setup`
   - Description: Self-host n8n with Docker, HTTPS, and non-root user
   - Visibility: Public (or Private if preferred)

2. On your VPS or dev machine:

```bash
git init n8n-selfhost-setup
cd n8n-selfhost-setup

# Add your files
cp ~/install_n8n_secure.sh .
cp ~/update_n8n.sh .
cp ~/uninstall_n8n.sh .
nano README.md  # Paste the README above

# Push to GitHub
git add .
git commit -m "Initial commit of secure n8n setup scripts"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/n8n-selfhost-setup.git
git push -u origin main
