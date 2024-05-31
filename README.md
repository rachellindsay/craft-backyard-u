# Craft site for Backyard University

## setting up local development first time

- need ddev installed (probably)
- pull the repo
- copy .env.example.dev to .env
- `ddev start` to start ddev
- `ddev composer install` to do composer install
- `ddev craft install` for initial craft install.
- `ddev craft up` for any migrations (probably none)

## after every pull

- `ddev composer install`
- `ddev craft up`
