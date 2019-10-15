---
title: Travis CI
weight: 4 
---

## Authorization

You don't need any token if the repositories you want to track are public. In that case, use the token `none` in the configuration.

Otherwise, you need the Travis CI's API authorization:

1. Go to your [Travis CI account](https://travis-ci.org/) in your favorite browser
2. Click on your avatar (top right corner)
3. Click on "Settings"
4. Click on the tab "Settings" 
5. Copy your API authentication and past it as the `token` value in your configuration file

## Service configuration

```yml
    services:
      travis:
        token: none
```

## Widgets available

| Name                     | Description                                      |
|--------------------------|--------------------------------------------------|
| travis.table_builds      | Display the last builds ordered by finished date |

## Widget Options

### Table Widgets

| Name       | Description                                                            | Default value | Examples    | Availability |
|------------|------------------------------------------------------------------------|---------------|-------------|--------------|
| row_limit  | Limit the number of rows                                               | 5             | 5, 100      |              |
| repository | Repository you want to track. If omitted, every repository will appear |               | `devdash`   |              |
| owner      | The owner of the repository                                            |               | `Phantas0s` |              |
