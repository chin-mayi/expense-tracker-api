# Expense Tracker API 💰

A secure and scalable REST API built with Django REST Framework for tracking personal expenses.

## 🚀 Live Demo
[Coming soon - Deploying on Render]

## ✨ Features
- JWT Authentication (Register/Login/Logout)
- Add, view, edit and delete expenses
- Filter expenses by category and date
- Monthly summary by category
- Secure — each user sees only their own data
- Dockerized with PostgreSQL

## 🛠️ Tech Stack
- **Backend:** Python, Django, Django REST Framework
- **Authentication:** JWT (JSON Web Tokens)
- **Database:** PostgreSQL
- **Containerization:** Docker
- **Deployment:** Render.com

## 📌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/token/ | Login and get JWT token |
| POST | /api/token/refresh/ | Refresh JWT token |
| GET | /api/expenses/ | Get all expenses |
| POST | /api/expenses/ | Add new expense |
| GET | /api/expenses/{id}/ | Get single expense |
| PUT | /api/expenses/{id}/ | Update expense |
| DELETE | /api/expenses/{id}/ | Delete expense |
| GET | /api/expenses/summary/ | Get monthly summary |

## 🏃 How to Run Locally

### Without Docker:
```bash
# Clone the repo
git clone https://github.com/YOURUSERNAME/expense-tracker-api.git
cd expense-tracker-api

# Create virtual environment
python -m venv expenseenv
expenseenv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py migrate

# Start server
python manage.py runserver
```

### With Docker:
```bash
docker-compose up --build
```

## 📸 Sample API Response

### Login
```json
{
  "access": "eyJhbGc...",
  "refresh": "eyJhbGc..."
}
```

### Add Expense
```json
{
  "id": 1,
  "title": "Lunch",
  "amount": "150.00",
  "category": "food",
  "date": "2025-06-13",
  "description": "Lunch at office canteen",
  "created_at": "2025-06-13T10:11:11Z"
}
```

### Monthly Summary
```json
[
  {"category": "food", "total": 150.00},
  {"category": "transport", "total": 500.00}
]
```