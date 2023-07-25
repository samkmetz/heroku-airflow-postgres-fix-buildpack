# heroku-airflow-postgres-fix-buildpack
This buildpack tweaks the environment variables for a given application to account for the $database variable not being sqlalchemy 1.4+ compliant

When Airflow moved to requiring postgres connection strings to start with "postgresql://" that broke the ability to deploy on heroku as the auto built $database_url config variable still uses the "postgres://" convention.

This script helps correct that by setting some of the most common config vars to be compliant.
