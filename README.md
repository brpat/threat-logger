# Threat Logger

## Overview
Threat Logger is a simple Django-based cybersecurity application that allows users to log and manage security threats. It is designed to be lightweight, with CRUD operations for storing threat details in a PostgreSQL database. The entire application runs in Docker containers for easy deployment.

## Features
- **Log Security Threats**: Add, update, and delete cybersecurity threats.
- **Severity Levels**: Categorize threats as Low, Medium, High, or Critical.
- **Timestamps**: Automatically record when a threat is logged.
- **PostgreSQL Integration**: Store data securely in a PostgreSQL database.
- **Dockerized Deployment**: Run the app and database in isolated containers.

## Project Structure
```
threat-logger/
│── docker-compose.yml
│── Dockerfile
│── .env
│── django_app/  # Django project
│   ├── threats/  # Django app for threat logging
│── requirements.txt
```

## Prerequisites
- Docker & Docker Compose installed
- Python 3.x installed (for local development, if needed)

## Installation & Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/threat-logger.git
   cd threat-logger
   ```
2. Create a `.env` file with database credentials:
   ```env
   POSTGRES_DB=threat_db
   POSTGRES_USER=admin
   POSTGRES_PASSWORD=securepassword
   ```
3. Build and run the containers:
   ```bash
   docker-compose up --build
   ```
4. Apply database migrations:
   ```bash
   docker-compose exec web python manage.py migrate
   ```
5. Create a superuser (optional, for admin panel):
   ```bash
   docker-compose exec web python manage.py createsuperuser
   ```
6. Access the app:
   - Web interface: `http://localhost:8000`
   - Admin panel: `http://localhost:8000/admin`

## Usage
- Navigate to the web interface to log threats.
- Use Django Admin to manage database entries.
- If using Django REST Framework, API endpoints will be available at `http://localhost:8000/api/threats/`.

## Future Enhancements
- **User Authentication**: Restrict access to logged-in users.
- **Logging & Alerts**: Send notifications for critical threats.
- **Search & Filtering**: Enhance usability with advanced queries.

## License
MIT License. Feel free to modify and expand the project!

