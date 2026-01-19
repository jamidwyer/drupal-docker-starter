# incident_schema

Optional schema module that adds an **Incident** content type and REST defaults.

## What it installs

- Content type: `Incident` (`incident`)
- Fields:
  - Required:
    - `field_incident_time` (Datetime)
    - `field_location` (Text)
  - Optional:
    - `body` (Description)
    - `field_reporter` (Entity reference → `person`)
    - `field_persons` (Entity reference → `person`, unlimited)

## Dependencies

- `person_schema` (provides the `person` content type used by references)
- Core: `rest`, `serialization`

## REST defaults

Installs REST config for the core `entity:node` resource (GET/POST, JSON, cookie auth) and adds two roles:

- `api_reader` (read via REST)
- `api_writer` (read + create incidents via REST)

> Cookie auth is suitable for same-origin/session-based API calls. If you later use Auth0 Bearer tokens, you'll add a JWT/OIDC auth provider and adjust REST authentication accordingly.
