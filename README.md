# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
  
## Program
```
-- PL/SQL program to find the greatest of two numbers
DECLARE
    num1 NUMBER := 50;  -- First number
    num2 NUMBER := 80;  -- Second number
    greatest NUMBER;    -- Variable to store the greatest number
BEGIN
    -- Compare the numbers
    IF num1 > num2 THEN
        greatest := num1;
    ELSE
        greatest := num2;
    END IF;
    
    -- Display the greatest number
    DBMS_OUTPUT.PUT_LINE('Greater number is: ' || greatest);
END;
/
```

**Expected Output:**  
Greater number is: 80
## Output
<img width="1028" height="798" alt="image" src="https://github.com/user-attachments/assets/ae94bd82-be29-41d7-80cc-28d94421ae21" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
  
## Program
```
-- PL/SQL program to calculate sum of first N natural numbers
DECLARE
    n NUMBER := 10;       -- Total numbers to sum
    sum NUMBER := 0;      -- Variable to store sum
    i NUMBER := 1;        -- Loop counter
BEGIN
    -- WHILE loop to calculate sum
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;
    
    -- Display the result
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
**Expected Output:**  
Sum of first 10 natural numbers is: 55
## Output
<img width="1019" height="770" alt="image" src="https://github.com/user-attachments/assets/4a5afcd1-d700-4b2b-b07e-b40dd4c98f5e" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
## Program
```
-- PL/SQL program to generate Fibonacci series
DECLARE
    n NUMBER := 7;      -- Number of terms to generate
    a NUMBER := 0;      -- First Fibonacci number
    b NUMBER := 1;      -- Second Fibonacci number
    c NUMBER;           -- Variable to store next Fibonacci number
    i NUMBER := 3;      -- Counter starts from 3 since first two terms are known
BEGIN
    -- Display the first two terms
    DBMS_OUTPUT.PUT('Fibonacci sequence: ' || a || ', ' || b);
    
    -- Loop to generate remaining terms
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT(', ' || c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
    
    DBMS_OUTPUT.PUT_LINE('');  -- Move to the next line
END;
/
```
**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
## Output
<img width="1023" height="787" alt="image" src="https://github.com/user-attachments/assets/a6775bea-3738-493b-b5fc-79698dd1950a" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
## Program
```
-- PL/SQL program to reverse a number
DECLARE
    n NUMBER := 1535;        -- Original number
    reversed NUMBER := 0;    -- Variable to store reversed number
    digit NUMBER;            -- Variable to store extracted digit
    temp NUMBER;             -- Temporary variable to manipulate n
BEGIN
    temp := n;  -- Copy of original number

    -- Loop to reverse the number
    WHILE temp > 0 LOOP
        digit := MOD(temp, 10);          -- Extract last digit
        reversed := reversed * 10 + digit; -- Append digit to reversed number
        temp := FLOOR(temp / 10);        -- Remove last digit
    END LOOP;

    -- Display the reversed number
    DBMS_OUTPUT.PUT_LINE('Reversed number is: ' || reversed);
END;
/
```
**Expected Output:**  
n = 1535  
Reversed number is 5351
## Output
<img width="1016" height="803" alt="image" src="https://github.com/user-attachments/assets/bc14dfa2-1bab-4137-a894-903d42146374" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
## Program
```
-- PL/SQL program to find the largest of three numbers
DECLARE
    a NUMBER := 10;   -- First number
    b NUMBER := 9;    -- Second number
    c NUMBER := 15;   -- Third number
    largest NUMBER;   -- Variable to store largest number
BEGIN
    -- Nested IF-ELSIF-ELSE to find the largest
    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
    
    -- Display the largest number
    DBMS_OUTPUT.PUT_LINE('Largest of three numbers is: ' || largest);
END;
/
```
**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## Output
<img width="1007" height="723" alt="image" src="https://github.com/user-attachments/assets/d3bd33bf-ad67-45e2-999f-75a031961f5b" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.


