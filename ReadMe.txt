Steps:
Make sure that larave is install on your computer.

1) Please extract in a separate folder where you want Laravel Docker.

2) Go to the folder where the docker.yml file is present and open CMD. Run the following command:Note: If there's another container running on the same port, run this command before setting up Docker.

* docker-compose down

3) Run the following command to set up Docker:

*docker-compose up

After completing Docker setup, start the services using:

* docker-compose up -d

4) To connect MySQL service to a local machine admin panel (Workbench/PHPMyAdmin), please retrieve the correct details from the .env file:
Host name
Port
Username
Password
If the database is not connecting, find the MySQL host IP address using the following command:

* docker ps -a
*docker inspect <container_id>

Then, take the IP address under "IPAddress" and use it as the host name in Workbench. Also, update the .env file for DB_HOST.

5) After successfully connecting to the database, access Laravel on port http://localhost:8000/.

6) Command to enter inside the Laravel container:
 *docker-compose exec app bash

7) Run the migration to create the tables:

* php artisan migrate

8) The database/seeds/ directory contains seeders to populate the tables. Run the following command to seed the database:

* php artisan db:seed --class=seederName

9) Access the login webpage at:
 
*http://localhost:8000/login



