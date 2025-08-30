🎟 Event Management API

A RESTful API built with Django and Django REST Framework for handling events, user registrations, and ticket management.

✨ Key Features

🔐 Secure user authentication with JWT

🛠 Full CRUD operations for events

🎫 Event registration with ticket limits

⏳ Automatic waitlist support for full events

🔍 Event filtering and search functionality

📖 API docs available with Swagger & ReDoc

📋 Requirements

Python 3.8+

pip (Python package manager)

PostgreSQL (optional – SQLite is the default)

⚡ Installation

Clone the repository

git clone <repository-url>
cd event-management-api

Create & activate a virtual environment

Windows:

python -m venv venv
.\venv\Scripts\activate

macOS/Linux:

python3 -m venv venv
source venv/bin/activate

Install dependencies

pip install -r requirements.txt

Configure environment variables
Create a .env file in the project root:

SECRET_KEY=your-secret-key-here
DEBUG=True
DATABASE_URL=sqlite:///db.sqlite3

Run migrations

python manage.py migrate

Create a superuser

python manage.py createsuperuser

▶ Running the Server
python manage.py runserver

API available at: http://127.0.0.1:8000/

📖 API Documentation

Swagger UI → http://127.0.0.1:8000/api/docs/

ReDoc → http://127.0.0.1:8000/api/redoc/

🔗 API Endpoints
Authentication

POST /api/v1/auth/register/ → Register a new account

POST /api/v1/auth/token/ → Get JWT token

POST /api/v1/auth/token/refresh/ → Refresh JWT token

Events

GET /api/v1/events/ → List events

POST /api/v1/events/ → Create an event

GET /api/v1/events/{id}/ → Get event details

PUT /api/v1/events/{id}/ → Update event

DELETE /api/v1/events/{id}/ → Delete event

POST /api/v1/events/{id}/register/ → Register for event

User-Specific

GET /api/v1/users/me/events/registered/ → View events registered by current user

GET /api/v1/users/me/events/organized/ → View events organized by current user

🔍 Query Parameters (Events List)

upcoming=true → Show only upcoming events

organizer=username → Filter by organizer

search=term → Search in title or location

🧪 Testing

Run all tests with:

python manage.py test

🚀 Deployment Notes

For production:

Set DEBUG=False

Use a strong SECRET_KEY

Configure PostgreSQL (recommended)

Use Gunicorn + Nginx for serving

Enable HTTPS with Let’s Encrypt
