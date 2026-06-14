# Use Python 3.8 (same as your local version)
FROM python:3.8-slim

# Set work directory inside container
WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy all project files
COPY . .

# Collect static files
RUN python manage.py collectstatic --noinput

# Run the app using gunicorn
CMD ["gunicorn", "expensetracker.wsgi:application", "--bind", "0.0.0.0:8000"]