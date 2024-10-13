# DigitalOcean Managed Database Primary Key Constraint Remover

Bash script to remove primary key restrictions on DigitalOcean managed SQL databases via Curl, experienced when using Prisma ORM for relations.

## Script

```bash
curl -X PATCH \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <DIGITAL_OCEAN_TOKEN>" \
  -d '{"config": {"sql_mode": "ANSI,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION,NO_ZERO_DATE,NO_ZERO_IN_DATE,STRICT_ALL_TABLES","sql_require_primary_key": false}}' \
  "https://api.digitalocean.com/v2/databases/<DATABASE_ID>/config" -k
```

## Requirements

- DigitalOcean account
- Curl

