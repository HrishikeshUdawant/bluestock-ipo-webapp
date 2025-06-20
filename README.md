Follow these command to run this project:

git clone https://github.com/HrishikeshUdawant/bluestock-ipo-webapp

cd bluestock-ipo-webapp

pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver



How to connect a Django application to your PostgreSQL database

## Setting Up PostgreSQL Database

1. **Install PostgreSQL:**

   Make sure PostgreSQL is installed on your system. You can download it from the official [PostgreSQL website](https://www.postgresql.org/download/).

2. **Create a PostgreSQL Database and User:**

   Once PostgreSQL is installed, create a new database and a user for your Django application. You can do this using the PostgreSQL command-line interface (`psql`) or a graphical tool like pgAdmin.

   Open your terminal and run the following commands:


CREATE DATABASE bluestock;
CREATE USER Hrishikesh WITH PASSWORD '1234';
ALTER ROLE Hrishikesh SET client_encoding TO 'utf8';
ALTER ROLE Hrishikesh SET default_transaction_isolation TO 'read committed';
ALTER ROLE Hrishikesh SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE bluestock TO Hrishikesh;



Install PostgreSQL Adapter for Python

pip install psycopg2-binary



DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'bluestock',
        'USER': 'Hrishikesh',
        'PASSWORD': '1234',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

Apply Migrations:
-->python manage.py makemigrations

-->python manage.py migrate

-->python manage.py runserver
