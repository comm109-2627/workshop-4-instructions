# Python Week 4 Workshop

Work in CodeSpaces. 

You may use the following cheat sheets if you need to look up any Python commands.

https://github.com/phil-lewis-exe/PythonCheatSheets

**During the workshop try not to use any websites - everything you need can be found in the module cheat sheets.**

---

## TASKS

### Part 0: Don't forget to call!

When we are coding functions, we need to test if they runs using diagnostic checks. 

For example if we work in file `w4_part0.py` and have the function:

```
def double_number(mynum):
    return mynum+2
```

Running the file will not do anything - it is creating the function, but there is no code to call it, so nothing will actually run.

We need to add code to call the function, choosing some suitable test arguments:

```
def double_number(mynum):
    return mynum+2

# test using function call
result = double_number(2)
print(result)
```

Add the test code to `w4_part0.py` and check the function works. 

There is a problem with this function (hint. it should do what its name suggests). 

Fix the bug and add two more test calls to demonstrate it works for 2 different input values.

---

### Part 1: Say Hi

*Work in file **`w4_part1.py`***

Write a Python function called `say_hi` that takes one argument `n`.

The function should display the message `hi` `n`-times each on a single line.

(i.e. when called with the value 9 it would display hi 9 times).

After writing the function show how to call it, using the example value 4.

The output should be:

```
hi
hi
hi
hi
```

### Part 2: Calculating a percentage change

*Work in file **`w4_part2.py`***

A programmer wants to write code to calculate the percentage change between two values `a` and `b`.

This can be found using the following formula:

$$\texttt{percent change} = \frac{b - a}{a} \times 100$$

Write a function `percent_change` that takes two arguments `a` and `b` and returns the percent change.

After writing your code add the following code lines to test it. 

```python
check_a = percent_change(50,55)
print(f"Percent change from 50 to 55 is {check_a}%")

check_b = percent_change(50,25)
print(f"Percent change from 50 to 25 is {check_b}%")
```

The values shown should be 10.0% and -50.0%.

---


### Part 3: Validating an age variable

*Work in file **`w4_part3.py`***

A programmer wants to write code to validate that a provide age is sensible.

This must be done in function `validate` that takes a single argument `age`.

This will **return** the string `passed` if the age is an integer, between 0 and 120 inclusive.

It will **return** the string `failed` for any other age value.

The following code shows a way to check if the age is an integer:

```python
if age == int(age):
    print("age is an integer")
else:
    print("age is not an integer")
```

Write a function `validate` that takes an argument `age` to do this.

After writing your code add the following code lines to test it. 

```python
check_minus = validate(-5)
print(f"Check -5 returned: {check_minus}")

check_20 = validate(20)
print(f"Check 20 returned: {check_20}")

check_150 = validate(150)
print(f"Check 150 returned: {check_150}")

check_non_int = validate(7.2)
print(f"Check 7.2 returned: {check_non_int}")
```

Check the output is as expected.

Can you improve the test code, so it will take a list:

```
test_vals = [-5, 20, 150, 7.2]
```

Then carry out the check for each value in the list, giving output as above.

---

### Part 4: Finding the net change over a series

*Work in file **`w4_part4.py`***

A programmer wants to write code to calculate the net change between the start and end of a timeseries.

For example look at this example timeseries,

```
[ 16, 15, 12, 13, 14, 11 ]
```

Here the first value is 16 the last value is 11 and the net change is -5.

i.e. the net change can be found using:

$$\texttt{net change} =  \texttt{last value} - \texttt{first value}$$

Write a function `net_change` that takes a single argument `time_series`.

It should return the net change over the time series provided. 

You can assume the time series passed is always valid and contains at least two values.

After writing your code add the following code lines to test it. 

```python 
series1 = [ 1, 0, 2, 4 ]
series2 = [ 10, 0, 2 ]

check_series1 = net_change(series1)
print("Change over series: {series1} is {check_series1}")

check_series2 = net_change(series2)
print("Change over series: {series2} is {check_series2}")
```

The changes returned by the function should be 3 and -8 for the two test series.

### Part 5: Generating a set of sequences

*Work in file **`w4_part5.py`***

A programmer is writing code to explore a mathematical sequence.

In this sequence the next value is found by taking the product of the last two values.

For example for the sequence starting : **2, 3**

The next value is $2 \times 3$, growing the sequence to: **2, 3, 6**

The next value is $3 \times 6$, growing the sequence to: **2, 3, 6, 18**

The next value is $6 \times 18$, growing the sequence to: **2, 3, 6, 18, 108**

Write a function `grow_list` that takes an input argument `mylist` that stores a sequence in a Python list.

The function should calculate the next term in the sequence.

It should return a **new** list that contains the extended sequence.

After writing your code add the following code lines to test it. 

```python
list1 = [ 2, 3 ]
list2 = grow_list(list1)
list3 = grow_list(list2)

print(list1)
print(list2)
print(list3)
```

This should produce the output:

```
[2, 3] [2, 3, 6] [2, 3, 6, 18]
```

Hint. Lists are mutable objects and when passed as a function argument, can be changed by function code.

To avoid changing the original copy you can make a copy of a list using code like:

```python
mylist = [1,2,3]
# option 1
mylist_copy1 = mylist.copy()

# option 2 (uses slice operator)
mylist_copy2 = mylist[:]
```

---

### Submitting your work

Use the following command to build a zip of the work you completed in the workshop. 

You will see the created file in the file panel. 

Right click on the zip file to download a copy to your computer.

```
git_helper --zip
```
