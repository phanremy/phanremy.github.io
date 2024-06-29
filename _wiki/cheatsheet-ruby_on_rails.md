---
layout: wiki
title: Cheat sheet - Ruby on Rails
cate1: Ruby on Rails
cate2:
description: Papier de triche, aka cheat sheet, pour retrouver la mémoire
keywords: Ruby on Rails
---

## How to search in a jsonb attribute with keys and values of hash using PG

https://www.postgresql.org/docs/12/functions-json.html

```jsx
Post.where("hash_details->'array_details'->0 = '?'", id)
    .where("hash_details->>'text_details' = ?", title)
```

## How to test the repeatability of a test

```jsx
for i in {1..100}; do echo "*** Run $i ***"; rails test test-path.rb || break; done;
```

## How to get just one file from another branch?

you are on a different branch than `main` and you want to retrieve a file (ie. structure.sql) from `main`

```jsx
git checkout main path/to/structure.sql
```

## How to use `delegate_missing_to`

With this method, it is required to write `article.title` or `article.body`

```ruby
module Articles
  class BuildPost
    attr_reader :article

    delegate_missing_to :article

    def initialize(article)
      @article = article
    end

    def call
      Post.new(title: title, body: body)
    end
  end
end
```

## Update multiple instances with different values in SQL

```sql
ActiveRecord::Base.connection.execute("
          UPDATE posts
          SET posts.upvote = row.upvote
          FROM (VALUES (1, 100), (2, 50))
          AS row(id, upvote)
          WHERE row.id = posts.id;
        ")
```

## Transform a string into a class and vice versa

`humanize` `camelize`

```ruby
PostCategory.name.demodulize.underscore
> "post_category"
```

```ruby
Object.const_get("Post CateGory".parameterize.underscore.camelize)
> PostCategory
```

OR

```ruby
"Post CateGory".parameterize.underscore.camelize.constantize
> PostCategory
```

## How to metaprogram instance variables dynamically?

```ruby
instance_variable_set("@coucou", "salut")
@coucou
> "salut"
instance_variable_get("@coucou")
> "salut"
```

## Know the source location of a method

```ruby
self.method(:customs).source_location
```

## How to metaprogram creation of methods

```ruby
class Post
  class << self
    %w[main secondary].each do |category|
      define_method "#{category}_comment" do
        send(category).first&.content
      end
    end
  end
end
```

will create

```ruby
> @post.main_comment
> @post.secondary_comment
```

## How to measure a method performance

```ruby
require 'benchmark'
puts(Benchmark.measure do
  posts = Post.where(attribute: nil)
  method_on(posts)
end)
```

## How To Inflect

config/initializers/inflections.rb

Be sure to restart your server when you modify this file.

Add new inflection rules using the following format. Inflections
are locale specific, and you may define rules for as many different
locales as you wish. All of these examples are active by default:

```ruby
ActiveSupport::Inflector.inflections(:en) do |inflect|
  inflect.plural /^(ox)$/i, '\1en'
  inflect.singular /^(ox)en/i, '\1'
  inflect.irregular 'person', 'people'
  inflect.uncountable %w( fish sheep )
end
```

These inflection rules are supported but not enabled by default:

```ruby
## frozen_string_literal: true

ActiveSupport::Inflector.inflections(:en) do |inflect|
  inflect.acronym 'RESTful'
end
```

```arduino
heroku pg:psql -a thepackengersapp-staging

> CREATE INDEX index_regulations ON public.regulations USING btree (rule_id, value);
> DROP INDEX index_regulations;

```

## Delete branch locally which are deleted remotely

```arduino
git fetch -p && for branch in $(git for-each-ref --format '%(refname) %(upstream:track)' refs/heads | awk '$2 == "[gone]" {sub("refs/heads/", "", $1); print $1}'); do git branch -D $branch; done
```

## How to search in a JSON in SQL

```ruby
GoodJob::Job.where("serialized_params->'arguments'->0 = '?'", id)
            .where("serialized_params->>'job_class' = ?", class_name)

irb(main):010:0> GoodJob::Job.last.serialized_params
=> {"arguments"=>[nil, 42],
    "job_class"=>"NameJob"}
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
