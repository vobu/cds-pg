# cds-pg - PostgreSQL adapter for SAP CDS (CAP)

This node module provides an adapter to the PostgreSQL database.

## Current status

This is a first alpha version! It can connect to a PostgreSQL database and execute a simple SELECT statement. Please help us to improve by your contribution.

## Installation

Add this package to your [SAP Cloud Application Programming Model](https://cap.cloud.sap/docs/) project by running:

```bash
npm install cds-pg
```

Then add this configuration to the cds section of your package.json:

```JSON
  "cds": {
    "requires": {
      "db": {
        "kind": "postgres"
      },
      "postgres": {
        "impl": "cds-pg",
        "model": [
          "srv"
        ]
      }
    }
  }
```

For local development you can provide the credentials in the file `default-env.json`:

```JSON
{
  "VCAP_SERVICES": {
    "postgres": [
      {
        "name": "postgres",
        "label": "postgres",
        "tags": [
          "postgres"
        ],
        "credentials": {
          "host": "localhost",
          "port": "5432",
          "database": "dbname",
          "user": "postgres",
          "password": "postgres"
        }
      }
    ]
  }
}
```

[pg-beershop](https://github.com/gregorwolf/pg-beershop) provides an example project.
