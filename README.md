# Private proxy via tor/privoxy

## Requirements

- docker compose
- also running under gvisor runsc -> https://gvisor.dev/docs/user_guide/install/

## starting

```shell
docker compose up
```

### nyx

attach within tor container

```shell
docker compose exec tor nyx
```

## Testing

### Tor

check connection

```shell
curl --proxy socks5h://127.0.0.1:9050 https://check.torproject.org/api/ip
```

### Privoxy

check connection 

```shell
curl --proxy http://127.0.0.1:8118 https://check.torproject.org/api/ip
```

## shutdown

```shell
docker compose down
```