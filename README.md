# Monopoly Deal

Card game playable at `http://100.80.40.32:3000`

## Deploy to Synology via GitHub

### 1. Create GitHub Repo

```bash
# On your local machine
cd monopoly-deal-docker
git init
git add .
git commit -m "Monopoly Deal"
gh repo create monopoly-deal --private --source=. --push
```

Or create the repo on github.com manually, then:

```bash
git init
git add .
git commit -m "Monopoly Deal"
git remote add origin git@github.com:YOUR_USERNAME/monopoly-deal.git
git push -u origin main
```

### 2. SSH into Synology & Clone

```bash
ssh your-user@100.80.40.32
cd /volume1/docker
git clone https://github.com/YOUR_USERNAME/monopoly-deal.git
cd monopoly-deal
```

### 3. Build & Run

```bash
docker compose up -d --build
```

Game is now live at **http://100.80.40.32:3000**

### Updating

After pushing changes to GitHub:

```bash
ssh your-user@100.80.40.32
cd /volume1/docker/monopoly-deal
git pull
docker compose up -d --build
```
