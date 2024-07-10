# Pydantic Data Transformation Services

### [Repo]()

### [YouTube Video]()

Under construction 🏗️

*DESERIALIZATION === input string/dict/JSON data into Pydantic Python Models*

*SERIALIZATION === output data from Pydantic Python Model to string/dict/JSON data*

## Lifecycles

### Before

If we are importing in JSON for example, we can create aliases so that we can map firstName to first_name for example. We can also set rules for how Pydantic should handle extra fields.

We can also apply validation and data transformation prior to Pydantic carry out its own validataion, transformation and insertion.

### Pydantic validation

Our Pydantic model will validate data and return a list of errors that fail validation.

Pydantic does not stop on the first failed validation but continues on until all fields have been validated and it will then report a list of all validation errors.

### After

After Pydantic has run thorugh its own process, we can apply after validators/transformations prior to being inserted into the class.

### Serialization

When serialising, ('exporting'), we can set up rules for include/exclude fields depending on whether we are exporting to a Python dict or JOSN object.

## Ingesting a REST API

This is `01_users.py`

Using `https://dummyjson.com/users/3` we get a dictionary from our requests library.

In this first template, we only want id, first_name, last_name, age and email.

We want to map our `user_id` in our Pydantic model to the REST `id` so we use our ConfigDict model alias for all the fields except this one, which uses a field level alias to map `user_id` to `id`,

<br>