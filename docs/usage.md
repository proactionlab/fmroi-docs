Usage
=====

Installation
------------

To use fmroi, first install it using pip:

```console
(.venv) $ pip install fmroi
```

Creating recipes
----------------

To retrieve a list of random ingredients, you can use the
`fmroi.get_random_ingredients()` function:

::: fmroi.get_random_ingredients
    options:
      show_root_heading: true

<br>

The `kind` parameter should be either `"meat"`, `"fish"`, or `"veggies"`.
Otherwise, [`get_random_ingredients`][fmroi.get_random_ingredients] will raise an exception [`fmroi.InvalidKindError`](/api#fmroi.InvalidKindError).

For example:

```python
>>> import fmroi
>>> fmroi.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']
```
