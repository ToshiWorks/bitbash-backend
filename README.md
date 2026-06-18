# ⚙️ Bit Bash Bonanza — Backend

> REST API backend for the Bit Bash Bonanza coding competition platform. Built with Python Flask, featuring a custom sandboxed code execution engine.

🔗 **Frontend Repo:** [bitbash-frontend](https://github.com/ToshiWorks/bitbash-frontend)  
🌐 **Live Frontend:** [bitbash-frontend.vercel.app](https://bitbash-frontend.vercel.app/)

---

## ✨ Key Features

- 🔒 **Sandboxed Code Execution** — runs user-submitted code safely using Python's `subprocess` module with timeout protection
- ✅ **Test Case Evaluation** — automatically validates output against expected results
- 📊 **Dynamic Scoring API** — calculates and returns scores based on correctness
- 🗂️ **Question Management** — serves topic-based questions with difficulty levels
- 🔄 **REST API Design** — clean endpoints consumed by the React frontend

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | Python Flask |
| API Style | REST |
| Code Execution | Python subprocess module |
| Deployment | Render |

---

## 🔧 How to Run Locally

### Prerequisites
- Python 3.10+
- pip

### Steps

```bash
# Clone the repo
git clone https://github.com/ToshiWorks/bitbash-backend.git
cd bitbash-backend

# Install dependencies
pip install -r requirements.txt

# Run the server
python app.py
```

The API runs at `http://localhost:5000`

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/questions` | Fetch all questions |
| GET | `/questions/:topic` | Fetch questions by topic |
| POST | `/execute` | Submit and execute code |
| POST | `/score` | Calculate and return score |

---

## 🔐 Code Execution — How It Works

User-submitted code is executed via Python's `subprocess` module:

```python
result = subprocess.run(
    ['python3', '-c', user_code],
    capture_output=True,
    text=True,
    timeout=5  # Timeout protection — kills process after 5 seconds
)
```

Output is then compared against expected test case results to determine correctness.

---

## 👩‍💻 Built By

**Toshita Upadhyay** — [github.com/ToshiWorks](https://github.com/ToshiWorks)
