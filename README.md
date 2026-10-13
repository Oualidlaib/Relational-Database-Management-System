# Implementation of an RDBMS

## Description
This project implements a functional Relational Database Management System (RDBMS). It handles the full lifecycle of a SQL query—from lexical analysis and parsing into an **Abstract Syntax Tree (AST)** to final semantic evaluation and execution.

## Features
- **Supported Queries**: `INSERT` and `SELECT`.
- **Clause Support**: The `FROM` clause accepts exactly one relation (**JOINS are not currently supported**).
- **Syntax**: All queries must terminate with a semicolon (`;`).
- **Supported Datatypes**:
  - `CHAR(n)` and `VARCHAR(n)`
  - `INT`
  - `FLOAT`

## Technical Architecture
The engine utilizes a classic compiler-design pipeline:
1. **Lexical Analysis**: Tokenizes the raw SQL string using a Pythonic implementation of **Lex**.
2. **Parsing**: Generates an AST using a Pythonic implementation of **Yacc**.
3. **Semantic Analysis**: Validates the query against the schema (type checking and relation existence).
4. **Evaluation**: Executes the logic against the stored data.

---

## Setup & Requirements

### Prerequisites
Create a virtual environment (recommended best practice).

This project requires **PLY (Python Lex-Yacc)** to handle grammar and parsing:

```bash
pip install ply
```
### Compatibility
* **Tested on**: Python 3.11
* **Note**: Compatibility with other versions is not guaranteed.

---

## 🚀 Usage Guide
To get the program up and running with the default schema and provided mock data, follow these steps:

1. **Populate the Relations**:
   Run the following scripts to fill the `Mathematics` and `Employee` relations with mock data:
   ```bash
   python3 fill_Mathematics_relation.py
   python3 fill_Employee_relation.py
   ```
2. **Launch the DBMS**:
   Start the main interface by running:
   ```bash
   python3 ./main.py
   ```
3. **Running Queries**:
   Once the program is running, you can enter your SQL queries directly into the prompt.
   
   **Example:**
   ```sql
   SELECT * FROM Employee;
   INSERT INTO Mathematics VALUES (1, 'Logic', 'Kurt Godel', 69.9);
   ```
