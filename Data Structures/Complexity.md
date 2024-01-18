
Algorithms can be analyzed by using the following and the analysis process can be _customized_ for specific needs/requirements:
1. **Time**
2. **Space**
3. Network I/O
4. Power Consumption
5. CPU Registers
### Algorithm Analysis
```c
void swap(a int, b int) {
	temp = a; // ---> 1 unit of time | 1 unit of space
	a = b; // ---> 1 unit of time | 1 unit of space
	b = temp; // ---> 1 unit of time | 1 unit of space
}
```

**Time**
f(n) = 3 units of time -> O(1) -> Constant

**Space**
s(n) = 3 units of space -> O(1) -> Constant
### Frequency Count Method
```c
int sum(A int[], n int) { 
	s = 0; // ---> 1 unit of time 
	for (i=0;i<n;i++) { // 1, n+1, n ---> n+1 unit of time
		s = s + A[i]; // --> n unit of time
	}
	return s; // 1 unit of time
}
```

**Time**
f(n) = 2n + 3 -> O(n) -> Linear

**Space**
**A** has _n units of space_
**n** is 1 unit of space
**s** is 1 unit of space
**i** is 1 unit of space
s(n) = n + 3 -> O(n) -> Linear

---

```c
void add(A int[], B int[], n int) {
	for (i=0;i<n;i++) { // n + 1 
		for (j=0;j<n;j++) { // n x (n + 1)
			C[i,j] = A[i,j] + B[i,j]; // n x n
		}
	}
}
```

**Time**
f(n) = 2n<sup>2</sup> + 2n  + 1 -> O(n<sup>2</sup>)

**Space**
A has _n<sup>2</sup> units of space_ -> Matrix
B has _n<sup>2</sup> units of space_ -> Matrix
C has _n<sup>2</sup> units of space_ -> Matrix
n is 1 unit of space
i is 1 unit of space
j is 1 unit of space
s(n) = 3n<sup>2</sup> + 3 -> O(n<sup>2</sup>)

---

```c
void multiply(A int[], B int[], n int) {
	for (i=0;i<n;i++) {                            // n + 1
		for (j=0;j<n;j++) {                        // n * (n + 1)
			C[i,j] = 0;                            // n * n
			for (k=0;k<n;k++) {                    // n * n * (n + 1)
				C[i,j] = C[i,j] + A[i,k] + B[k,j]; // n * n * n
			}
		}
	}
}
```

**Time**
f(n) = 2n<sup>3</sup> + 3n<sup>2</sup>  + 2n + 1 -> O(n<sup>3</sup>)

**Space**
A -> n<sup>2</sup>
B -> n<sup>2</sup>
C -> n<sup>2</sup>
n -> 1
i -> 1
j -> 1
k -> 1
f(n) = 3n<sup>2</sup> + 4 -> O(n<sup>2</sup>)