# Simple Calculator Project Using Python:
# Project Overview:-

This is a simple calculator application implemented in Python. The calculator can perform basic arithmetic operations: addition, subtraction, multiplication, and division. The user can perform multiple calculations consecutively without restarting the program.

1 Features:-

- Perform basic arithmetic operations: addition, subtraction, multiplication, and division.
- Continuous calculations with the option to use the result of the previous calculation.
- Option to start a new calculation at any time.

2 Requirements:-

Python 3.x
art module (for printing ASCII art logo, if used)

3 Project Files:-

calculator.py: The main Python script containing the calculator code.
art.py: (Optional) A module that contains the ASCII art for the logo.

4 Code Explanation:-

~ Importing Modules
The script imports the logo from an art module which is used to display a logo when the calculator starts. 

from art import logo

5 Defining Arithmetic Functions:-
Four functions are defined to perform basic arithmetic operations.

# Add
def add(n1, n2):
  return n1 + n2

# Subtract 
def subtract(n1, n2):
  return n1 - n2 

# Multiply
def multiply(n1, n2):
  return n1 * n2 

# Divide 
def divide(n1, n2):
  return n1 / n2

6 Operations Dictionary :- 
A dictionary is defined to map operation symbols to their respective functions.

operations = {
  "+": add,
  "-": subtract,
  "*": multiply,
  "/": divide 
}

7 Calculator Function:-
The main function calculator() handles the input/output and controls the flow of the program.

def calculator():
  print(logo)  # Display the logo
  num1 = float(input("What is the first number?: "))  # Get the first number from the user

  # Display available operations
  for symbol in operations:
    print(symbol) 

  should_continue = True  # A flag to control the loop

  while should_continue:
    operation_symbol = input("Pick an operation: ")  # Get the operation symbol from the user
    num2 = float(input("What is the second number?: "))  # Get the second number from the user
    calculation_function = operations[operation_symbol]  # Get the function based on the operation symbol
    answer = calculation_function(num1, num2)  # Perform the calculation

    print(f"{num1} {operation_symbol} {num2} = {answer}")  # Print the result

    # Ask the user if they want to continue calculating with the result
    if input(f"Type 'y' to continue calculating with {answer}, or type 'n' to start a new calculation: ") == "y":
      num1 = answer  # Use the result for the next calculation
    else:
      should_continue = False  # Exit the loop
      calculator()  # Start a new calculation

8 Running the Calculator
The calculator is started by calling the calculator() function.
calculator()

9 How to Use:-
~ Run the calculator.py script.

~ Enter the first number when prompted.

~ Select an arithmetic operation by entering the corresponding symbol.

~ Enter the second number.

~ View the result of the calculation.

~ Choose to either continue calculating with the result or start a new calculation.

10 Example Usage:-

What is the first number?: 10
+
-
*
/
Pick an operation: +
What is the second number?: 5
10.0 + 5.0 = 15.0
Type 'y' to continue calculating with 15.0, or type 'n' to start a new calculation: y
Pick an operation: *
What is the second number?: 2
15.0 * 2.0 = 30.0
Type 'y' to continue calculating with 30.0, or type 'n' to start a new calculation: n

11 Notes:- 

The art module containing the logo variable should be available in the same directory as the calculator.py script. The logo can be a simple ASCII art representation of a calculator or any other design you prefer.

The script handles division by zero gracefully by allowing Python's built-in exception handling to manage any potential errors.

This documentation provides an overview, detailed explanation of the code, and instructions on how to use the calculator.
