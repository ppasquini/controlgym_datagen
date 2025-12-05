To modify the initial coditions go to:
``` 
controlgym\envs\name_of_the_enviroment.py
```
And modify the function:
```python
    def select_init_state(self, init_amplitude=None, init_spread=None):
```

For burgers, one shock scenario:
```python
init_state = init_amplitude * np.cosh(
        1 / init_spread * (self.domain_coordinates - 0.5 * self.domain_length)
    ) ** (-1) 
```
or, for two shocks:
```python
init_state = init_amplitude * np.cosh(
            1 / init_spread * (env.domain_coordinates - 0.3)
        ) ** (-1) + np.cosh(
            1 / init_spread * (env.domain_coordinates - 0.7)
        ) ** (-1)
```
