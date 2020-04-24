# Astronomer Code Challenges

This challenge tests full-stack abilities of a GraphQL server and client-rendering
of API returned data.

### 1st Challenge - Create User Functions in GraphQL:

1. Add support for creating a user:
```
mutation createUser($email: String!, $password: String!) {
  createUser(email: $email, password: $password) {
    user {
      id
      email
    }
  }
}
```

2. Add support for returning all users in the database:
```
query users {
  users {
    id
    email
  }
}
```

### 2nd Challenge - Connect to server and list users:

1. Connect to the `graphql-server`.
```
import ApolloClient from 'apollo-boost';

const client = new ApolloClient({
  uri: 'http://localhost:4000',
});
```

2. Query all users.
```
query users {
  users {
    id
    email
  }
}
```

3. List users in the client.
```
{users.map(user =>
  <span key={user.id}>{user.email}</span>
)}
```
