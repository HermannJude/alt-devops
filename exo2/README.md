# Issues fixed

- Added `.env` file to store environment variables
- Added healthchecks to ensure services are ready and toggle the `condition: service_healthy` in `depends_on` to ensure services start in the correct order :
  - Nextcloud depends on the database and Redis to start
- Added a custom networks to allow communication between containers :
  - `db_net` allowing the database and Nextcloud to communicate
  - `redis_net` allowing Redis and Nextcloud to communicate
- Added volumes to persist data
- Use locked versions of images to ensure reproducibility
