# backend

## Run

```
go run .
```

## Build

```
go build
```

## Configuration

- `PORT` - port to listen on (default: `8000`)
- `REDIS` - Redis host (default: `127.0.0.1`)
- `REDIS_PASSWORD` - Redis password (default: `''` - empty string)
- `EXTRA_TEXT` -  Extra text to display (default: `''`)
- `EXTRA_TEXT_SUFFIX` -  Extra text suffix to display after the text value (default: `''`)
- `HTTP_CLOSE_CONNECTION` - Close HTTP connection after every response when set to `1` (default: `0`)

## API Endpoints

### Counter Endpoints

- **GET /api/counter** - Get and increase counter value in JSON format
- **GET /api/counter-txt** - Get and increase counter value in plain text format

### Health Check Endpoints

- **GET /api/livez** or **GET /livez** - for liveness probe
- **GET /api/readyz** or **GET /readyz** - for readiness probe

### Information Endpoints

- **GET /api/version** or **GET /version** - Get application version
- **GET /api/status** or **GET /status** - Get application status and runtime information

### Monitoring Endpoints

- **GET /metrics** - Prometheus metrics endpoint

## Run Dependencies

Redis

```
docker run --name redis -d -p 6379:6379 redis
```
