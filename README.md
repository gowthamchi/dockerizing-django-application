#  Dockerized Django Complaint Management System

This is a fully Dockerized Django REST API project for managing user complaints. It allows CRUD operations via REST endpoints and demonstrates modern DevOps practices including Docker, environment variable management, and clean code architecture.

---

##  Project Setup Instructions

Clone the repository:

```bash
git clone https://github.com/gowthamchi/dockerized-django-app.git
cd dockerized-django-app
```

Create your `.env` file 

```bash
vim .env
```

Then add the following environment variables:

```env
DEBUG=True
SECRET_KEY=your-secret-key
ALLOWED_HOSTS=localhost
DB_NAME=postgres
DB_USER=postgres
DB_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

Build and start the services using Docker Compose:

```bash
docker-compose up --build
```

Apply database migrations:

```bash
docker-compose exec web python manage.py migrate
```

Create a Django superuser (optional):

```bash
docker-compose exec web python manage.py createsuperuser
```

---

##  API Endpoints

You can access and test the API endpoints listed below:

```http
GET     /api/complaints/           # List all complaints  
POST    /api/complaints/           # Create a new complaint  
GET     /api/complaints/<id>/      # Get a specific complaint by ID  
PUT     /api/complaints/<id>/      # Update a complaint  
DELETE  /api/complaints/<id>/      # Delete a complaint  
```

Test using Postman or with `curl`, e.g.:

```bash
curl http://localhost:8000/api/complaints/
```

All responses are returned in JSON format.

---

##  Project Structure

```text
.
├── docker-compose.yml
├── Dockerfile
├── .env
├── .gitignore
├── manage.py
├── credentials/
│   └── gowtham-key.json (ignored)
├── myproject--
```

---

##  Sensitive Files

The following files are excluded via `.gitignore`:

```gitignore
.env
gowtham-key.json
__pycache__/
*.pyc
venv/
.idea/
.vscode/
*.log
```

---

##  Demo Videos

| Project Overview   | https://drive.google.com/file/d/1h3ugBmSRGoAEPgFWbyDeL0MdLxx-V16T/view?usp=drive_link |



---

##  Assumptions & Design

- The app runs in a local Dockerized environment.  
- All environment variables are injected via `.env`.  
- API authentication is not implemented to keep the project simple.  
- The service account file `gowtham-key.json` is required for secure external integrations but is excluded from version control.

---

##  Technologies Used

```text
- Python 3.x
- Django
- Django REST Framework
- PostgreSQL
- Docker
- Docker Compose
- Git & GitHub
```

---

##  Author

**Gangeddula Goutham Reddy**  
gowthamchintu2004@gmail.com  
 [GitHub](https://github.com/gowthamchi) | [LinkedIn](https://www.linkedin.com/in/gouthamreddy1)

---


