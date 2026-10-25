# Wii/DS GPSP Server

OpenPak's Wii/DS GPSP Server.

| | |
| --- | --- |
| Network | Wii, DS |
| Role | GameSpy player search and otherslist; current-session verification is delegated to GPCM |
| Depends on | [`wfc-gpcm`](https://github.com/openpak/wfc-gpcm) (`WFC_GPCM_URL`) |
| Image | `ghcr.io/openpak/wfc-gpsp` |
| Based on | [WiiLink WFC](https://github.com/WiiLink24/wfc-server) (AGPL-3.0) |
| Licence | AGPL-3.0-only |

## What it serves

| Endpoint | What |
| --- | --- |
| GameSpy player search | Player search (`gpsp/search.go`) |
| GameSpy otherslist | Otherslist (`gpsp/otherslist.go`) |
| Internal HTTP | `GET /healthz` (unauthenticated); `WFC_HTTP_ADDR` defaults to `:20201` |

## Run

```sh
GOWORK=off go test -mod=vendor ./...
GOWORK=off go vet -mod=vendor ./...
docker build -t wfc-gpsp .
```

## Docs

- [Protocol](docs/protocol.md)
- [Evidence](docs/evidence.md)
- [Deploy](docs/deploy.md)
- [Notes](docs/notes.md)

## Licence

AGPL-3.0-only. See [LICENSE](LICENSE).
