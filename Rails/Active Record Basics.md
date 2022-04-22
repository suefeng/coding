# Active Record Basics

## Active Record as an Object Relational Mapping (ORM) Framework
They provide these abilities:

- Represent models and their data.
- Represent associations between these models.
- Represent inheritance hierarchies through related models.
- Validate models before they get persisted to the database.
- Perform database operations in an object-oriented fashion.

## Reserved column names

name | notes
-- | --
created_at | Automatically gets set to the current date and time when the record is first created.
updated_at | Automatically gets set to the current date and time whenever the record is updated.
lock_version | Adds optimistic locking to a model.
type | Specifies that the model uses Single Table Inheritance.
(association_name)_type | Stores the type for polymorphic associations.
(table_name)_count | Used to cache the number of belonging objects on associations. For example, a comments_count column in an Article class that has many instances of Comment will cache the number of existent comments for each article.

[Optimistic locking](https://api.rubyonrails.org/v5.2.7/classes/ActiveRecord/Locking/Optimistic.html) allows multiple users to access the same record for edits, and assumes a minimum of conflicts with the data. It does this by checking whether another process has made changes to a record since it was opened, an ActiveRecord::StaleObjectError exception is thrown if that has occurred and the update is ignored.

## Overriding the Naming Conventions

Sometimes you may use Rails with an existing database or want to use a different naming convention. You may define the overrides in the model class.

### Table name override

```ruby
class Product < ApplicationRecord
  self.table_name = "my_products"
end
```

### Fixture override

```ruby
class ProductTest < ActiveSupport::TestCase
  set_fixture_class my_products: Product
  fixtures :my_products
  ...
end
```

### Primary key override

```ruby
class Product < ApplicationRecord
  self.primary_key = "product_id"
end
```

## CRUD: Reading and Writing Data

### Options for Create 

```ruby
User.create(name: "David", occupation: "Designer")
``` 
```ruby
user = User.new
user.name = "David"
user.occupation = "Designer"
user.save
```
```ruby
user = User.new do |u|
  u.name = "David"
  u.occupation = "Code Artist"
end
user.save
```

### Options for Read

There are a lot of different ways

### Options for Update

```ruby
user = User.find_by(name: "David")
user.name = "Dave"
user.save
```
```ruby
user = User.find_by(name: "David")
user.update(name: "Dave")
```
```ruby
User.update_all "max_login_attempts = 3, must_change_password = 'true'"
```

### Options for Delete

```ruby
user = User.find_by(name: "David")
user.destroy
```
```ruby
# find and delete all users named David
User.where(name: 'David').destroy_all
 
# delete all users
User.destroy_all
```

## Migrations

ActiveRecord migrations are database-agnostic: they will run in MySQL, PostgreSQL, Oracle and others. 
Rails keeps track of which files have been committed to the database and provides rollback features. 

`rails db:migrate` creates, and `rails db:rollback` rolls back the changes.
