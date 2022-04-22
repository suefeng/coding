# Getting Started Notes

## Generating a model

When generating a model, it also generates the migration and related tests

```ruby
$ bin/rails generate model Comment commenter:string body:text article:references
```

This command will generate four files:
File  |	Purpose
-- | --
db/migrate/20140120201010_create_comments.rb | Migration to create the comments table in your database (your name will include a different timestamp)
app/models/comment.rb |	The Comment model
test/models/comment_test.rb | Testing harness for the comment model
test/fixtures/comments.yml | Sample comments for use in testing

In our app, it generates Rspec tests.

## Generating a controller
```ruby
$ bin/rails generate controller Comments
```

This creates five files and one empty directory:
File/Directory | Purpose
-- | --
app/controllers/comments_controller.rb | The Comments controller
app/views/comments/ | Views of the controller are stored here
test/controllers/comments_controller_test.rb | The test for the controller
app/helpers/comments_helper.rb | A view helper file
app/assets/javascripts/comments.coffee | CoffeeScript for the controller
app/assets/stylesheets/comments.scss | Cascading style sheet for the controller

Again, in our app, it generates Rspec tests, and not coffee script but JavaScript


## Pluralize

```ruby
pluralize(@comment.count, "comment")
```

pluralize is a rails helper that takes a number and a string as its arguments. If the number is greater than one, the string will be automatically pluralized.
