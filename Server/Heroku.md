# Heroku

DB backend
heroku addons:create heroku-postgresql -a gymrats

``` shell
heroku pg:pull DATABASE_URL gym -a gymrats

heroku pg:push gym DATABASE_URL -a gymrats
(ignore the error via [https://comm.support.ca.com/kb/error-message-must-be-owner-of-extension-plpgsql-seen-during-the-postgres-database-restore-step/kb000004307](https://comm.support.ca.com/kb/error-message-must-be-owner-of-extension-plpgsql-seen-during-the-postgres-database-restore-step/kb000004307) 
 
heroku pg:reset -a gymrats 
Force migrate
heroku run rake db:migrate -a gymratsForce seed
heroku run rake db:seed -a gymrats
```