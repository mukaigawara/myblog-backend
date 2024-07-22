up

```bash
blog-backend % docker compose up -d --build
```

入る

```bash
 docker compose exec go-api-server sh
```

build

```sh
go build -gcflags "all=-N -l" -o tmp/main .
```
