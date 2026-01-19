# Drupal Docker Starter

Docker Compose + Postgres + Nginx + PHP-FPM.

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

## Optional modules

Enable these content types:

### Organization

- Service
- Organization

### Food

- Product
- Ingredient
- Inventory
- Quantity
- Quantitative Unit

### Incident

### Person

- Given name
- Family name
- Outfit
- Hair color (`field_hair_color`)
- Eye color (`field_eye_color`)
- Skin color (`field_skin_color`)

### Outfit

Enable a module like:

```bash
drush en person_schema -y
```

Or set this in your env file:

```
ENABLED_MODULES=organization_schema,food_schema,incident_schema,person_schema
```

## TODO

- add postalAddress content type
- add location content type
- make sure incident content type has an array of persons, description, location, reporter (a person) and datetime fields. everything optional except time and location
- make sure content types have right fields
- make sure content types have right relationships
- login header
- use the starter to make an incident report project
- present incident content type as REST
- use the starter to make a service list project
- use the starter to make a food inventory project
- make a react frontend that lists a content type
- search a content type
- move drupal to its own repo
- move react to its own repo
- add election content type
- add candidate content type
- add business content type with address, name, tag, fields
- provide graphql option

```

```
