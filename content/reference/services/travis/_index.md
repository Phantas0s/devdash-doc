---
title: Travis CI
weight: 4
---

## Service configuration

```yml
    services:
      travis:
        token: "1234"
```

## Widgets available

| Name                     | Description                                               |
|--------------------------|-----------------------------------------------------------|
| travis.table_builds      | Display last builds information, ordered by finished date |

## Widget Options

### Table Widgets

| Name              | Description                                 | Default value   | Examples      | Comment                   |
|-------------------|---------------------------------------------|-----------------|---------------|--------------------------------|
| row_limit         | Limit the number of rows                    | 5               | 5, 100        |                                |
| repository        | Display last build from specific repository |                 | `devdash`     | Need the option `owner`        |
| owner             | Owner of the specific repository            |                 | `Phantas0s`   | Need the option `repository`   |
