# Multi-Container WordPress Deployment with Docker Compose

## Project Overview

This project provides a deployable, multi-container **WordPress** website using **Docker Compose**. It is a classic application stack designed for easy setup and persistence.

The stack consists of two services:

1.  **`db` (MySQL 5.7):** The database engine that stores all site content (posts, users, settings). Data is preserved using a **named volume** (`db_data`) so it is not lost when containers are restarted.
2.  **`wordpress` (WordPress Latest):** The main web application, configured to connect to the `db` service and exposed on the host machine via port 8080.

---

## Setup Instructions

This guide provides the necessary steps to clone, configure, and launch the application.

### Prerequisites

You must have **Docker** and **Docker Compose** installed on your machine.

### 1. Clone the Repository

Clone the project files to your local machine (replace the URL with your actual public repository URL):

```bash
git clone [https://github.com/MissPhantom/wordpress-docker-project.git](https://github.com/MissPhantom/wordpress-docker-project.git)
cd wordpress-docker-project
````

### 2\. Configure Environment Variables

For security, sensitive credentials must be stored in a separate `.env` file, which is kept out of version control via the included `.gitignore`.

1.  **Create the file** using the provided template:
    ```bash
    cp .env.example .env
    ```
2.  **Edit the `.env` file** and replace all placeholder values (e.g., `changeme_...`) with **strong, unique passwords** and usernames.

-----

## Running the Application

### The Exact Command to Start the Application

Start both the database and WordPress containers in **detached mode** (`-d`):

```bash
docker compose up -d
```

### How to Access the Running Application

Once the services are successfully started, you can access the WordPress setup screen in your web browser:

**Visit:** [http://localhost:8080](https://www.google.com/search?q=http://localhost:8080)

-----

### The Exact Command to Stop the Application

To shut down and remove the containers, networks, and **the persistent database volume**, run this command:

```bash
docker compose down --volumes
```

```
```