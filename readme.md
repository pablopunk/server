# Home Server

> Files to run a server at home using Zero Trust from Cloudflare

## Installation

Before installing the project, ensure that you have the following dependencies installed:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

You will also need a **Cloudflare** account and create a [Tunnel](https://www.cloudflare.com/products/tunnel/) in your Zero Trust dashboard.

To install the project, follow these steps:

1. Clone the repository to your local machine.

``` bash
git clone https://github.com/pablopun/server && cd server
```

2. Copy the example `.env` file and modify it to fit your needs (remember to get your tunnel token).

``` bash
cp .env.example .env
```

3. Build and run all the images:

``` bash
docker-compose up -d
```

> **Note**
> If you don't want to use a particular service, such as Time Machine, simply remove it from the `docker-compose.yml` file.


## Usage

It all runs on docker containers. Once it's running, you can see all of your containers in `http://<your-host>:9000`

- **Cloudflare Tunnel**: Cloudflare's proxy to securely access your services over HTTPS.
- **Nevergiveup**: A little image that checks if your domain is remotely available and restarts cloudflare service if it's not.
- **Time Machine**: Wireless backups for your Mac.
- **Portainer**: GUI for managing Docker containers and images.
- **Watchtower**: Updates your docker images automatically.

## Troubleshooting

If you encounter any issues while installing or using the server, try the following solutions:

- Check that all dependencies are installed correctly.
- Ensure that the `.env` file is configured correctly.
- Check the logs of the Docker containers (in portainer, port 9000) for any error messages.

## License

MIT License

