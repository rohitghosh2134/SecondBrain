Here’s how to convert your **existing local folder** into a **Git repository** and connect it to your **GitHub repo** (`https://github.com/rohitghosh2134/StockPrediction.git`).

---

### 🧭 Step-by-Step Guide

#### 1. Open your project folder

Open a terminal or command prompt and **navigate to your folder**:

```bash
cd "path/to/your/folder"
```

#### 2. Initialize Git in that folder

```bash
git init
```

> This creates a new `.git` folder that tracks all version history.

#### 3. Add all files to staging

```bash
git add .
```

> This stages all existing files for the first commit.

#### 4. Commit your changes

```bash
git commit -m "Initial commit"
```

#### 5. Add the remote GitHub repository

Replace the URL with your own repo:

```bash
git remote add origin https://github.com/rohitghosh2134/StockPrediction.git
```

You can verify the remote is added:

```bash
git remote -v
```

#### 6. Rename your local branch to main (if needed)

```bash
git branch -M main
```

#### 7. Push your local code to GitHub

```bash
git push -u origin main
```

> You might be asked to log in or use a **personal access token** (PAT) if you’re using HTTPS.

---

### ✅ Optional — If the remote already has files (like a README)

If the GitHub repo isn’t empty, you should first **pull** to merge remote files:

```bash
git pull origin main --allow-unrelated-histories
```

Then push:

```bash
git push -u origin main
```

---

Would you like me to give you a **single script** (you can paste into terminal) that does all this automatically for your specific repo and folder path?