# Issues fixed

- Added `.env` file to store environment variables
- Added healthchecks to ensure services are ready and toggle the `condition: service_healthy` in `depends_on` to ensure services start in the correct order :
  - Wordpress depends on the database to start
  - phpMyAdmin depends on the database to start
- Added a custom networks to allow communication between containers :
  - `blog` allowing Wordpress and the database to communicate
  - `db` allowing the database and phpMyAdmin to communicate
- Added volumes to persist data
- Use locked versions of images to ensure reproducibility
