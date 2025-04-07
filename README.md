
#  A-32 FINAL: Flask + Django Web Apps with Docker Compose

 It demonstrates how to build and run two different web applications — one with **Flask** and the other with **Django** — and manage them together using **Docker Compose**.

---

##  Project Overview

The repository contains:
- A **Flask** application that displays a simple homepage.
- A **Django** application with an item listing, admin panel, and a form to add new items.
- Dockerfiles for both apps.
- A Docker Compose configuration to run everything together.

---

## Directory Structure

```
A-32-final/
├── flask_app/
│   ├── app.py
│   └── Dockerfile
│
├── django_app/
│   ├── Dockerfile
│   ├── manage.py
│   ├── myproject/
│   └── itemlist/
│
├── docker-compose.yml
└── README.md
```

---

##  How to Run the Project

###  Prerequisites
Make sure Docker is installed and running on your machine.

### Steps to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/SRCEM-AIM-Class-A/A-32-FINAL.git
   cd A-32-FINAL
   ```

2. Build and run the containers:
   ```bash
   docker-compose up --build
   ```

3. Access the apps in your browser:
   - Flask App: [http://localhost:5000](http://localhost:5000)
   - Django App: [http://localhost:8000](http://localhost:8000)

---

##  App Details

### 🔷 Flask App
- A basic Python Flask app (`app.py`)
- Just displays a homepage message
- Runs on port `5000`
- Dockerized using its own `Dockerfile`

### 🟦 Django App
- Standard Django project (`myproject`)
- Has an app named `itemlist`
- Features:
  - Item list view
  - Form to add new items
  - Admin panel (`/admin`)
- Runs on port `8000`
- Database: SQLite

---

##  Docker Hub Images

If you don’t want to build locally, pull the Docker images directly:

- **Flask App**  
  [chhavipancholi/a-32-final-flaskapp](https://hub.docker.com/r/chhavipancholi/a-32-final-flaskapp)

  ```bash
  docker pull chhavipancholi/a-32-final-flaskapp
  ```

- **Django App**  
  [chhavipancholi/a-32-final-djangoapp](https://hub.docker.com/r/chhavipancholi/a-32-final-djangoapp)

  ```bash
  docker pull chhavipancholi/a-32-final-djangoapp
  ```

---

## Notes

- If needed, run migrations for the Django app:
  ```bash
  docker exec -it a-32-final-djangoapp-1 python manage.py migrate
  ```

- Access the Django admin:
  - Navigate to `/admin`
  - Create superuser:
    ```bash
    docker exec -it a-32-final-djangoapp-1 python manage.py createsuperuser
    ```

---

##  Author

**Chhavi Pancholi**  
AIM Lab – A-32  
GitHub: [github.com/chhavipancholi](https://github.com/chhavipancholi)  
Docker Hub: [hub.docker.com/u/chhavipancholi](https://hub.docker.com/u/chhavipancholi)

---

> Thanks for checking out my project!
