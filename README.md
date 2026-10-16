# Python Week 4 Workshop

Work in Codespaces.

You may use the module cheat sheets if you need to look up any Python commands:

https://github.com/phil-lewis-exe/PythonCheatSheets

**During the workshop try not to use any websites other than the cheat sheets - everything you need can be found there.**

As you work through the tasks, and at the end of the session, remember to save your files from Codespaces (where they exist in your temporary workspace) to GitHub, using the command:

```
git_helper --commit
```

in the lower terminal panel.

---

## TASKS

### Part 0: Don't forget to call!

*Work in file **`w4_part0.py`***

When we are coding functions, we need to test if they run using diagnostic checks.

For example if we work in file `w4_part0.py` and have the function:

```
def double_number(mynum):
    return mynum+2
```

We can run the code in the file by typing:

```
python w4_part0.py
```

In the lower panel of Codespaces. However if the file contains a function definition only, running the file will not do anything - it is creating the function, but there is no code to call it, so nothing will actually run.


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

Create the code file **`w4_part1.py`**.

On the left side of the screen, click the **☰** button to open the menu, then select **File > New File**.

In this file write a Python function called `say_hi` that takes one argument `n`.

The function should display the message `hi` `n` times, each on its own line.

(i.e. when called with the value 9 it would display hi 9 times).

After writing the function show how to call it, using the example value 4.

The output should be:

```
hi
hi
hi
hi
```

---

### Part 2: Calculating a percentage change

*Work in file **`w4_part2.py`***

A programmer wants to write code to calculate the percentage change between two values `a` and `b`.

This can be found using the following formula:

$\texttt{percent change} = \frac{b - a}{a} \times 100$

Write a function `percent_change` that takes two arguments `a` and `b` and returns the percent change.

You can assume `a` is never 0.

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

A programmer wants to write code to validate that a provided age is sensible.

This must be done in function `validate` that takes a single argument `age`.

This will **return** the string `passed` if the age is an integer, between 0 and 120 inclusive.

It will **return** the string `failed` for any other age value.

The following code shows how we can use the `isinstance()` function to check if a variable is an instance of a particular data type:

```python
if isinstance(age,int):
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

The output should be:

```
Check -5 returned: failed
Check 20 returned: passed
Check 150 returned: failed
Check 7.2 returned: failed
```

Can you improve the test code, so it will take a list:

```
test_vals = [-5, 20, 150, 7.2]
```

Then use a `for` loop to carry out the check for each value in the list, giving output as above.

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
print(f"Change over series: {series1} is {check_series1}")

check_series2 = net_change(series2)
print(f"Change over series: {series2} is {check_series2}")
```

The changes returned by the function should be 3 and -8 for the two test series.

---

### Part 5: Generating a set of sequences

*Work in file **`w4_part5.py`**

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
[2, 3]
[2, 3, 6]
[2, 3, 6, 18]
```

Hint. Lists are mutable objects and when passed into a function by argument, can be changed by actions in the function.

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

First make sure all your files are saved.

In the terminal, in your repository folder, run the following command to build a zip of the work you completed in the workshop:

```
git_helper --zip
```

This commits your work and creates a file named `archive_<repo name>__<date-time>.zip`. You will see it in the file panel.

Right click on the zip file to download a copy to your computer.
