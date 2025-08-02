🔗 URL Shortener Microservice
A lightweight URL shortening service built with FastAPI, supporting custom shortcodes and link expiry.

📦 Tech Stack
Python 3.7+

FastAPI

Uvicorn

Pydantic

🚀 Getting Started
1. Clone & Set Up Environment
bash
Copy
Edit
git clone <your-repo-url>
cd url-shortener
python -m venv venv
source venv/bin/activate  # or .\venv\Scripts\activate on Windows
2. Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
▶️ Run the Application
Start the development server:

bash
Copy
Edit
uvicorn main:app --host 127.0.0.1 --port 8000
Visit: http://127.0.0.1:8000

API docs: http://127.0.0.1:8000/docs

📖 API Reference
🔹 Create a Short URL
Method: POST /shorturls

Body:

json
Copy
Edit
{
  "url": "https://example.com",
  "validity": 30,
  "shortcode": "custom123"  // Optional
}
Response:

json
Copy
Edit
{
  "shortLink": "http://localhost:8000/custom123",
  "expiry": "2025-01-01T00:30:00Z"
}
🔹 Redirect to Original URL
Method: GET /{shortcode}

Automatically redirects to the original URL if valid.

🧠 Architecture
See DESIGN.md for more details on internal logic, data flow, and extension plans.

⚠️ Limitations
Uses in-memory storage only (data resets on restart).

Not ready for production out-of-the-box — persistence, auth, and logging are needed.

💡 Future Improvements
✅ Add database (Redis, SQLite, etc.)

🔐 JWT Authentication

📊 Analytics dashboard for click tracking

📦 Docker containerization
