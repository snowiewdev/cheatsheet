REST
- multiple url endpoints for different data
- may use frontend to filter out unnecessary information

GraphQL
- query language between frontend & backend using GraphQL API
- single url endpoint (/graphql) into the API
- return fields that are requested only
- more complexity in building graphQL server

Schema
- Query type: fetching / reading data
- Mutation type: creating / updating / deleting data

Types in graphQL
- String
- Boolean
- Int
- ! -> required
- Custom type

```
type User {
  firstName: String!
  lastName: String!
  email: String!
  age: Int!
  job: Job!
}

type Query {
  getAllUsers: [User]!
  getUser(id: ID!)
}

type Mutation {
  createUser (input: CreateUserInput): User
  updateUser (input: UpdateUserInput): User
  deleteUser (input: DeleteUserInput): User
}

input CreateUserInput {
  firstName: String!
  lastName: String!
  email: String!
  age: Int!
  job: Job!
}
```


