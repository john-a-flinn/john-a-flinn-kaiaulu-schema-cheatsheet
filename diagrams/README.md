## Module Analysis

The steps are as follows:

1. **Analyze the Notebook:** Run the notebook and understand its functionality.
2. **Verify Tables:** Grab all tables that contain a different set of columns. You can ignore functions that only change the rows.
3. **Extract Tables:** Import the tables columns and one row into a spreadsheet and remove any Personal Identifiable Information (PII), such as email addresses and first/last names.
4. **Issue Creation:** Use the format in **Example Issue** 1 - 2 and the Task List.
5. **Add "Explicit Merge Functions":** These are columns that are affected by a `merge` function directly within the notebook (**Example Issue** 3).
6. **Add "Implicit Merge Functions":** These are columns affected by a `merge` function in a file other than the notebook (generally `.R` files). Search for all instances of `merge` in the codebase to understand if the application of the merge is utilized in the module (**Example Issue** 4).
7. **Add "Implicit Inner Joins":** These are joins not explicitly mentioned in any code file. An example is `file_pathname`, which is an inner join to the local path where the repository was downloaded (**Example Issue** 5).

---

## MySQL Workbench

1. **Create a New Layer:** Create a new layer for the module in the EER diagram.
   * *Note:* The layer color should have low saturation and avoid bright tones.
2. **Create a Table:** Next, create your table. 

   **Table names must follow this format:**
   * Standard format: 
     `[table name in notebook]`
   * If the table name is reused, append the module name: 
     `[table name in notebook]_[module]`
   * If both the table name and module are identical to an existing one, append the specific use case or function change: 
     `[table name in notebook]_[module]_[use case]`

   **Columns data type should be the same type as the spreadsheet example** (Example Issue 1.1)

3. **Add Merges:** * Keys must be in `ALL_CAPS`.
   * The first instance of a column is the Primary Key (PK).
   * The table being created from a PK contains the Foreign Keys (FKs). *Note: FKs can reference other FKs.*

## Example Issue

### As-is
* `[Insert image of the current table structure]`

---

### 1 Notebook 1: [Name of the Notebook]
* Overview of what the notebook does and its purpose.

#### 1.1 First Table: [Actual or agreed name with sponsor]
* Description of the table
* `[Permalink to the table in the notebook]`
* `[Spreadsheet of the table's columns and 1 row value]`
* `[Image of the table in My SQL workbench]`

#### 1.2 Second Table: [Name of the Table]
* *(Repeat the steps from 1.1 for each table in the notebook)*

---

### 2 Notebook 2: [Name of the Notebook]
* *(Sometimes issues contain multiple notebooks. Duplicate Notebook 1's steps until all notebooks are covered)*

---

### 3. Explicit Merge Functions

#### 3.1 [Name of the affected column(s)]
* Description of the merge in the notebook
* `[Permalink to the code]`
* `[Spreadsheet of the table's columns and 1 row value]`
* `[Image of the table in My SQL workbench]`

#### 3.2 [Next affected column]
* *(Loop until all Explicit Merge Functions are covered)*

---

### 4. Implicit Merge Functions

#### 4.1 [Name of the affected column(s)]
* Description of the merge in the file
* `[Permalink to the code]`
* `[Image of the table in My SQL workbench]`

#### 4.2 [Next affected column]
* *(Loop until all Implicit Merge Functions are covered)*

---

### 5. Implicit Inner Joins

#### 5.1 [Name of the affected column(s)]
* Reasoning for the inner join
* `[Image of the table in My SQL workbench]`

#### 5.2 [Next affected column]
* *(Loop until all Implicit Inner Joins are covered)*

---

### Task List
- [x] Notebook 1
- [x] External notebooks (if any exist)