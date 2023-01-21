## Getting started

### 1. Install dependencies

Install npm dependencies:

```
npm install
```

### 2. Start the REST API server

```
npm run dev
```

The server is now running on `http://localhost:3000`. 

## Using the REST API

You can access the REST API of the server using the following endpoints:

## Evolving the app

Evolving the application typically requires two steps:

1. Migrate your database using Prisma Migrate
1. Update your application code

For the following example scenario, assume you want to add a "profile" feature to the app where users can create a profile and write a short bio about themselves.

### 1. Migrate your database using Prisma Migrate

Once you've updated your data model, you can execute the changes against your database with the following command:

```
npx prisma migrate dev 
```

This adds another migration to the `prisma/migrations` directory and creates the new table in the database.

### 2. Update your application code

You can now use your `PrismaClient` instance to perform operations against the new `Profile` table. Those operations can be used to implement API endpoints in the REST API.

#### 2.1 Add the API endpoint to your app

Update your `index.ts` file by adding a new endpoint to your API:

## Switch to another database (e.g. PostgreSQL, MySQL, SQL Server, MongoDB)

If you want to try this with another database than SQLite, you can adjust the the database connection in [`prisma/schema.prisma`](./prisma/schema.prisma) by reconfiguring the `datasource` block. 
