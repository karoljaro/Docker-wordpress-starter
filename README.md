# Docker WordPress Starter

Prosta konfiguracja `docker-compose` do szybkiego uruchomienia lokalnego środowiska WordPress z bazą danych MariaDB. Idealne do rozwoju i testowania motywów lub wtyczek.

## Wymagania

*   [Docker](https://www.docker.com/get-started)
*   [Docker Compose](https://docs.docker.com/compose/install/) (zazwyczaj dołączany do Docker Desktop)

## Jak używać

1.  **Sklonuj repozytorium:**
    ```bash
    git clone https://github.com/karoljaro/Docker-wordpress-starter.git
    cd Docker-wordpress-starter
    ```
2.  **Sprawdź i dostosuj `docker-compose.yml`:**
    *   **WAŻNE:** Otwórz plik `docker-compose.yml` i zmień domyślne hasła (`MYSQL_ROOT_PASSWORD`, `MYSQL_PASSWORD`, `WORDPRESS_DB_PASSWORD`) na własne, bezpieczne hasła. Upewnij się, że hasło użytkownika bazy danych jest takie samo w sekcjach `db` i `wordpress`.
    *   Możesz dostosować inne parametry, takie jak mapowanie portów (`ports`), nazwy usług czy wolumenów.
3.  **Uruchom kontenery:**
    W terminalu, w głównym folderze repozytorium, uruchom:
    ```bash
    docker compose up -d
    ```
    *(Jeśli używasz starszej wersji, może być konieczne użycie `docker-compose up -d`)*
4.  **Dostęp do WordPressa:**
    Po chwili WordPress będzie dostępny w przeglądarce pod adresem `http://localhost:8080` (lub innym portem, jeśli został zmieniony w pliku `docker-compose.yml`). Przy pierwszym uruchomieniu pojawi się ekran instalacyjny WordPressa.
5.  **Zatrzymywanie kontenerów:**
    Aby zatrzymać kontenery działające w tle:
    ```bash
    docker compose down
    ```
    *(Lub `docker-compose down`)*. Dane zostaną zachowane w wolumenach Dockera (`db_data`, `wordpress_data`). Aby usunąć również wolumeny (utrata danych!), użyj `docker compose down -v`.

## Struktura

*   `docker-compose.yml`: Definicja usług Dockera (WordPress i MariaDB), sieci oraz wolumenów.
*   `db`: Usługa kontenera bazy danych MariaDB.
*   `wordpress`: Usługa kontenera aplikacji WordPress.
*   `db_data`: Nazwany wolumen Dockera do przechowywania danych bazy.
*   `wordpress_data`: Nazwany wolumen Dockera do przechowywania plików WordPress (motywy, wtyczki, uploady).

---

*Repozytorium stworzone jako punkt startowy do pracy z WordPressem na Dockerze.*
