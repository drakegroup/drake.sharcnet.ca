# drake.sharcnet.ca website infrastructure

This repo contains all configuration needed to host the website for [Dr. Gordon Drake's Research Group](https://drake.sharcnet.ca).

## Prerequisites

- Linux x64 (ie. Ubuntu 24.04 LTS) with public IP and ports 443 and 80 exposed to the internet
- docker engine ([installation guide](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository))
- DNS A-record for drake.sharcnet.ca should point to the public IP of the server
- site secrets (stored in `~/drake.shacnet.ca/.env` file)
- site data mounted to `/media/backedup`

## Installation

- clone the repo
```bash
git clone https://github.com/drakegroup/drake.sharcnet.ca.git
cd drake.sharcnet.ca
```

- migrate the site data and secrets (SQL, secrets, static data)
```bash
sudo cp -r /media/backedup/var/lib/mysql ~/drake.sharcnet.ca/db
sudo cp -r /media/backedup/var/www/html ~/drake.sharcnet.ca/html
source .env
```

- spin up the environment

```bash
sudo docker compose -f nginx.yml up -d
sudo docker compose -f mediawiki.yml up -d
```
