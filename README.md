# Portracker — ZimaOS / CasaOS Package

![ZimaOS Compatible](https://img.shields.io/badge/ZimaOS-Compatible-0ea5e9?logo=icloud&logoColor=white)
![CasaOS Compatible](https://img.shields.io/badge/CasaOS-Compatible-22c55e?logo=homeassistant&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker-Compose-2496ed?logo=docker&logoColor=white)
![Architectures](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-8b5cf6)
![Maintainer](https://img.shields.io/badge/Maintainer-George%20(Jacko88888)-f59e0b)

Discover and track open ports on your Docker host(s) with **Portracker**, packaged for **ZimaOS / CasaOS** using a **read-only Docker socket proxy** for safety.

**Credits:** https://github.com/mostafa-wahied/portracker

---

## 🚀 Quick Install (ZimaOS UI)

1. Open **Apps → Custom Install → Compose**  
2. Click **Import from URL**, paste:

https://raw.githubusercontent.com/Jacko88888/portracker-zimaos/main/docker-compose.yml

3. **Install** → then **Open** (default: `http://<your-ip>:4999`)

> Tip: If you prefer a CDN mirror, you can also use  
> `https://cdn.jsdelivr.net/gh/Jacko88888/portracker-zimaos@main/docker-compose.yml`

---

## 🧰 Quick Install (CLI)

```bash
mkdir -p /var/lib/casaos_data/portracker
cd /var/lib/casaos_data/portracker
curl -fsSL https://raw.githubusercontent.com/Jacko88888/portracker-zimaos/main/docker-compose.yml -o docker-compose.yml
docker compose up -d
Web UI: http://<your-ip>:4999

Data path: /var/lib/casaos_data/portracker/portracker-data

CasaOS note: If your system uses /DATA/AppData, edit the volume line in the compose to:

/DATA/AppData/portracker/portracker-data:/data
🔒 Why this package is safer
This package includes linuxserver/socket-proxy with read-only Docker API access:

No --privileged

No host networking

POST=0 (no write actions), only info endpoints required for discovery

📦 What gets deployed
portracker — the web UI (port 4999)

portracker-socket-proxy — minimal helper for Docker API (read-only)

🧪 Verify it’s running

docker ps --format "table {{.Names}}\t{{.Ports}}\t{{.Status}}"
curl -I http://127.0.0.1:4999
docker logs --tail=200 portracker
If Portracker shows errors like ECONNREFUSED socket-proxy:2375, ensure the socket-proxy container is up and healthy.

🗑 Uninstall

cd /var/lib/casaos_data/portracker
docker compose down
# Optional: remove data
rm -rf /var/lib/casaos_data/portracker/portracker-data
(Adjust the path to /DATA/AppData/portracker if you used CasaOS’ default.)

Credits
Portracker by Mostafa Wahied — https://github.com/mostafa-wahied/portracker

### Share link (give people this line)
https://raw.githubusercontent.com/Jacko88888/portracker-zimaos/main/docker-compose.yml

Want a matching repo description too? Use:
ZimaOS / CasaOS package for Portracker — discover and track open ports on your Docker hosts with a safe read-only Docker socket proxy.

::contentReference[oaicite:0]{index=0}

