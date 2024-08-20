# WordPress with MySQL Docker Compose Setup
This project sets up WordPress with MySQL using Docker Compose, including persistent volumes for data storage and backup purposes.

## Project Structure
The setup includes two main containers:
1. WordPress
2. MySQL

Both containers have volumes attached for data persistence.

## Prerequisites
- Docker
- Docker Compose

## Quick Start
1. Clone this repository:
2. Start the containers:
3. Access WordPress at `http://localhost:5500`

## Docker Compose Configuration
The `docker-compose.yml` file defines two services:

### MySQL Service
- Uses MySQL 5.7 image
- Environment variables set for root password, database name, user, and password
- Volume attached for data persistence: `db_data:/var/lib/mysql`

### WordPress Service
- Uses latest WordPress image
- Depends on MySQL service
- Environment variables set to connect to MySQL database
- Port 8080 on host mapped to port 80 in container
- Volume attached for WordPress files: `wordpress_data:/var/www/html`

## Volumes

Two volumes are created for data persistence:
1. `db_data`: Stores MySQL database files
2. `wordpress_data`: Stores WordPress files

These volumes ensure that your data is not lost when containers are stopped or removed.

## Customization
You can customize the setup by modifying the `docker-compose.yml` file:
- Change MySQL version
- Modify database credentials (remember to update in both services)
- Change the port mapping for WordPress

## Backup
To backup your data, you can copy the contents of the Docker volumes. The volume locations can be found using:
## Stopping the Services

To stop the services, run:
docker-compose down
