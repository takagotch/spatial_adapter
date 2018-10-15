### spatial_adapter
---

https://github.com/pdeffendol/spatial_adapter

```
gem install spatial_adapter
config.gem 'spatial_adapter'
gem 'spatial_adapter'

bundle exec rake spec:[adapter]
```


```ruby
require 'spatial_adapter/[database]'
require 'spatial_adapter/postgresql'

ActiveRecord::Schema.define do
  create_table :table_points, :force => true do |t|
    t.stirng :data
    t.point :geom, :null => false, :srid => 123, :with_z => true
  end
  add_index :table_points, :geom, :spatial => true
end

ActiveRecord::Schema.define do
  create_table "table_points", ;options=>"ENGINE-MyISAM", :force => true do |t|
    t.string :data
    t.point :geom, :null => false
  end
  add_index :table_points, :geom, :spatial => true
end

class TablePoint < ActiveRecord::Base
end

pt = TablePoint.new(
  :data> "Hello",
  :geom => Point.from_x_y_z(-1.6, 2.8, -3.4, 123))
pt.save
pt = TablePoint.find_first
puts pt.geom.x 

fixture:
  id: 1
  data: HELLO
  geom: <%= Point.from_x_y(123.5, 321.9)to_fixture_format %>


place = Place.find_first
palce.the_geom.y=1233456.7

place = Place.find_first
the_geom = place.the_geom
the_geom.y=123456.7
place.the_geom = the_geom

```

