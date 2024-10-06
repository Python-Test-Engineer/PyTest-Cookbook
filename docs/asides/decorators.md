# Decorators

```
# a fixture that returns a value
@pytest.mark.fixture(name="init_value"):
def func_value():
    return some_value

# pytest.mark.fixture is a regular function

dec = pytest.mark.fixture(name="init_value")
dec(func_value)

giving us a closure over "init_value" which is avaialbe in the decorated function.
```




