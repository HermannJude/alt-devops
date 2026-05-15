# Issues fixed

- Added use of `.env` file in `compose.yml`
- Removed `version` which is not needed in newer versions of Docker compose
- Using a fixed version of wordpress
- Set `MYSQL_ROOT_PASSWORD` in the `db` service which was missing and is required for the MySQL image to start
- Port on MySQL is not needed as the services will be able to communicate internally
- Removed `PMA_USER` and `PMA_PASSWORD` to open the login form and avoid intrusion issues.
