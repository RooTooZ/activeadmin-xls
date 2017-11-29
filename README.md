# Active Admin Xls: Excel Spreadsheet Export for Active Admin

**Git**: [http://github.com/thambley/activeadmin-xls](http://github.com/thambley/activeadmin-xls)

**Author**:  Todd Hambley

**Copyright**:    2014 ~ 2017

**License**: MIT License

**Latest Version**: 1.0.4

**Release Date**: 2017.11.22

## Synopsis

This gem provides xls downloads for Active Admin resources.

This gem borrows heavily from [https://github.com/randym/activeadmin-axlsx](https://github.com/randym/activeadmin-axlsx) and [https://github.com/splendeo/to_xls](https://github.com/splendeo/to_xls).

Usage example:

Add the following to your Gemfile and you are good to go.
All resource index views will now include a link for download directly
to xls.

```ruby
gem 'activeadmin-xls'
```

## Cool Toys

Here are a few quick examples of things you can easily tweak.

<<<<<<< HEAD
### Localize column headers
=======
## localize column headers
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

```ruby
# app/admin/posts.rb
ActiveAdmin.register Post do
  config.xls_builder.i18n_scope = [:active_record, :models, :posts]
end
```

<<<<<<< HEAD
### Use blocks for adding computed fields
=======
## Use blocks for adding computed fields
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

```ruby
# app/admin/posts.rb
ActiveAdmin.register Post do
  config.xls_builder.column('author_name') do |resource|
    resource.author.name
  end
end
```

<<<<<<< HEAD
### Change the column header format
=======
## Change the column header format
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

```ruby
# app/admin/posts.rb
ActiveAdmin.register Post do
  config.xls_builder.header_format = { weight: :bold,
                                       color: :blue }
end
```

<<<<<<< HEAD
### Remove columns
=======
## Remove columns
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

```ruby
# app/admin/posts.rb
ActiveAdmin.register Post do
  config.xls_builder.delete_columns :id, :created_at, :updated_at
end
```

<<<<<<< HEAD
## Using the DSL
=======
# Using the DSL
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

Everything that you do with the config's default builder can be done via
the resource DSL.

Below is an example of the DSL

```ruby
ActiveAdmin.register Post do

  # i18n_scope and header style are set via options
  xls(i18n_scope: [:active_admin, :xls, :post],
      header_format: { weight: :bold, color: :blue }) do

    # Specify that you want to white list column output.
    # whitelist

    # Do not serialize the header, only output data.
    # skip_header

    # deleting columns from the report
    delete_columns :id, :created_at, :updated_at

    # adding a column to the report
    column(:author) { |post| "#{post.author.first_name} #{post.author.last_name}" }

    # inserting additional data with after_filter
    after_filter do |sheet|
      # todo
    end

    # inserting data with before_filter
    before_filter do |sheet|
      # todo
    end
  end
end
```

<<<<<<< HEAD
## Specs

=======
# Specs
------
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00
Running specs for this gem requires that you construct a rails application.
To execute the specs, navigate to the gem directory,
run bundle install and run these to rake tasks:

```text
bundle exec rake setup
```

```text
bundle exec rake
```

<<<<<<< HEAD
## Copyright and License
=======
# Copyright and License
----------
>>>>>>> 8440c797967129e42a4e21909269ae272eaf3b00

activeadmin-xls &copy; 2014 by [Todd Hambley](mailto:thambley@travelleaders.com).

activeadmin-xls is licensed under the MIT license. Please see the LICENSE document for more information.
