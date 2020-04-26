## Getting Started

Just clone the repo, tweak `.env` file in the root of the project, and run `yarn start`:

```bash
$ git clone https://github.com/kriasoft/nodejs-api-starter.git example-api
$ cd example-api                # Change current directory to the newly created one
$ yarn                  # Install Node.js dependencies
$ yarn start                    # Launch Node.js API application. Or, yarn start --env=local
```

The API server must become available at [http://localhost:8080/graphql](http://localhost:8080/graphql)
([live demo][demo]).

### How to Migrate Database Schema

While the app is in development, you can use a simplified migration workflow by
creating a backup of your existing database, making changes to the existing
migration file (see `migrations/20180101000000_initial.ts`), re-apply the
migration and restore data from the backup file (`backup.sql`):

```bash
$ yarn db-backup --env=dev      # Or, yarn db-backup --env=test
$ yarn db-reset-dev             # Or, yarn db-reset-test
```

Upon deployment to production, switch to normal migration workflow:

```bash
$ yarn db-change <name>         # Create a new database migration file
$ yarn db-migrate --env=dev     # Migrate database to the latest version
```

**HINT**: Test your migration thoroughly with a local instance of the DB first
(by using `--env=local` or `--env=dev` (default) flag) then apply it to your
`test` or `prod` database instance using `--env=test` or `--env=prod` command
argument.

Other helpful database scripts:

```bash
$ yarn db-version --env=dev     # Print the version number of the last migration
$ yarn db-rollback --env=dev    # Rollback the latest migration
$ yarn db-restore --env=dev     # Restore database from backup.sql
$ yarn db-seed --env=dev        # Seed database with test data
$ yarn db --env=dev             # Open Knex.js REPL shell (type ".exit" for exit)
$ yarn psql --env=dev           # Open PostgreSQL shell (type "\q" for exit)
```

### How to Test

```bash
$ yarn lint                     # Check JavaScript and CSS code for potential issues
$ yarn lint-fix                 # Attempt to automatically fix ESLint warnings
$ yarn check                    # Check source code for type errors
$ yarn test                     # Run unit tests. Or, `yarn test --watch`
```

For more information visit https://jestjs.io/docs/getting-started

### How to Deploy

```bash
$ yarn build                    # Build the app in production mode (NODE_ENV=production)
$ yarn deploy-test              # Deploy the app to TEST environment
$ yarn deploy-prod              # Deploy the app to PROD environment
```

For more information refer to the [Deployment](https://github.com/kriasoft/nodejs-api-starter/wiki/deployment)
guide in the project's Wiki.