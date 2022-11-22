## Write some unit tests
We already have a couple of test cases in `test/test_models.py` that test the `daily_mean()` function. Looking at `inflammation/models.py`, write at least two new test cases that test the `daily_max()` and `daily_min()` functions, adding them to `test/test_models.py`. Here are some hints:

You could choose to format your functions very similarly to `daily_mean()`, defining test input and expected result arrays followed by the equality assertion.
Try to choose cases that are suitably different, and remember that these functions take a 2D array and return a 1D array with each element the result of analysing each column of the data.
Once added, run all the tests again with `pytest tests/test_models.py`, and you should also see your new tests pass.

<details>
<summary>Solution</summary>

```
def test_daily_max():
    """Test that max function works for an array of positive integers."""
    from inflammation.models import daily_max

    test_input = np.array([[4, 2, 5],
                           [1, 6, 2],
                           [4, 1, 9]])
    test_result = np.array([4, 6, 9])

    npt.assert_array_equal(daily_max(test_input), test_result)


def test_daily_min():
    """Test that min function works for an array of positive and negative integers."""
    from inflammation.models import daily_min

    test_input = np.array([[ 4, -2, 5],
                           [ 1, -6, 2],
                           [-4, -1, 9]])
    test_result = np.array([-4, -6, 2])

    npt.assert_array_equal(daily_min(test_input), test_result)
```

</details>

<br>
<br>
<br>
<br>

## Write parameterised unit tests
Rewrite your test functions for daily_max() and daily_min() to be parameterised, adding in new test cases for each of them.

