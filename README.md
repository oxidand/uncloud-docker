# Radarr & moarr

```sh
cp .env.example global.env
cp qbittorrentvpn/.env.example qbittorrentvpn/qbittorrentvpn.env
```

- Set env values in env files.
- Follow instructions to configure VPN for [oxidand/qbittorrentvpn](https://github.com/oxidand/docker-qBittorrentvpn)

```sh
docker network create torrent-net

docker-compose \
  --env-file global.env \
  --env-file qbittorrentvpn/qbittorrentvpn.env \
  -f qbittorrentvpn/qbittorrentvpn.yml \
  up -d

docker-compose \
  --env-file global.env \
  --env-file servarr/servarr.env \
  -f servarr/servarr.yml \
  up -d
```
