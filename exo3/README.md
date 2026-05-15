# Issues fixed

- Added `.env` file to store environment variables
- Added healthchecks to ensure services are ready and toggle the `condition: service_healthy` in `depends_on` to ensure services start in the correct order :
  - Mattermost depends on the database to start
- Added a custom networks to allow communication between containers :
  - `db_net` allowing the database and Mattermost to communicate
- `?sslmode=disable` added to the database connection string to allow Mattermost to connect to the database without SSL, which is not supported in this setup
- Added volumes to persist data
- Use locked versions of images to ensure reproducibility
