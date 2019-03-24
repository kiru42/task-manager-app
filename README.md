# README

## Deploy to heroku

```bash
bundle install
git add .
git commit -m "Preparing for Heroku deploy"
heroku apps:create <YOUR_APP_NAME>
heroku addons:create heroku-postgresql:hobby-dev
git push heroku master
heroku run rails db:master
```
