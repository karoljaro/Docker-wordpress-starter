# Docker WordPress Starter

A simple `docker-compose` setup to quickly launch a local WordPress environment with a MariaDB database. Ideal for developing and testing themes or plugins.

## Requirements

*   [Docker](https://www.docker.com/get-started)
*   [Docker Compose](https://docs.docker.com/compose/install/) (usually included with Docker Desktop)

## How to Use

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/karoljaro/Docker-wordpress-starter.git
    cd Docker-wordpress-starter
    ```
2.  **Check and customize `docker-compose.yml`:**
    *   **IMPORTANT:** Open the `docker-compose.yml` file and change the default passwords (`MYSQL_ROOT_PASSWORD`, `MYSQL_PASSWORD`, `WORDPRESS_DB_PASSWORD`) to your own secure passwords. Ensure the database user password is the same in both the `db` and `wordpress` service sections.
    *   You can customize other parameters like port mapping (`ports`), service names, or volume names.
3.  **Start the containers:**
    In your terminal, from the main repository folder, run:
    ```bash
    docker compose up -d
    ```
    *(If you are using an older version, you might need to use `docker-compose up -d`)*
4.  **Access WordPress:**
    After a moment, WordPress will be available in your browser at `http://localhost:8080` (or a different port if you changed it in `docker-compose.yml`). The standard WordPress installation screen will appear on the first run.
5.  **Stopping the containers:**
    To stop the containers running in the background:
    ```bash
    docker compose down
    ```
    *(Or `docker-compose down`)*. Your data will be preserved in Docker volumes (`db_data`, `wordpress_data`). To remove the volumes as well (data loss!), use `docker compose down -v`.

## Structure

*   `docker-compose.yml`: Defines the Docker services (WordPress and MariaDB), network, and volumes.
*   `db`: The MariaDB database container service.
*   `wordpress`: The WordPress application container service.
*   `db_data`: A named Docker volume for storing database data.
*   `wordpress_data`: A named Docker volume for storing WordPress files (themes, plugins, uploads).

---

*Repository created as a starting point for working with WordPress on Docker.*
