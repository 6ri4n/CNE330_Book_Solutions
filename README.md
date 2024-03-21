# CNE330 Smoke Testing

A solution manual for RTC's Python 1 course (CNE330). Providing feedback and conducting smoke testing to improve the user experience and stability of the course materials.

Supported Python Versions: Python 3.9, Python 3.10, Python 3.11, Python 3.12

<hr>

## Table of Contents

### [Unit Testing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#unit-testing-1)

- [LinuxWindowsMac](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#linuxwindowsmac)

### [Strings](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#strings-1)

- [Comparison](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#comparison)

- [Concatenation](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#concatenation)

- [Length](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#length)

- [Slicing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#slicing)

### [List](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#lists)

- [Accessing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#accessing)

- [Cloning](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#cloning)

- [Slicing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#slicing)

- [Traversal](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#traversal)

### [Files](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#files-1)

- [Reading](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#reading)

- [Writing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#writing)

### [Dictionaries](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#dictionaries-1)

- [Accessing](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#accessing)

- [Creating](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#creating)

<hr>

## Unit Testing

### LinuxWindowsMac

**Task Description Feedback**:

- clarify that the ending_ip is exclusive
- clarify that a server could be multiple operating systems and not just limited to one

**Solutions**:

```python
# This program returns the count of IPs within a range that would be allocated to different OSes
def linux_mac_windows(starting_ip, ending_ip):
    linux = 0  # Numbers divisible by 3
    mac = 0  # Numbers divisible by 5
    windows = 0  # Numbers divisible by 3 and 5

    # TODO - Write code here, starting_ip = beginning number, ending_ip = ending number
    for num in range(starting_ip, ending_ip):
        if num % 3 == 0 and num % 5 == 0:
            windows = windows + 1
        if num % 3 == 0:
            linux = linux + 1
        if num % 5 == 0:
            mac = mac + 1

    # DO NOT EDIT BELOW THIS LINE
    return [linux, mac, windows]

assert linux_mac_windows(1, 5) == [1, 0, 0]  # 1 Linux, 0 Mac, 0 Windows
assert linux_mac_windows(1, 10) == [3, 1, 0]  # 3 Linux, 1 Mac, 0 Windows
assert linux_mac_windows(1, 15) == [4, 2, 0]  # 4 Linux, 2 Mac, 0 Windows
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```

```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

<hr>

## Strings

### Comparison

**Task Description Feedback**:

- not related to the task description but the unit test test_check_not_in_type is calling the wrong function (it's calling check_in when it should be check_not_in)

**Solutions**:

```python
def check_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet in ip_address:
        return True

    return False

def check_not_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet in ip_address:
        return False

    return True
```

```python
def check_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet not in ip_address:
        return False

    return True

def check_not_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet not in ip_address:
        return True

    return False
```

```python
def check_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet not in ip_address:
        return False

    return True

def check_not_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    return not check_in(ip_address, octet)
```

```python
def check_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    if octet in ip_address:
        return True

    return False

def check_not_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line
    return not check_in(ip_address, octet)
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def check_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line

    """
    only checks the first octet which does not solve the problem as the problem
    wants to determine if an octet is equal to any of the four octets
    """
    if octet == ip_address[:3]:
        return True

    return False

def check_not_in(ip_address, octet):
    # TODO - Write your code here. Make sure to edit the return line

    """
    only checks the first octet which does not solve the problem as the problem
    wants to determine if an octet is equal to any of the four octets
    """
    if octet == ip_address[:3]:
        return False

    return True
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Concatenation

**Task Description Feedback**:

- removing this sentence would make the problem more clearer
  > If they are the same length, return either IP address.

**Solutions**:

```python
def create_ip_address(first_octet, second_octet, third_octet, fourth_octet):
    # TODO - Write your code here. Make sure to edit the return line
    return f"{first_octet}.{second_octet}.{third_octet}.{fourth_octet}"
```

```python
def create_ip_address(first_octet, second_octet, third_octet, fourth_octet):
    # TODO - Write your code here. Make sure to edit the return line
    return str(first_octet) + "." + str(second_octet) + "." + str(third_octet) + "." + str(fourth_octet)
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def create_ip_address(first_octet, second_octet, third_octet, fourth_octet):
    # TODO - Write your code here. Make sure to edit the return line

    """
    returning any string value does not solve the problem of
    returning an ip address containing the four given octets
    """
    return "hi"
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Length

**Task Description Feedback**:

- N / A

**Solutions**:

```python
def compare_ip_length(address_a, address_b):
    # TODO - Write your code here. Make sure to edit the return line
    len_address_a = len(address_a)
    len_address_b = len(address_b)

    if len_address_a == len_address_b:
        return address_a

    if len_address_a > len_address_b:
        return address_a

    return address_b
```

```python
def compare_ip_length(address_a, address_b):
    # TODO - Write your code here. Make sure to edit the return line
    len_address_a = len(address_a)
    len_address_b = len(address_b)

    if len_address_a == len_address_b:
        return address_a
    elif len_address_a > len_address_b:
        return address_a
    else:
        return address_b
```

```python
def compare_ip_length(address_a, address_b):
    # TODO - Write your code here. Make sure to edit the return line
    if len(address_a) == len(address_b):
        return address_a
    elif len(address_a) > len(address_b):
        return address_a
    else:
        return address_b
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def compare_ip_length(address_a, address_b):
    # TODO - Write your code here. Make sure to edit the return line

    """
    checks the length of the last octet which does not solve the problem
    of comparing the length of the entire ip
    """
    last_octet_a = address_a.split(".")[3]
    last_octet_b = address_b.split(".")[3]

    if len(last_octet_a) == len(last_octet_b):
        return address_a
    elif len(last_octet_a) > len(last_octet_b):
        return address_a
    else:
        return address_b
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Slicing

**Task Description Feedback**:

- not related to the task description but the task file has a function called get_fourth_octet when it should be called get_third_octet

**Solutions**:

```python
def get_first_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    octet_indices = []

    for index in range(len(ip_address)):
        if ip_address[index] == ".":
            octet_indices.append(index)
            break

    return ip_address[:octet_indices[0]]

def get_third_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    octet_indices = []

    for index in range(len(ip_address)):
        if ip_address[index] == ".":
            octet_indices.append(index)

    return ip_address[octet_indices[1] + 1:octet_indices[2]]
```

```python
def get_first_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    first_octet_end = ip_address.index(".")
    return ip_address[:first_octet_end]

def get_third_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    octet_indices = []

    for index in range(len(ip_address)):
        if ip_address[index] == ".":
            octet_indices.append(index)

    return ip_address[octet_indices[1] + 1:octet_indices[2]]
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def get_first_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line

    """
    uses the split method which does not solve the problem using the slicing operator
    """
    return ip_address.split(".")[0]

def get_third_octet(ip_address):
    # TODO - Write your code here. Make sure to edit the return line

    """
    uses the split method which does not solve the problem using slicing the slicing operator
    """
    return ip_address.split(".")[2]
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

<hr>

## Lists

### Accessing

**Task Description Feedback**:

- might not be necessary but clarify that accessing the elements should be done using an index

**Solutions**:

```python
def access_first_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[0]

def access_second_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[1]

def access_last_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[3]
```

```python
def access_first_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[0]

def access_second_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[1]

def access_last_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[-1]
```

```python
def access_first_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[-4]

def access_second_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[-3]

def access_last_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return list[-1]
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def access_first_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line

    """
    hard coded values which does not solve the problem of accessing an element based on its index
    """
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return '127.0.0.1'

def access_second_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line

    """
    hard coded values which does not solve the problem of accessing an element based on its index
    """
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return '192.168.0.1'

def access_last_element(ip_address):
    # TODO - Write your code here. Make sure to edit the return line

    """
    hard coded values which does not solve the problem of accessing an element based on its index
    """
    list = ['127.0.0.1','192.168.0.1','10.0.0.1','192.168.1.1']
    return '192.168.1.1'
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Cloning

**Task Description Feedback**:

- N / A

**Solutions**:

```python
def create_clone(list_to_clone):
    # TODO - Create a copy of the list
    return list_to_clone[:]
```

```python
def create_clone(list_to_clone):
    # TODO - Create a copy of the list
    clone = []

    for element in list_to_clone:
        clone.append(element)

    return clone
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```

```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Slicing

**Task Description Feedback**:

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

```

```

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

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Traversal

**Task Description Feedback**:

- make this into a hint?
  > It is also possible to perform list traversal using iteration by item as well as iteration by index.

**Solutions**:

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for ip in ip_address_list:
        if "192.168" in ip:
            result.append(ip)

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for ip in ip_address_list:
        if "192.168" == ip[:7]:
            result.append(ip)

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(len(ip_address_list)):
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(0, len(ip_address_list)):
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(len(ip_address_list)):
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(0, len(ip_address_list)):
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(len(ip_address_list) - 1, -1, -1):
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []

    for index in range(len(ip_address_list) - 1, -1, -1):
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []
    index = 0

    while index < len(ip_address_list):
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])
        index += 1

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []
    index = 0

    while index < len(ip_address_list):
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])
        index += 1

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []
    index = len(ip_address_list) - 1

    while index >= 0:
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])
        index -= 1

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line
    result = []
    index = len(ip_address_list) - 1

    while index >= 0:
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])
        index -= 1

    return result
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    any solution that starts iterating starting from the end and does not check the first element
    can pass the unit tests through luck (randomness) due to the last test case
    if the last test case does not generate an ip with 192.168 as its first element then the solution will pass
    which does not solve the problem because the problem wants "all ips" meaning iterating through every element
    """
    result = []

    for index in range(len(ip_address_list) - 1, 0, -1):
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    any solution that starts iterating starting from the end and does not check the first element
    can pass the unit tests through luck (randomness) due to the last test case
    if the last test case does not generate an ip with 192.168 as its first element then the solution will pass
    which does not solve the problem because the problem wants "all ips" meaning iterating through every element
    """
    result = []

    for index in range(len(ip_address_list) - 1, 0, -1):
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    any solution that starts iterating starting from the end and does not check the first element
    can pass the unit tests through luck (randomness) due to the last test case
    if the last test case does not generate an ip with 192.168 as its first element then the solution will pass
    which does not solve the problem because the problem wants "all ips" meaning iterating through every element
    """
    result = []
    index = len(ip_address_list) - 1

    while index > 0:
        if "192.168" in ip_address_list[index]:
            result.append(ip_address_list[index])
        index -= 1

    return result
```

```python
def return_all_192_168 (ip_address_list):
    # TODO - Write your code here. Make sure to edit the return line

    """
    any solution that starts iterating starting from the end and does not check the first element
    can pass the unit tests through luck (randomness) due to the last test case
    if the last test case does not generate an ip with 192.168 as its first element then the solution will pass
    which does not solve the problem because the problem wants "all ips" meaning iterating through every element
    """
    result = []
    index = len(ip_address_list) - 1

    while index > 0:
        if "192.168" == ip_address_list[index][:7]:
            result.append(ip_address_list[index])
        index -= 1

    return result
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

<hr>

## Files

### Reading

**Task Description Feedback**:

- not clear on how many lines are in the file (I assume that it'll always only have 1 line)
- could be simpler / clearer
  > To open this file, we would call the open function. The variable, fileref, now holds a reference to the file object returned by open. When we are finished with the file, we can close it by using the close method. After the file is closed any further attempts to use fileref will result in an error.
  - could rephrase to something like "To open this file, we would call the open function which returns a file object that has a read and close method. It is good practice to always close the file when you are done with it by using the close method. After the file is closed any further attempts to use the file object will result in an error."

**Solutions**:

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")
    first_line = file_obj.readline()
    file_obj.close()
    return first_line
```

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")
    first_line = ""

    for line in file_obj:
        first_line = line
        break

    file_obj.close()

    return first_line
```

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")

    for line in file_obj:
        return line
```

```python
def read_file_first_line(filename):
    first_line = open(filename, "r").readline()
    return first_line
```

```python
def read_file_first_line(filename):
    return open(filename, "r").readline()
```

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")
    first_line = file_obj.read()
    file_obj.close()
    return first_line
```

```python
def read_file_first_line(filename):
    first_line = open(filename, "r").read()
    return first_line
```

```python
def read_file_first_line(filename):
    return open(filename, "r").read()
```

```python
def read_file_first_line(filename):
    first_line = open(filename, "r").readlines()[0]
    return first_line
```

```python
def read_file_first_line(filename):
    return open(filename, "r").readlines()[0]
```

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")
    first_line = file_obj.readlines()[0]
    file_obj.close()
    return first_line
```

```python
def read_file_first_line(filename):
    lines = open(filename, "r").readlines()

    for line in lines:
        return line
```

```python
def read_file_first_line(filename):
    file_obj = open(filename, "r")
    lines = file_obj.readlines()
    first_line = ""

    for line in lines:
        first_line = line
        break

    file_obj.close()

    return first_line
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def read_file_first_line(filename):
    """
    does not read a file
    """
    return """
    83.149.9.216 - - [17/May/2015:10:05:03 +0000] "GET /presentations/logstash-monitorama-2013/images/kibana-search.png HTTP/1.1" 200 203023 "http://semicomplete.com/presentations/logstash-monitorama-2013/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/32.0.1700.77 Safari/537.36"
    """
```

```python
def read_file_first_line(filename):
    """
    does not read a file
    """
    first_line = """
    83.149.9.216 - - [17/May/2015:10:05:03 +0000] "GET /presentations/logstash-monitorama-2013/images/kibana-search.png HTTP/1.1" 200 203023 "http://semicomplete.com/presentations/logstash-monitorama-2013/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/32.0.1700.77 Safari/537.36"
    """
    return first_line
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Writing

**Task Description Feedback**:

- missing a task description
  - should clarify on what counts as writing to a file, does overwriting the lines in the file count? does appending a new line in the file count?
- unable to execute any unit test - "No tests were found"

**Solutions**:

```python
def write_line_to_file(filename):
    file_obj = open(filename, "w")
    file_obj.write("text")
    file_obj.close()
```

```python
def write_line_to_file(filename):
    open(filename, "w").write("a")
```

```python
def write_line_to_file(filename):
    file_obj = open(filename, "a")
    file_obj.write("\ntext")
    file_obj.close()
```

```python
def write_line_to_file(filename):
    open(filename, "a").write("\ntext")
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```

```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

<hr>

## Dictionaries

### Accessing

**Task Description Feedback**:

- task description says to create an entry with the key "Router" when the unit test is looking for "Gateway"

**Solutions**:

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    return dictionary.get(hostname, None)
```

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    if hostname in dictionary:
        return dictionary.get(hostname)

    return None
```

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    if hostname in dictionary:
        return dictionary[hostname]

    return None
```

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    if hostname not in dictionary:
        return None

    return dictionary[hostname]
```

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    if hostname not in dictionary:
        return None

    return dictionary.get(hostname)
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```python
def dns_resolve(hostname):
    # todo: replace this with an actual task

    """
    does not use a dictionary
    """
    if hostname == "Linux":
        return "192.168.1.101"
    elif hostname == "Windows":
        return "192.168.1.102"
    elif hostname == "Gateway":
        return "192.168.1.1"
    else:
        return None
```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)

### Creating

**Task Description Feedback**:

- task description says to create an entry with the key "Router" when the unit test is looking for "Gateway"

**Solutions**:

```python
def create_network_dns():
    # todo: replace this with an actual task
    dictionary = {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }

    return dictionary
```

```python
def create_network_dns():
    # todo: replace this with an actual task
    return {
        "Linux": "192.168.1.101",
        "Windows": "192.168.1.102",
        "Gateway": "192.168.1.1"
    }
```

```python
def create_network_dns():
    # todo: replace this with an actual task
    return dict([("Linux", "192.168.1.101"), ("Windows", "192.168.1.102"), ("Gateway", "192.168.1.1")])
```

```python
def create_network_dns():
    # todo: replace this with an actual task
    dictionary = dict([("Linux", "192.168.1.101"), ("Windows", "192.168.1.102"), ("Gateway", "192.168.1.1")])

    return dictionary
```

**False Negatives**:

<!-- correct answer, graded as incorrect -->

```

```

**False Positives**:

<!-- solution passes test cases but does not solve the problem -->

```

```

[⬆️ back to table of contents](https://github.com/6ri4n/CNE330_Smoke_Testing?tab=readme-ov-file#table-of-contents)
