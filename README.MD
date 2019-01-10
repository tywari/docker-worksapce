# Web-developer workspace on Docker!
The docker image contains LEMP stack (Linux Nginx MySQL Php) with node and composer which is suitable for web development. **Note** that the container contains PHP version 5.6.

## Installation

Clone the repository.

```console
user@domain:~$ git clone https://github.com/
```

Place your project files in `repository/` directory. Configure virtual hosts by adding Nginx configuration file to `nginx-conf/` directory. and run the container using

```console
user@domain:~$ cd docker-workspace
user@domain:~/docker-workspace$ docker-compose up -d --build workspace
```

Once the container is running, you can enter the container using

```console
user@domain:~/docker-workspace$ docker exec -it workspace bash
```

Update your host file to add virtual hosts
    - `C:\Windows\System32\drivers\etc\hosts` on Windows
    - `/etc/hosts` on Linux/Mac
    - `127.0.0.1 {server_name}` as defined in the nginx-config files. You will need to add all the `{server_name}` defined in each config file.

**Test the URLs in the browser!!** [http://localhost](http://localhost)

Exit the container using

```console
user@domain:~/docker-workspace$ docker-compose down
```

## Directory info

| Project Directory | Container Directory | Description |
| --- | --- | --- |
| `repository/` | `/var/www/html/` |  Use this directory for storing project files. |
| `nginx-config/` | `/var/nginx/sites-available/` <br/> `/var/nginx/sites-enabled` | Configure virtual hosts by adding Nginx configuration files. A sample file is provided at `nginx-config/default`. |
