# Low level native sort and eliminate duplicates

Ex. (189) - <i>Low level native sort and eliminate duplicates (I)</i>, is presented here in three programming languages: <a href="https://github.com/Gagniuc/Python-Coding-Examples-from-Simple-to-Complex">Python</a>, <a href="https://github.com/Gagniuc/MATLAB-Coding-Examples-from-Simple-to-Complex">MATLAB</a>, and <a href="https://github.com/Gagniuc/JavaScript-Coding-Examples-from-Simple-to-Complex">JavaScript</a>. Although the implementations differ in syntax, the underlying concept remains identical across all three versions. Each code sample is reproduced from its respective volume of the series <i>Coding Examples from Simple to Complex</i> (Springer, 2024).

***

The example initializes two arrays, <i>a</i> and <i>b</i>, with <i>a</i> initially being an empty array and <i>b</i> containing some numerical values. It then defines two variables, <i>r</i> and <i>n</i>, where <i>r</i> is set to 0, and <i>n</i> is assigned the length of array <i>b</i>. The code proceeds to enter a loop that iterates through the elements of array <i>b</i> using a <i>for</i>-loop, where <i>i</i> serves as the loop counter. Inside the loop, it assigns the value of <i>b[i]</i> to <i>a[b[i]]</i>. This effectively creates a new array <i>a</i> where the indices correspond to the values of <i>b</i>, and the values in <i>a</i> are the same as the corresponding values in <i>b</i>. After that, the code calculates the length of the array <i>a</i> by getting the maximum value among the elements (as the maximum value is equal to the number of elements), and stores it in the variable <i>m</i>.

A second <i>for</i>-loop begins, with <i>j</i> as the loop counter, iterating through the indices of array <i>a</i>. Inside this loop, it checks if there is a non-falsy value at index <i>j</i> in array <i>a</i>. If a non-falsy value is found, it assigns that value to <i>b[r]</i> and increments the value of <i>r</i>. Next, the code prints the contents of array <i>b</i>.

Note that this native sorting method works well for number sequences of short ranges and is written for this book. To my knowledge it is not published anywhere but here. Note that the time spent by this method to sort the values of an array is <i>n + m</i>, where <i>m</i> represents the maximum value over elements of the array.

## Example in Python:

```python
a = {}
b = [3, 6, 2, 78, 99, 1, 4]

r = 0
n = len(b)

for i in range(n):
    a[b[i]] = b[i]

m = max(a.keys()) + 1

for j in range(m):
    if j in a:
        b[r] = a[j]
        r += 1

print(b)
``` 

```text
Python output:
[1, 2, 3, 4, 6, 78, 99]
```

## Example in Javascript:

```javascript
let a = [];
let b = [3, 6, 2, 78, 99, 1, 4];

let r = 0;
let n = b.length;
    
for (let i=0; i<n; i++) {
    a[b[i]] = b[i];
}
    
let m = a.length; // max val
    
for (let j=0; j<m; j++) {
    if(a[j]){b[r] = a[j]; r++}
}

print(b);
```

```text
Javascript output:
[1, 2, 3, 4, 6, 78, 99]
```

## Example in Matlab:

```matlab
b = [3, 6, 2, 78, 99, 1, 4];
n = length(b);

% Initialize array a with 
% zeros up to the maximum 
% value in b.

a = zeros(1, max(b));

% Fill a using values 
% from b as indices.

for i = 1:n
    a(b(i)) = b(i);
end

% Compact a back into b, 
% effectively sorting it r = 1;

for j = 1:length(a)
    if a(j) ~= 0
        b(r) = a(j);
        r = r + 1;
    end
end

% Truncate b to the new 
% size r - 1 to remove 
% trailing zeros.

b = b(1:r-1);

disp(b);
```

```text
Matlab output:
[1, 2, 3, 4, 6, 78, 99]
```

## References

- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in Python, Springer, 2024, pp. 1-245.</i>
- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in MATLAB, Springer, 2024, pp. 1-255.</i>
- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in Javascript, Springer, 2024, pp. 1-240.</i>

***
