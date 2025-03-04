# Auction Website

This is an eBay-like auction website built using **Django** with **Bootstrap 5** and **Chart.js** that uses a **PostgreSQL** database to store data.

![plot](https://github.com/BobsProgrammingAcademy/Auction-Website/blob/main/static/images/auctions.png?raw=true)

![plot](https://github.com/BobsProgrammingAcademy/Auction-Website/blob/main/static/images/dashboard.png?raw=true)

## Prerequisites

Install the following prerequisites:

1. [Python 3.9.12 or higher](https://www.python.org/downloads/)
2. [PostgreSQL](https://www.postgresql.org/download/)
3. [Visual Studio Code](https://code.visualstudio.com/download)


## Installation

### 1. Create a virtual environment

From the **root** directory run:

```bash
python -m venv venv
```

### 2. Activate the virtual environment

From the **root** directory run:

```bash
source venv/bin/activate
```

### 3. Install required dependencies

From the **root** directory run:

```bash
pip install -r requirements.txt
```

### 4. Set up a PostgreSQL database

With **PostgreSQL** up and running, in a new Terminal window run:

```bash
dropdb --if-exists auctions
```

Start **psql**, which is a terminal-based front-end to PostgreSQL, by running the command:

```bash
psql postgres
```

Create a new PostgreSQL database:

```sql
CREATE DATABASE auctions;
```

Create a new database admin user:

```sql
CREATE USER yourusername WITH SUPERUSER PASSWORD 'yourpassword';
```

To quit **psql**, run:

```bash
\q
```

### 5. Set up environment variables

From the **root** directory run:

```bash
touch .env
```

The **touch** command will create the **.env** file in the **root** directory. This command works on Mac and Linux but not on Windows. If you are a Windows user, instead of using the command line, you can create the **.env** file manually by navigating in Visual Studio Code to the Explorer, and selecting the option **New File**.


Next, declare environment variables in the **.env** file. Make sure you don't use quotation marks around the strings.

```bash
SECRET_KEY=yoursecretkey
DEBUG=True
DATABASE_NAME=auctions
DATABASE_USER=yourusername
DATABASE_PASS=yourpassword
DATABASE_HOST=localhost
```

### 6. Run migrations

From the **root** directory run:

```bash
python manage.py makemigrations
```
```bash
python manage.py migrate
```

### 7. Create an admin user to access the Django Admin interface

From the **root** directory run:

```bash
python manage.py createsuperuser
```

When prompted, enter a username, email, and password.


## Run the application

From the **root** directory run:

```bash
python manage.py runserver
```

### View the application

Go to http://127.0.0.1:8000/ to view the application.


## Add data to the application

Add data through Django Admin.

Go to http://127.0.0.1:8000/admin to access the Django Admin interface and sign in using the admin credentials.
