# RailsAdminSimpleHasMany

RailsAdminSimpleHasMany is a field type for [Rails Admin](https://github.com/sferik/rails_admin) for has_many associations that do not require a complex multiselect field. RailsAdminSimpleHasMany has been only tested with Mongoid adapter and on Chrome/Safari. I do not expect major issues with other ORMs or browsers, but bugs and enhancements pull requests are welcome!

Example of how the collection field would look like:

![RailsAdminSimpleHasMany screenshot1](https://s3.amazonaws.com/aimannajjar.com/assets/images/portfolio/rails_admin_simple_has_many_sm_orderable.png)

## Usage

Simply add the following gem to your Gemfile:
```ruby
gem "rails_admin_simple_has_many"
```
And then run `bundle` (note: `rails_admin` should already be in your Gemfile)

Next, add the field as follows in your model

```ruby
rails_admin do
    field :players, :simple_has_many do
        help 'Please add 12 players'
        orderable true
        required true
    end
end
```

Note: `orderable` enables UI controls to move items up and down but you still need to support it in your models, see [this](https://github.com/sferik/rails_admin/wiki/Orderable---Sortable-Has-Many-without-Through) for an example using `has_many` assocaition with Mongoid/MongoDB and [this](https://github.com/sferik/rails_admin/wiki/Has-many-%3Athrough-association) for an example using `has_many :through` and ActiveRecord. 


