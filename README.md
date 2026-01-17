# Drupal Docker Starter (Postgres)

Docker Compose + Postgres + Nginx + PHP-FPM.

This repo does **not** commit secrets or production data. Use env files.

## One-time: create the Drupal codebase

From the repo root:

```bash
composer create-project drupal/recommended-project drupal
cd drupal
composer require drush/drush
cd ..
```

## Create your env file

```bash
cp .env.example .env.local
```

## Bootstrap

```bash
./scripts/bootstrap.sh .env.local
```

Then open: http://localhost:8080

Admin creds (dev default): `admin` / `admin`

## Optional starter kit: Hord schema

Enables these content types:
- Service
- Organization
- Product
- Ingredient
- Inventory
- Quantity
- Quantitative Unit

Also creates a taxonomy vocabulary:
- Tag

Enable it after install:

```bash
docker compose exec php vendor/bin/drush en hord_schema -y
```

Or set this in your env file:

```
STARTER_KITS=hord_schema
```
