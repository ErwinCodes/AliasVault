# SQL Generation Scripts

This directory contains scripts to generate SQL files from Entity Framework Core migrations and convert them to TypeScript constants which are used by the `./shared/vault-sql` shared TS library.

This shared TS library is consumed by the web app, browser extensions and mobile apps for vault creation and upgrades.

Refer to the docs `upgrade-ef-client-model.md` for how this scripts are used.