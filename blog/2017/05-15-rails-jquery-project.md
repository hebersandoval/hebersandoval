---
layout: blog/blog_layout.html
pageTitle: "Rails JQuery Project"
title:  "Rails JQuery Project"
backgroundImage: '/assets/img/blog/beach-birds.jpg'
date:   2017-05-15
categories: Rails
tags: ['post']
---

<!-- Excerpt Start -->
In a RESTful world, it's ok to only relay on calls to the server to server your resources and causing a total page reload. But using JavaScript can save you fetching data that you already have to display. How can creating a simple API application help here?
<!-- Excerpt End -->

## Brief Overview of Rails JQuery Project - Portfolio/Blog

A brief description of the project here.

May want to show code:

```ruby
class Ingredient < ActiveRecord::Base
  belongs_to :recipe
end
```

Example of tables

ingredients_table

```bash
id |     name   | recipe_id |
---+------------+-----------+
1  |  Tomatoes  |      1    |
2  |  Garlic    |      1    |
```

recipes_table

```bash
id |   name   |
---+----------+
1  |  Lasagna |
```

Tables with associations

ingredients_table

```bash
id |     name   | recipe_id |
---+------------+-----------+
1  |  Tomatoes  |   1, [2]  |
```

recipes_table

```bash
id |    name    |
---+------------+
1  |  Lasagna   |
2  |  Pot Pie   |
```

After modification on tables.

Here is how the tables looks now:

ingredients_table

```bash
id |     name   |
---+------------+
1  |  Tomatoes  |
```

pantries_table

```bash
id | recipe_id | ingredient_id |
---+------------+--------------+
1  |     1      |     1        |
2  |     2      |     1        |
```

recipes_table

```bash
id |     name   |
---+------------+
1  |  Lasagna   |
2  |  Pot Pie   |
```

A description here.

### Putting This Understanding Into Practice

Put some content here.

### Recipe Model

```ruby
class Recipe < ActiveRecord::Base
  has_many :pantries
  has_many :ingredients, through: :pantries
end
```

Lets test this model out.

#### Creating a recipe:

```bash
$ recipe = Recipe.create name: "Lasagna"

(0.1ms)  SAVEPOINT active_record_1
SQL (0.5ms)  INSERT INTO "recipes" ("name", "created_at", "updated_at") VALUES (?, ?, ?)  [["name", "Lasagna"], ["created_at", "2016-09-12 02:36:47.743490"], ["updated_at", "2016-09-12 02:36:47.743490"]]
(0.1ms)  RELEASE SAVEPOINT active_record_1

=> #<Recipe id: 1, name: "Lasagna", created_at: "2016-09-12 02:36:47", updated_at: "2016-09-12 02:36:47">
```

More content here if you need it...