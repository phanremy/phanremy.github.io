---
layout: wiki
title: Cheat sheet - Divers
cate1: Cheat sheets
cate2:
description: Papier de triche, aka cheat sheet, pour retrouver la mémoire
keywords: Code
---

## How to test the repeatability of a test

```jsx
for i in {1..100}; do echo "*** Run $i ***"; rails test test-path.rb || break; done;
```

## How to get just one file from another branch?

you are on a different branch than `main` and you want to retrieve a file (ie. structure.sql) from `main`

```jsx
git checkout main path/to/structure.sql
```

```arduino
heroku pg:psql -a thepackengersapp-staging

> CREATE INDEX index_posts ON public.posts USING btree (user_id, value);
> DROP INDEX index_posts;

```

## Delete branch locally which are deleted remotely

```arduino
git fetch -p && for branch in $(git for-each-ref --format '%(refname) %(upstream:track)' refs/heads | awk '$2 == "[gone]" {sub("refs/heads/", "", $1); print $1}'); do git branch -D $branch; done
```

## Kill Heroku connections

```
heroku pg:killall -r heroku-staging
heroku run rails db:migrate -r heroku-staging
heroku run rails deploy -r heroku-staging
heroku restart -r heroku-staging
```

Et la commande pour avoir la liste des connexions ) la DB :

```
heroku pg:psql -c 'select usename, application_name, backend_start, query, wait_event, backend_type from pg_stat_activity;' -r heroku-staging
```

## Play with zshrc

```jsx
code /Users/phanremy/.zshrc
source ~/.zshrc

code ~/.zshrc
source ~/.zshrc
code ~/.aliases
source ~/.aliases
refresh_db
```

## Access Heroku logs

```
heroku logs --tail -a [app_name]
```
