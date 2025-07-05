# Use a Python base image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Install system dependencies required for building Python packages like mysqlclient
# python:3.11-slim is based on Debian, so we use apt-get
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    libmariadb-dev \
    pkg-config && \
    rm -rf /var/lib/apt/lists/*

# Copy requirements.txt into the container
COPY requirements.txt .

# Install Python dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy the rest of your Django project code into the container
COPY . .

# Expose the port your Django application runs on
EXPOSE 8000

# Command to run the Django application
# You might need to adjust this based on your Django project structure
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
