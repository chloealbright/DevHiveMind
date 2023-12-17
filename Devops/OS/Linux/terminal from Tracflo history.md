```bash
knex migrate:up
knex migrate:latest
knex migrate:rollback --all

npm run test-setup
npm run test -- -g "letterController"
npm run test -- -g "letterController GET"
```