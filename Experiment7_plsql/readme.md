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

**Expected Output:**  
Greater number is: 80

### program:-
~~~sql


DECLARE
    num1 NUMBER := 50;
    num2 NUMBER := 80;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;


~~~

### output:-
<img width="331" height="138" alt="image" src="https://github.com/user-attachments/assets/6d5ffbff-ce83-40c5-87ce-b1cc87101494" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55


### program:-
~~~sql


DECLARE
    n NUMBER := 10;  
    i NUMBER := 1;
    sum NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;


~~~

### output:-
<img width="439" height="163" alt="image" src="https://github.com/user-attachments/assets/56cc8a61-fdf6-4f62-b368-5e5cdde99bc8" />


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8


### program:-
~~~sql


DECLARE
    n NUMBER := 7;       -- Number of terms
    a NUMBER := 0;       -- First term
    b NUMBER := 1;       -- Second term
    c NUMBER;            -- Next term
    i NUMBER := 1;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    
    WHILE i <= n LOOP
        DBMS_OUTPUT.PUT_LINE(a);
        c := a + b;
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;


~~~

### output:-
<img width="448" height="292" alt="image" src="https://github.com/user-attachments/assets/491811db-3b96-4137-8750-7ffa006cef7c" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351


### program:-
~~~sql


DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    rem NUMBER;
BEGIN
    WHILE n > 0 LOOP
        rem := MOD(n, 10);
        rev := (rev * 10) + rem;
        n := TRUNC(n / 10);
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;


~~~

### output:-
<img width="434" height="178" alt="image" src="https://github.com/user-attachments/assets/72062784-7e35-4288-a9ad-ede8a813b3ea" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15


### program:-
~~~sql

DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
BEGIN
    IF (a > b) AND (a > c) THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is ' || a);
    ELSIF (b > a) AND (b > c) THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is ' || c);
    END IF;
END;



~~~

### output:-
<img width="441" height="153" alt="image" src="https://github.com/user-attachments/assets/bbbb2e7c-90f1-4663-8de3-10963226dc1c" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

