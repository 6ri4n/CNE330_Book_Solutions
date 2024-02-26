# CNE330_Book_Solutions

Table of Contents

####[List]()
[Slicing]()
[Traversal]()

####[Files]()
[Reading]()
[Writing]()

####[Dictionaries]()
[Accessing]()
[Creating]()

## Lists

#### Slicing

**Feedback on task descriptions**:

- not clear on length of the list of ip addresses, is it fixed at a length of 4? (I assume it's fixed)
- could be simpler / clearer
  > Remember that the first index is the starting point for the slice and the second number is one index past the end of the slice (up to but not including that element).
  - could rephrase to something like "The first index is inclusive and the second index is exclusive."

**Solutions**:

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) >= 3:
        return ip_address_list[1:3]

    return []
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) < 3:
        return []

    return ip_address_list[1:3]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) < 3:
        return []

    return ip_address_list[1:-1]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) >= 3:
        return ip_address_list[1:-1]

    return []
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) >= 3:
        return ip_address_list[-len(ip_address_list) + 1:-1]

    return []
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) < 3:
        return []

    return ip_address_list[-len(ip_address_list) + 1:-1]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) < 3:
        return []

    return ip_address_list[-len(ip_address_list) + 1:len(ip_address_list) - 1]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    if len(ip_address_list) >= 3:
        return ip_address_list[-len(ip_address_list) + 1:len(ip_address_list) - 1]

    return []
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

N / A

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    does not use the slice operator
    """
    if len(ip_address_list) >= 3:
        return [ip_address_list[1], ip_address_list[2]]

    return []
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    does not use the slice operator
    """
    if len(ip_address_list) < 3:
        return []

    return [ip_address_list[1], ip_address_list[2]]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    second argument could be any index as long as its a value of 3 or higher
    which does not solve the problem as the problem only wants to return a list
    that has 2 element but it's possible to return a list with more than 2 elements
    """
    if len(ip_address_list) < 3:
        return []

    return ip_address_list[-len(ip_address_list) + 1:]
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    second argument could be any index as long as its a value of 3 or higher
    which does not solve the problem as the problem only wants to return a list
    that has 2 element but it's possible to return a list with more than 2 elements
    """
    if len(ip_address_list) >= 3:
        return ip_address_list[-len(ip_address_list) + 1:]

    return []
```

```python
def slice_ips(ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    comparison operator could be <= 3 but this does not solve the problem
    of wanting to return [] when the list has less than 3 entries
    with <= 3 it returns [] even though the list has 3 entries which is not less than 3 entries
    """
    if len(ip_address_list) <= 3:
        return []

    return ip_address_list[1:3]
```

#### Traversal

## Files

#### Reading

#### Writing

## Dictionaries

#### Accessing

#### Creating
