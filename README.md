# rest-api-naming-convention-and-best-practices
Guide for writing proper REST API endpoints using proper naming conventions and best practices

# Use plurals for resource collections
```
/users ✅
/user ❎
```

# Specify the resource to access sub collection
```
/users/{id}/transactions
```

# URI must be noun and avoid using verbs
 - Because using verbs in URI adds verbosity and should be represented via HTTP methods
```
/users/{id} ✅ // means get a specific resource in the collection of user
/users/getById/{id} ❎
```

# Use HTTP method semantics
  ##### POST: Create a resource
  ##### GET: Retrieve a resource
  ##### PUT: Update the whole resource
  ##### PATCH: Update a specific data in resource
  ##### DELETE: Delete a resource
```
POST /users with request body
GET /users
GET /users/{id}
PUT /users/{id} with request body
PATCH /users/{id} with request params
DELETE /users/{id}
```

# Do not use trailing forward slashes
 - Because every forward slash there should be something that you can do and using forward slash that do nothing is just nonsense
```
/users ✅
/users/ ❎
```

# Use kebab case
 - To increase readability and scalability
```
/users/{id}/accounts/device-management ✅ // easy to read
/users/{id}/accounts/deviceManagement ❎ // hard to read
```