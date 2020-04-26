## Getting Started

Just clone the repo, tweak `.env` file in the root of the project, and run `yarn start`:

```bash
yarn
yarn db-init
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