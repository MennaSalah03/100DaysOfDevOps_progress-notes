Unlike the task title, it wasn't to install PostgreSQL but to use it directly and create a user with a password, a database, and give the user you created privilege to the DB.

Note: It was specified you mustn't restart the service ever.

Used Commands:
```bash
# Create user called kodekloud_joy
sudo -u postgres createuser kodekloud_joy

# Set password
sudo -u postgres psql -c "ALTER USER kodekloud_joy WITH PASSWORD 'ksH85UJjhb';"

# Create the database kodekloud_db2
sudo -u postgres createdb kodekloud_db2

# Grant privileges
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE kodekloud_db2 TO kodekloud_joy;"

# Make user the owner (optional but recommended for full control)
sudo -u postgres psql -c "ALTER DATABASE kodekloud_db2 OWNER TO kodekloud_joy;"
```

## Resources
- [PostgreSQL in 100 Seconds](https://www.youtube.com/watch?v=n2Fluyr3lbc)
- Claude help with needed PostgreSQL commands.