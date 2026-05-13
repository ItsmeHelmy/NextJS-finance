# Custom Skills

## Available Skills

### `/db-schema`
**Description:** View and understand the current database schema

**Usage:** `/db-schema`

**What it does:**
- Reads the Prisma schema or database migration files
- Displays current tables, relationships, and fields
- Shows indexes and constraints

**Example output:**
```
Tables:
- User (id, email, name, created_at)
- Account (id, user_id, name, balance, type)
- Transaction (id, account_id, amount, category, date)

Relationships:
- User → Account (1:N)
- Account → Transaction (1:N)
```

---

### `/component-create`
**Description:** Create a new React component with Tailwind styling

**Usage:** `/component-create <ComponentName> <type>`

**Parameters:**
- `ComponentName` - Name of the component (PascalCase)
- `type` - "client" or "server" (default: server)

**What it does:**
- Creates a new component file in the appropriate directory
- Sets up proper TypeScript types
- Adds Tailwind CSS classes placeholder
- Follows project naming conventions

**Example:**
```
/component-create TransactionForm client
```
Creates: `components/features/TransactionForm.tsx`

---

### `/api-route`
**Description:** Create a new API route with proper typing and error handling

**Usage:** `/api-route <route-name> <method>`

**Parameters:**
- `route-name` - The API route path
- `method` - HTTP method (GET, POST, PUT, DELETE)

**What it does:**
- Creates a new Route Handler in `app/api/`
- Sets up TypeScript types for request/response
- Adds error handling and validation
- Includes status codes and proper responses

**Example:**
```
/api-route transactions POST
```
Creates: `app/api/transactions/route.ts`

---

### `/db-query`
**Description:** Execute a safe database query and show results

**Usage:** `/db-query <table> <operation> [filters]`

**Parameters:**
- `table` - Database table name
- `operation` - find, findFirst, create, update, delete
- `filters` - Optional WHERE clause conditions

**What it does:**
- Generates type-safe Prisma/ORM query
- Shows the query that will be executed
- Executes and displays results (with row limit)
- Warns about destructive operations

**Example:**
```
/db-query Transaction find "where: { userId: 1 }"
```

---

### `/test-create`
**Description:** Create test files for components or API routes

**Usage:** `/test-create <target> <type>`

**Parameters:**
- `target` - Component or API route name
- `type` - "unit" or "integration"

**What it does:**
- Creates test file alongside target
- Sets up test framework (Jest/Vitest)
- Adds basic test cases
- Includes mocking setup if needed

**Example:**
```
/test-create TransactionForm unit
```
Creates: `components/features/TransactionForm.test.tsx`

---

### `/finance-validate`
**Description:** Validate financial data and calculations

**Usage:** `/finance-validate <data> <type>`

**Parameters:**
- `data` - JSON data or reference to variable
- `type` - "transaction", "account", "calculation"

**What it does:**
- Checks for decimal precision issues
- Validates amount ranges
- Checks for proper rounding
- Warns about float usage
- Suggests proper decimal handling

**Example:**
```
/finance-validate "{ amount: 100.50 }" transaction
```

---

### `/page-create`
**Description:** Create a new Next.js page with proper structure

**Usage:** `/page-create <path> <type>`

**Parameters:**
- `path` - URL path for the page
- `type` - "public" or "protected" (requires auth)

**What it does:**
- Creates page.tsx in appropriate app/ directory
- Sets up Server Component by default
- Adds layout if needed
- Includes metadata and SEO basics
- For protected pages, adds auth check placeholder

**Example:**
```
/page-create dashboard/overview protected
```
Creates: `app/dashboard/overview/page.tsx`

---

## How Skills Work

Skills are custom commands that I can execute to perform common tasks in this project. They encapsulate best practices and project-specific patterns.

To use a skill, simply type `/skill-name` in your message, followed by any required parameters.

Skills help maintain consistency and speed up development by automating repetitive tasks while following the project's established patterns.
