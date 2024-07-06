# Pydantic Data Transformation Services

### [Repo]()

### [YouTube Video]()

Under construction 🏗️

*DESERIALIZATION === input string/dict/JSON data into Pydantic Python Models*

*SERIALIZATION === output data from Pydantic Python Model to string/dict/JSON data*

## INPUT

- We can register aliases for input e.g. firstName, FirstName to go into first_name.
- We can clean/limit acceptable inputs before deserialization is complete.
- We can validate data after data has entered model.
  
## CLASS

- We can define types for each field, Nullability and whether it is required or optional.
- We can use Pydantic field definitions on what will be valid data.
- Define aliases for deserialization and serialization.
- We can use Custom Validator functions.

## OUTPUT

- We can specify which fields to include/exclude when outputing to dict of JSON.
- We can specify which alias to use e.g. first_name, FirstName or firstName etc.
  
As you can see, there are many operations we can perform and many ways to do them.

The repo has templates for the most common uses with Rich and PyBoxen for presentation of these examples.

## UTILITIES

### Import a REST API

A range of examples for clean and unclean data.

### Loading CSV files

As with APIs we have a set of examples depending on the cleanliness of the data.

### Import/Export to/from DB

We will use SQLite as our DB.

<br>