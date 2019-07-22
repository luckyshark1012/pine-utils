# Function to find Nth fibonacci

#### Snippet Description:

Function to find the sequence value of the Nth fibonacci number.

references:
* [link1](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/ "Multiple Methods:")


#### Code:
<!--  -->
<!-- code goes between the backticks: -->
```javascript
//-----------------
//  Binet's Formula to solve the Nth Fibonacci Number
//  pine version=2
f_n_fib(_step) =>
    _phi = 1.618
    _n_phi = 1/_phi
    _return = round(_step >= 0 ? pow(_phi, _step) / sqrt(5) : pow(-_n_phi, _step) / sqrt(5))
//-----------------
```
```
//-----------------
//  Binet's Formula to solve the Nth Fibonacci Number
//  pine version=4
f_n_fib(_step) =>
    float _phi = 1.618
    float _n_phi = 1/_phi
    int _return = round(abs(_step >= 0 ? pow(_phi, _step) / sqrt(5.0) : pow(-_n_phi, _step) / sqrt(5)))
    _return
//-----------------
```

#### Example:


Find the input index value in the fibonacci sequence, <br/>
00 01 02 03 04 05 06 07 08 09 \[10] 11 ... <br/>
00 01 01 02 03 05 08 13 21 34 \[55] 89 ...

<!--  -->
<!-- code goes between the backticks: -->
```javascript
//@version=4
study("Function - Nth Fibonacci Number")

//-----------------
//Binet's Formula to solve the Nth Fibonacci Number
f_n_fib(_step) =>
    float _phi = 1.618
    float _n_phi = 1/_phi
    int _return = round(abs(_step >= 0 ? pow(_phi, _step) / sqrt(5.0) : pow(-_n_phi, _step) / sqrt(5)))
    _return
//-----------------

var int step = 1
if bar_index >= f_n_fib(step)
    step := step + 1
int current_fib = f_n_fib(step)

int index = input(10)
int manual_example = f_n_fib(index)

plot(series=current_fib, title='Fib Time Number', color=color.black)
plot(series=bar_index, title='Time', color=color.blue)
plot(series=manual_example, title='example', color=color.red)

```
