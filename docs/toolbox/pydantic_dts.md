# Pydantic Data Transformation Services

Utilities that carry out data transformation services - JOSN to CSV to Pydantice Classes to Export etc.

Under construction 🏗️

## Classes

We will have the following classes:

- User
- Product
- Category

## Data sources

- API (or JSON stub)
- CSV
- DB

## Data Transformation Services

- Before Validation
- After Validation
- Aliasing
- Type Conversion
- Handling Date/Time

## Example DTS

1. From an API, handle JS type field names, firstName, and convert to Python field name, first_name, and also exporting out to JS field names.

2. Read data in from a CSV, validate, clean and then load into a DB.

3. Extract data from a DB/CSV and export to JSON.