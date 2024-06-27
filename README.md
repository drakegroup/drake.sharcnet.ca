## Prerequisites

- Linux x64 (ie. Ubuntu 24.04 LTS) with public IP and ports 443 and 80 exposed to the internet
- docker engine ([installation guide](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository))
- DNS A-record for drake.sharcnet.ca should point to the public IP of the server

## Installation

- clone the repo
```bash
git clone https://github.com/drakegroup/drake.sharcnet.ca.git
cd drake.sharcnet.ca
```

- migrate the site data (SQL, secrets, static data)



- spin up the containers:

```bash
docker compose -f nginx.yml up -d
docker compose -f mediawiki.yml up -d
```
