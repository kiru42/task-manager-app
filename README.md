# README

## Deploy to heroku

### Gemfile

```yaml
production:
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") {5} %>
  url: <%= ENV['DATABASE_URL'] %>
```

### database.yml

```ruby
# ...
group :development, :test do
  # ...
  gem 'sqlite3', '~> 1.3.6'
end
# ...
group :production do
  gem 'pg'
end
# ...
```

### Heroku

```bash
bundle install
git add .
git commit -m "Preparing for Heroku deploy"
heroku apps:create <YOUR_APP_NAME>
heroku addons:create heroku-postgresql:hobby-dev
git push heroku master
heroku run rails db:master
```
