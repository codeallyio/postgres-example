## Getting Started

First start
```bash
yarn && yarn init-db && yarn start
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