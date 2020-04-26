## Getting Started

First start
```bash
yarn && yarn db-init && yarn start
```

Any other start
```bash
yarn start
```


### Queries to test
```graphql
{
  users {
    edges {
      node {
        username
      }
    }
  }
}
```