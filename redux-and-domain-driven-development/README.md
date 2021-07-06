# Redux and DDD

- https://levelup.gitconnected.com/redux-and-doman-driven-development-29f818f60f2f

- Author is comparing DDD w/ redux

## DDD tools

- **Queries**
    - Asking a question in the system
    `listPosts(): post[] {...}`
- **Commands**
    - Request for mutation
        - May work may fail
    - `AddPost(Title title, Body, body): void {...}`
- **Domain Events**
    - Represent the *effect* of a *cause*
    - They are facts, something that has happened
    - Do not fail
    - `PostAdded(postId, title, body): void {...}`
- **Aggregates**
    - Represents small pieces of models
        - ideally just one entity and a few value objects
    - Aggregates communicate w/ eah other through queries, commands, and domain events
    - Consume domain events to keep their state consistent
    - Generate new domain events for each mutation
    - `Post(postId, title, body) {...}`

## Redux

- **Queries**
    - Use selectors
- **Commands**
    - These are actions
- **Events**
    - actions after they have gone through reducer
- **Aggregate**
    - Reducer
