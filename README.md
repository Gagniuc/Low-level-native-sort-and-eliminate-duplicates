# Low level native sort and eliminate duplicates

Ex. (189) - Low level native sort and eliminate duplicates (I), is presented here in three programming languages: Python, MATLAB, and JavaScript. Although the implementations differ in syntax, the underlying concept remains identical across all three versions. Each code sample is reproduced from its respective volume of the series <i>Coding Examples from Simple to Complex</i> (Springer, 2024).
***

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
