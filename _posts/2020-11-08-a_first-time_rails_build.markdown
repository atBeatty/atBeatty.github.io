---
layout: post
title:      "A First-Time Rails Build"
date:       2020-11-08 23:08:45 +0000
permalink:  a_first-time_rails_build
---


This project was exciting for me and most of our cohort. It was our first attempt at building our own Rails App that carried a legitimate Many-to-many relationship. I started off with an idea that carried forward from my Sinatra project. I gathered my data and organized it into tables aptly named USERS, PLANTS, and GARDENS. I took this project concept nearly to the end until I had started over with three days left.

I could not get my head around the aforementioned classes and their respected associations. Now, Rails is an app framework that allows for flexibility. In no way was my first project one that was flawed and impossible to build. However, I had several conversations with myself around the UX stories and attempted to relate it back to the databse model.

**The key challenge is mapping your own definitions of how the DATABASE MODEL works when compared to how the REAL WORLD MODEL works. **

My issue (again, not a Rails issue) was that I did not feel comfortable with how my users related to the model. 

```
belongs_to :user
    belongs_to :garden, optional: true
end

class User < ApplicationRecord
   has_many :plants
   has_many :gardens, through: :plants
end

class Garden < ApplicationRecord
    has_many :plants
    has_many :users, through: :plants
    # accepts_nested_attributes_for :plants
end
```

With this in place, I ran into errors and found myself coding into a corner. One of the biggest flaws was that it was deleting multiple associated database entries when I built out the delete functionality. I actually learned quite a bit on the dynamics of how some of the Rails relationships work. 

I ended up starting over because I needed to come up with a stronger model/domain. Plants and Gardens were all too similar and it was hard to make either one the driving force of an App. 


