# 📚 Book Recommender Chatbot

A full-stack AI-powered book recommendation chatbot built with **Flask + Glassmorphism UI + Google Books API**.

🔗 **Live Demo:** *(add your Render URL here after deployment)*
🐙 **GitHub:** https://github.com/Kamalapro05/book-recommender

---

## ✨ Features

- 🔐 Session-based Sign-up & Login
- 🌐 Live book data from **Google Books API** (covers, ratings, previews)
- 📂 Fallback to **38,000+ local books** if API is unavailable
- 🎨 Glassmorphism UI with animated gradient background
- 📚 10 genres: Sci-Fi, Fantasy, Mystery, Romance, Horror, Thriller, Historical, Western, Fiction, Non-Fiction
- 🖱️ Draggable genre chip bar
- 📖 Book cards with cover image, star rating, page count & preview link

---

## 🗂️ Project Structure

```
book-recommender/
├── backend/
│   ├── app.py              # Flask server (routes, auth, API)
│   ├── recommender.py      # Google Books API + CSV fallback logic
│   ├── books_data.csv      # 38K local books dataset
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── index.html          # Sign-up page
│   ├── login.html          # Login page
│   ├── chat.html           # Chat interface
│   ├── style.css           # Glassmorphism design system
│   └── script.js           # Fetch calls & UI logic
├── .env                    # Secret keys (DO NOT commit!)
├── .env.example            # Safe template for .env
├── .gitignore
├── Procfile                # For Render/Railway deployment
├── runtime.txt             # Python version
└── README.md
```

---

## 🚀 Local Setup (Step by Step)

### 1. Clone the repository
```bash
git clone https://github.com/Kamalapro05/book-recommender.git
cd book-recommender
```

### 2. Create a virtual environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac / Linux
python3 -m venv venv
.\venv\Scripts\Activate.ps1    
```

### 3. Install dependencies
```bash
pip install -r backend/requirements.txt
```

### 4. Set up environment variables
```bash
# Copy the example file
cp .env.example .env
```
Then open `.env` and fill in your values:
```env
SECRET_KEY=any-random-string-here
GOOGLE_BOOKS_API_KEY=your-google-books-api-key
FLASK_ENV=development
FLASK_DEBUG=1
```

> 💡 Get a free Google Books API key at: https://console.cloud.google.com
> Enable **Books API** → Credentials → Create API Key

### 5. Run the server
```bash
python backend/app.py
```

### 6. Open the app
Visit **http://127.0.0.1:5000** in your browser 🎉

---

## ☁️ Deploy to Render (Free Hosting)

### Step 1 — Push to GitHub
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/Kamalapro05/book-recommender.git
git push -u origin main
```

### Step 2 — Create a Render account
Go to → https://render.com and sign up with GitHub

### Step 3 — Create a new Web Service
1. Click **"New +"** → **"Web Service"**
2. Connect your GitHub repo **book-recommender**
3. Fill in settings:

| Field | Value |
|---|---|
| **Name** | book-recommender |
| **Region** | Singapore (closest to India) |
| **Branch** | main |
| **Runtime** | Python 3 |
| **Build Command** | `pip install -r backend/requirements.txt` |
| **Start Command** | `gunicorn --chdir backend app:app --bind 0.0.0.0:$PORT` |
| **Instance Type** | Free |

### Step 4 — Add Environment Variables on Render
In your Render service → **Environment** tab → Add these:

| Key | Value |
|---|---|
| `SECRET_KEY` | any-long-random-string |
| `GOOGLE_BOOKS_API_KEY` | AIzaSyAcr6WDn7Mk8x-HRpCWdOsAWQpzPYMHvHQ |
| `FLASK_ENV` | production |
| `FLASK_DEBUG` | 0 |

### Step 5 — Deploy
Click **"Create Web Service"** — Render will build and deploy automatically.
Your app will be live at: `https://book-recommender-xxxx.onrender.com`

---

## 🔄 Push Updates to GitHub

After making any changes:
```bash
git add .
git commit -m "Your message here"
git push
```
Render auto-deploys every time you push to `main`. ✅

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.11, Flask 3.0, Flask-CORS |
| Data | Google Books API + Pandas CSV (38K books) |
| Frontend | Vanilla HTML / CSS / JavaScript |
| Auth | Flask Sessions |
| Hosting | Render (free tier) |
| Version Control | Git + GitHub |

---

## ⚠️ Important Security Notes

- Never commit your `.env` file — it's in `.gitignore`
- Use `.env.example` as a template for others
- Change `SECRET_KEY` to a long random string in production
- Rotate your `GOOGLE_BOOKS_API_KEY` if it gets exposed

---

## 📄 License
MIT — free to use and modify.
