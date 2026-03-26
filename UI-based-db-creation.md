# Step-by-step, UI-based guide** to create **PostgreSQL database and all tables using pgAdmin**


---

##  Prerequisites

Before starting, make sure you have:

* PostgreSQL installed and running
* pgAdmin 4 installed
* Your PostgreSQL server credentials:

  * Username (e.g. `postgres`)
  * Password

---

## Step 1: Open pgAdmin & Connect Server

1. Open **pgAdmin**
2. Enter your master password (if prompted)
3. In the left sidebar:

   * Expand **Servers**
   * Click your PostgreSQL server

---

## Step 2: Create New Database

### 2.1 Navigate:

* Right click:

  ```
  Databases → Create → Database
  ```

### 2.2 Fill Details:

| Field         | Value      |
| ------------- | ---------- |
| Database Name | `your_db_name`   |
| Owner         | `postgres` |

Click **Save**

---

## Step 3: Open Query Tool

1. Select your new DB:

   ```
   your_db_name
   ```
2. Click:

   ```
   Tools → Query Tool
   ```

This is where we will run all SQL

---

## Step 4: Create All Tables (Run This Script)

Write the Tables creation Query into the Query Tool
Then click  **Execute**

---

## Step 5: Verify Tables

In pgAdmin:

```
your_db_name → Schemas → public → Tables
```

You should see (Your created tables):

* abc
* def
* igk
* lmn
* opq
* etc.

---

