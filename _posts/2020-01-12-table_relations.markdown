---
layout: post
title:      "Table Relations"
date:       2020-01-13 04:52:12 +0000
permalink:  table_relations
---


As I write this I am working on a project which involves tracking users and their posts. While I have been aware of technologies like SQL for some time, and have persisted data within text files for past projects, I have only recently grasped how table relations work and how to implement them in Ruby.

At the moment, I have only created the users table and plan to have everything related to the users table (aside from posts) working before I begin implementing the posts table. For my project posts will include a code snippet and a description. The migration for posts will be as follows...

```
class CreatePosts < ActiveRecord::Migration
    def change
		    create_table :posts do |t|
				    t.string :code_snippet
						t.string :description
						t.integer :user_id
				end
		end
end
```

within the User class will be...

```
has_many :posts
```

and within the Post class...

```
belongs_to :user
```

I believe that this solution, although simple, will be everything I need to reach my goals. In the near future I may attempt to build a 'favorites' feature so that users are able to store their favorite posts created by other users. This will involve creating another table named favorties. A favorite will have a ```:post_id``` and a user will have many favorites.

I am still learning about how these relationships work and look forward to building more complex relationships in future projects.
