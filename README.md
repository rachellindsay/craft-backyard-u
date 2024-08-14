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

## committing changes on ddev

- `git status`
- `git add .`
- `git commit`
- `git pull`
- resolve any conflicts
- `ddev composer install`
- `ddev craft up`
- `git status` to make sure everything is still committed
- `git push`

(All changes to the control panel need to be made in ddev and then pulled into Digital Ocean. Settings have been turned off on live control panel)

To update Digital Ocean

- `git status`
- `git pull`
- `composer8.2-sp install`
- `php8.2-sp craft up`

### Some thoughts on the database:

ddev database lives in a docker volume, so it subject to being removed in a docker prune. Possible to back it up with: `ddev export-db > backup.sql`, restore it with `ddev import-db < backup.sql`. Access adminer with `ddev adminer` (if that doesn't work `ddev describe`).
