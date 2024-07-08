# Pydantic Data Transformation Services

### [Repo]()

### [YouTube Video]()

Under construction 🏗️

*DESERIALIZATION === input string/dict/JSON data into Pydantic Python Models*

*SERIALIZATION === output data from Pydantic Python Model to string/dict/JSON data*

## LIFECYCLE

### Before

If we are importing in JSON for example, we can create aliases so that we can map firstName to first_name for example. We can also set rules for how Pydantic should handle extra fields.

We can also apply validation and data transformation prior to Pydantic carry out its own validataion, transformation and insertion.

### After

Afte Pydantic has run thorugh its own process, we can apply after validators/transformations prior to being inserted into the class.

### Serialization

When serialising, ('exporting'), we can set up rules for include/exclude fields depending on whether we are exporting to a Python dict or JOSN object.

## UTILITIES

### Import a REST API

A range of examples for clean and unclean data.

### Loading CSV files

As with APIs we have a set of examples depending on the cleanliness of the data.

### Import/Export to/from DB

We will use SQLite as our DB.

<br>