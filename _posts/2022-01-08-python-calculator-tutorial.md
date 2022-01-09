---
layout: post
title:  "Python Calculator Tutorial"
author: richard
categories: [ Tutorial ]
image: assets/images/python_calculator_tutorial.png
thumbnail: assets/images/thumbnails/python_calculator_tutorial.png
tags: [recent, tutorials]
pitch: "Create a GUI Calculator with Python 3"
permalink: "/blog/python-calculator-tutorial"
---

It is common for Python programming students to create a text-based calculator. However, creating a GUI calculator requires a different format and syntax than simply calling the Python math module.

Below is a tutorial you may use to create a calculator using the Tkinter library.

<hr>

Import the Tkinter library.
```python
# Imports
import tkinter as tk

root = tk.Tk()
```
<br>
<br>
Create some common, global, variables that you will refer to countless times while coding the program.
```python
# Common Variables
btn_height = 4
btn_width = 4
font = "Georgia"
font_size = 20
```
<br>
<br>
Create a title for your calculator application.
```python
# Title
root.title('Python Calculator')  
```
<br>
<br>
Assign the calculator's basic dimensions (length and width).
```python
# Basic Design Dimensions
root.geometry('350x560')
root.resizable(height=False, width=False)  # Delete line to make app dimensions resizable
```
<br>
<br>
(Optional) Configure the background color.
```python
# Colors
# Background Color
root.configure(background="white")
```
<br>
<br>
Create the calculator input text field.
```python
calc_input = tk.Text(root, height=1, width=26, font=(font, font_size))
calc_input.grid(columnspan=4)
```
<br>
<br>
Create a result String variable.
```python
result = ""
```
<br>
<br>
Define a calculation function.
```python
def calc():
    calc_result = eval(retrieve_user_input())
    calc_input.delete(1.0, tk.END)
    calc_result = format(calc_result, '.2f')  # Limit result to 2 decimal places
    calc_input.insert(1.0, str(calc_result))
```
<br>
<br>
Define a function to retrieve user input.
```python
def retrieve_user_input():
    input_result = calc_input.get(1.0, tk.END)
    return input_result
```
<br>
<br>
Define a function to insert user input.
```python
def user_input(number):
    calc_input.insert(tk.END, str(number))
```
<br>
<br>
Define a function to clear the text field.
```python
def clear():
    calc_input.delete(1.0, tk.END)
```
<br>
<br>
Define a function to create the calculator's buttons.
```python
def calc_btn(calc_root, btn_text, btn_command, height, width, btn_font, btn_font_size, btn_row, btn_column):
    calc_btn_template = tk.Button(calc_root,
                                  text=btn_text,
                                  command=btn_command,
                                  height=height,
                                  width=width,
                                  font=(btn_font, btn_font_size))
    calc_btn_template.grid(row=btn_row, column=btn_column)
    return calc_btn_template
```
<br>
<br>
Create the first row of buttons. You will notice all buttons share a similar template.
```python
# BUTTONS
# ROW 1
btn_clear = calc_btn(root, "C", lambda: clear(), btn_height, btn_width, font, font_size, 1, 0)
# Exponent btn
btn_exponent = calc_btn(root, "e", lambda: user_input("**"), btn_height, btn_width, font, font_size, 1, 1)
# Pi btn
btn_pi = calc_btn(root, "pi", lambda: user_input(3.14), btn_height, btn_width, font, font_size, 1, 2)
# Percentage btn
btn_percentage = calc_btn(root, "%", lambda: user_input("%"), btn_height, btn_width, font, font_size, 1, 3)
```
<br>
<br>
Create the second row of buttons.
```python
#  ROW 2
# 7 btn
btn_7 = calc_btn(root, "7", lambda: user_input(7), btn_height, btn_width, font, font_size, 2, 0)
# 8 btn
btn_8 = calc_btn(root, "8", lambda: user_input(8), btn_height, btn_width, font, font_size, 2, 1)
# 9 btn
btn_9 = calc_btn(root, "9", lambda: user_input(9), btn_height, btn_width, font, font_size, 2, 2)
# Division btn
btn_division = calc_btn(root, "/", lambda: user_input("/"), btn_height, btn_width, font, font_size, 2, 3)
```
<br>
<br>
Create the third row of buttons.
```python3
# ROW 3
# 4 btn
btn_4 = calc_btn(root, "4", lambda: user_input(4), btn_height, btn_width, font, font_size, 3, 0)
# 5 btn
btn_5 = calc_btn(root, "5", lambda: user_input(5), btn_height, btn_width, font, font_size, 3, 1)
# 6 btn
btn_6 = calc_btn(root, "6", lambda: user_input(6), btn_height, btn_width, font, font_size, 3, 2)
# Division btn
btn_multiplication = calc_btn(root, "X", lambda: user_input("*"), btn_height, btn_width, font, font_size, 3, 3)
```
<br>
<br>
Create the fourth row of buttons.
```python
# ROW 4
# 1 btn
btn_1 = calc_btn(root, "1", lambda: user_input(1), btn_height, btn_width, font, font_size, 4, 0)
# 2 btn
btn_2 = calc_btn(root, "2", lambda: user_input(2), btn_height, btn_width, font, font_size, 4, 1)
# 3 btn
btn_3 = calc_btn(root, "3", lambda: user_input(3), btn_height, btn_width, font, font_size, 4, 2)
# Subtraction btn
btn_subtraction = calc_btn(root, "-", lambda: user_input("-"), btn_height, btn_width, font, font_size, 4, 3)
```
<br>
<br>
Create the fifth row of buttons.
```python
# ROW 5
# 0 btn
btn_0 = calc_btn(root, "0", lambda: user_input("0"), btn_height, btn_width, font, font_size, 5, 0)
# Decimal btn
btn_decimal = calc_btn(root, ".", lambda: user_input("."), btn_height, btn_width, font, font_size, 5, 1)
# Equate btn
btn_equate = calc_btn(root, "=", lambda: calc(), btn_height, btn_width, font, font_size, 5, 2)
# Addition btn
btn_addition = calc_btn(root, "+", lambda: user_input("+"), btn_height, btn_width, font, font_size, 5, 3)
```
<br>
<br>
Finally, run the main loop of the program.
```python
# Run main loop
root.mainloop()
```
<hr>
<br>
<br>
Below is the full program code. You can copy the code here or download it from <a href="https://github.com/RichardLudwig/PythonDemos/blob/main/python_calculator.py" target="_blank">GitHub</a>.
{% highlight python linenos %}
# Imports
import tkinter as tk

