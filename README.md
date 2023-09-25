# wrk-docker

## push

```bash
docker buildx build --platform linux/amd64,linux/arm64 -t fengjx/wrk:latest --push .
```

## usage

```bash
docker run --rm -v $(pwd):/data fengjx/wrk:latest -s hello.lua -d60s -t4 -c100 --latency https://www.example.com
```

