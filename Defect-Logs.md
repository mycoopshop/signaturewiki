Irrelevant condition - I was checking for something that should have been skipped altogether

Constant unset - I was checking for a constant value which was never set

Missed parentheses - I did not lint the code

Public function was not local - I added a function to an object within a function instead of simple nesting

Cached value was wrong - I cached a dynamic value in a variable instead of wrapping it in a function call

**References**

* https://siderite.blogspot.com/2017/02/caching-as-antipattern.html
* https://news.ycombinator.com/item?id=3233526
* https://www.reddit.com/r/reactjs/comments/3bjdoe/state_is_an_antipattern/