root = tk.Tk()

# Common Variables
btn_height = 4
btn_width = 4
font = "Georgia"
font_size = 20

# Title
root.title('Python Calculator')

# Basic Design Dimensions
root.geometry('350x560')
root.resizable(height=False, width=False)  # Delete line to make app dimensions resizable

# Colors
# Background Color
root.configure(background="white")

calc_input = tk.Text(root, height=1, width=26, font=(font, font_size))
calc_input.grid(columnspan=4)

result = ""


def calc():
    calc_result = eval(retrieve_user_input())
    calc_input.delete(1.0, tk.END)
    calc_result = format(calc_result, '.2f')  # Limit result to 2 decimal places
    calc_input.insert(1.0, str(calc_result))


def retrieve_user_input():
    input_result = calc_input.get(1.0, tk.END)
    return input_result


def user_input(number):
    calc_input.insert(tk.END, str(number))


def clear():
    calc_input.delete(1.0, tk.END)


def calc_btn(calc_root, btn_text, btn_command, height, width, btn_font, btn_font_size, btn_row, btn_column):
    calc_btn_template = tk.Button(calc_root,
                                  text=btn_text,
                                  command=btn_command,
                                  height=height,
                                  width=width,
                                  font=(btn_font, btn_font_size))
    calc_btn_template.grid(row=btn_row, column=btn_column)
    return calc_btn_template


# BUTTONS
# ROW 1
btn_clear = calc_btn(root, "C", lambda: clear(), btn_height, btn_width, font, font_size, 1, 0)
# Exponent btn
btn_exponent = calc_btn(root, "e", lambda: user_input("**"), btn_height, btn_width, font, font_size, 1, 1)
# Pi btn
btn_pi = calc_btn(root, "pi", lambda: user_input(3.14), btn_height, btn_width, font, font_size, 1, 2)
# Percentage btn
btn_percentage = calc_btn(root, "%", lambda: user_input("%"), btn_height, btn_width, font, font_size, 1, 3)

#  ROW 2
# 7 btn
btn_7 = calc_btn(root, "7", lambda: user_input(7), btn_height, btn_width, font, font_size, 2, 0)
# 8 btn
btn_8 = calc_btn(root, "8", lambda: user_input(8), btn_height, btn_width, font, font_size, 2, 1)
# 9 btn
btn_9 = calc_btn(root, "9", lambda: user_input(9), btn_height, btn_width, font, font_size, 2, 2)
# Division btn
btn_division = calc_btn(root, "/", lambda: user_input("/"), btn_height, btn_width, font, font_size, 2, 3)

# ROW 3
# 4 btn
btn_4 = calc_btn(root, "4", lambda: user_input(4), btn_height, btn_width, font, font_size, 3, 0)
# 5 btn
btn_5 = calc_btn(root, "5", lambda: user_input(5), btn_height, btn_width, font, font_size, 3, 1)
# 6 btn
btn_6 = calc_btn(root, "6", lambda: user_input(6), btn_height, btn_width, font, font_size, 3, 2)
# Division btn
btn_multiplication = calc_btn(root, "X", lambda: user_input("*"), btn_height, btn_width, font, font_size, 3, 3)

# ROW 4
# 1 btn
btn_1 = calc_btn(root, "1", lambda: user_input(1), btn_height, btn_width, font, font_size, 4, 0)
# 2 btn
btn_2 = calc_btn(root, "2", lambda: user_input(2), btn_height, btn_width, font, font_size, 4, 1)
# 3 btn
btn_3 = calc_btn(root, "3", lambda: user_input(3), btn_height, btn_width, font, font_size, 4, 2)
# Subtraction btn
btn_subtraction = calc_btn(root, "-", lambda: user_input("-"), btn_height, btn_width, font, font_size, 4, 3)

# ROW 5
# 0 btn
btn_0 = calc_btn(root, "0", lambda: user_input("0"), btn_height, btn_width, font, font_size, 5, 0)
# Decimal btn
btn_decimal = calc_btn(root, ".", lambda: user_input("."), btn_height, btn_width, font, font_size, 5, 1)
# Equate btn
btn_equate = calc_btn(root, "=", lambda: calc(), btn_height, btn_width, font, font_size, 5, 2)
# Addition btn
btn_addition = calc_btn(root, "+", lambda: user_input("+"), btn_height, btn_width, font, font_size, 5, 3)

# Run main loop
root.mainloop()
{% endhighlight %}