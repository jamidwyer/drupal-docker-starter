# Incident Schema

Provides an optional **Incident** content type for the starterpack.

## Installs
- Content type: `incident`
- Fields:
  - **Required**
    - `field_incident_time` (datetime)
    - `field_location` (text)
  - Optional
    - `body` (description)
    - `field_reporter` (entity reference → Person, single)
    - `field_persons` (entity reference → Person, unlimited)

## REST (core)
This module enables a basic core REST resource for nodes (`entity:node`) using JSON serialization and cookie auth.
It also adds two optional roles:
- `api_reader` (GET via REST)
- `api_writer` (GET/POST via REST + create content)

Assign roles to users as needed.

## Enable
```bash
drush en incident_schema -y
```
