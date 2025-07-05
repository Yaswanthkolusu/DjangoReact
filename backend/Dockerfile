FROM python:3.11-slim
 
# Set workdir
WORKDIR /app
 
# Environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
 
# Install dependencies
COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
 
# Copy source code
COPY . .
 
# Run Django development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
