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

## committing changes

- `git status`
- `git add .`
- `git commit`
- `git pull`
- resolve any conflicts
- `ddev composer install`
- `ddev craft up`
- `git status` to make sure everything is still committed
- `git push`

### Some thoughts on the database:

ddev database lives in a docker volume, so it subject to being removed in a docker prune. Possible to back it up with: `ddev export-db > backup.sql`, restore it with `ddev import-db < backup.sql`. Access adminer with `ddev adminer` (if that doesn't work `ddev describe`).
