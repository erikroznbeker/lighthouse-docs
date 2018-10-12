---
id: relay
title: Relay
---

## Cursor Connection

Relay requires a particular kind of pagination which is the [Cursor Connection](https://facebook.github.io/relay/graphql/connections.htm)
To get a relay-compatible connection on a root query field, use the [@paginate](directives#paginate)
directive with the pagination type `connection`.

```graphql
type Query {
    users: [User] @paginate(type: "connection")
}
```

This automatically converts the type definition into a relay connection and constructs
the appropriate queries via the underlying Eloquent model.
Connections can also be used for sub-fields of a type, given they are defined as a HasMany-Relationship
in Eloquent. Use the [@hasMany](directives#hasMany) directive.

```graphql
type User {
    name: String
    posts: [Post] @hasMany(type: "connection")
}
```

## Global Object Identification

// TODO write out this section, accepting PR's

[Global Object Identification](https://facebook.github.io/relay/graphql/objectidentification.htm)

[@model](directives#model)

[@globalId](directives#globalid)

## Mutations

// TODO write something about how Mutations must always take InputObjects and how flattening helps achieve that.
