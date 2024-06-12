Step-by-Step Demo
Start the Docker container:

First, make sure your Docker Compose file is running with:


docker-compose up -d
Access the running container:

Open a shell session inside the container:


docker exec -it sqlite sh
Verify SQLite installation:

Check if SQLite is installed:


sqlite3 --version
You should see the SQLite version information.

Create a new SQLite database:

Navigate to the /data directory and create a new SQLite database:


cd /data
sqlite3 demo.db
This will open the SQLite shell.

Create a table:

Inside the SQLite shell, create a table named users:

CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
Insert some data:

Insert some sample data into the users table:

INSERT INTO users (name, age) VALUES ('Alice', 30);
INSERT INTO users (name, age) VALUES ('Bob', 25);
Query the data:

Retrieve the data from the users table:

SELECT * FROM users;
You should see output similar to this:

1|Alice|30
2|Bob|25
Exit the SQLite shell:

To exit the SQLite shell, type:

.quit
Leave the container shell:

To exit the container's shell session, type:

exit
Complete Interaction Example
Here is a complete example of the interaction:

$ docker-compose up -d
$ docker exec -it sqlite sh
Inside the container:

# Verify SQLite installation
sqlite3 --version

# Create and navigate to the database directory
cd /data

# Create a new database and open the SQLite shell
sqlite3 demo.db

# Inside the SQLite shell
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
INSERT INTO users (name, age) VALUES ('Alice', 30);
INSERT INTO users (name, age) VALUES ('Bob', 25);
SELECT * FROM users;
.quit

# Exit the container's shell
exit
This sequence of commands demonstrates creating a new SQLite database, creating a table, inserting data, and querying data within the container.







