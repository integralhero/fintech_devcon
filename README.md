# fintech_devcon

## IAV Workshop

Build an app that connects to the MX Bank (OAuth) connection, displays a list of verified accounts to select, and gets account numbers for the one that was selected.

### Client ID

```
fintech_devcon
```

### API Key

```
2e45e16d42c769a174ba52ce2567c6a42e56ee49
```

### Examples

#### Create a user

```
curl -i -X POST 'https://int-api.mx.com/users' \
  -u 'fintech_devcon:2e45e16d42c769a174ba52ce2567c6a42e56ee49' \
  -H 'Accept: application/vnd.mx.api.v1+json' \
  -H 'Content-Type: application/json' \
  -d '{ "user": { "metadata": "{}" } }'
```

#### Create a Connect URL

```
curl -i -X POST 'https://int-api.mx.com/users/{USER_GUID}/widget_urls' \
  -u 'fintech_devcon:2e45e16d42c769a174ba52ce2567c6a42e56ee49' \
  -H 'Accept: application/vnd.mx.api.v1+json' \
  -H 'Content-Type: application/json' \
  -d '{ "widget_url": { "widget_type": "connect_widget", "mode": "verification", "wait_for_full_aggregation": true } }'
```

#### Get accounts for user

```
curl -i -X GET 'https://int-api.mx.com/users/{USER_GUID}/accounts' \
  -u 'fintech_devcon:2e45e16d42c769a174ba52ce2567c6a42e56ee49' \
  -H 'Accept: application/vnd.mx.api.v1+json' \
  -H 'Content-Type: application/json'
```

#### Get account numbers for a specific account

```
curl -i -X GET 'https://int-api.mx.com/users/{USER_GUID}/accounts/{ACCOUNT_GUID}/account_numbers' \
  -u 'fintech_devcon:2e45e16d42c769a174ba52ce2567c6a42e56ee49' \
  -H 'Accept: application/vnd.mx.api.v1+json' \
  -H 'Content-Type: application/json'
```

### Extras

#### Beta versions of API client libraries:

- **Ruby** https://github.com/mxenabled/mx-platform-ruby
- **Java** https://github.com/mxenabled/mx-platform-java
- **Node** https://github.com/mxenabled/mx-platform-node

#### OpenAPI spec for MX Platform API:

https://github.com/mxenabled/openapi