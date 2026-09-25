# payment-gateway-config

Centralized configuration for Payment Gateway — served by `config-server:8888`

## Structure

| File | Description |
|------|-------------|
| `application.yml` | Common config for all services |
| `application-dev.yml` | Common dev overrides |
| `application-prod.yml` | Common prod overrides |
| `discovery-server.yml` | Eureka config (mirror, standalone) |
| `discovery-server-dev.yml` | Eureka dev (self-preservation OFF) |
| `discovery-server-prod.yml` | Eureka prod (self-preservation ON) |
| `config-server.yml` | Config Server self-config |
| `api-gateway.yml` | Template: API Gateway |
| `payment-service.yml` | Template: Payment Service |

## Usage

```bash
# Config Server จะเสิร์ฟตาม pattern: http://localhost:8888/{application}/{profile}
curl http://localhost:8888/payment-service/default
curl http://localhost:8888/payment-service/dev
curl http://localhost:8888/application/prod
```

## Profiles
- `dev`: self-preservation=false, threshold 0.49 (local)
- `prod`: self-preservation=true, threshold 0.85 (production)

## Changelog
ดูที่ `../docs/PRODUCTION_DOC.md#3-changelog--ทุกการแก้ไข`
