Polynomial from Roots (Assignment)
■ Problem Statement
We are given polynomial roots in **JSON format**, where each root is expressed in a specific base
(binary, octal, decimal, hexadecimal, etc.).
The task is to:
1. Parse the JSON input.
2. Convert each root into a **decimal integer**.
3. Use exactly **k roots** (where k = degree + 1) to form the polynomial.
4. Expand the polynomial into standard form:
P(x) = a_m x^m + a_{m-1} x^{m-1} + … + a_0
5. Output the coefficients [a_m, a_{m-1}, …, a_0].
---
■■ Approach
1. **Parse JSON Input**
- Extract n (total roots given) and k (minimum required).
- Collect the first k roots.
2. **Convert Roots**
- Each root has a "base" and "value".
- Convert to decimal using base conversion.
Example:
"2": { "base": "2", "value": "111" }
→ Decimal = 7.
3. **Form Polynomial**
- Build polynomial as:
(x - r1)(x - r2)...(x - rk)
4. **Expand Polynomial**
- Multiply step by step to compute coefficients.
- Handle large numbers using BigInteger (Java) or equivalent.
5. **Output**
- Print coefficients as a list.
---
■■ Example
Input
{
"keys": {
"n": 4,
"k": 3
},
"1": {
"base": "10",
"value": "4"
},
"2": {
"base": "2",
"value": "111"
},
"3": {
"base": "10",
"value": "12"
},
"6": {
"base": "4",
"value": "213"
}
}
Conversion
- Root 1: 4
- Root 2: 7
- Root 3: 12
Polynomial
(x - 4)(x - 7)(x - 12) = x^3 - 23x^2 + 160x - 336

Output
[1, -23, 160, -336]
---
■ How to Run
1. Clone the repo:
git clone https://github.com/username/repo-name.git
cd repo-name
2. Compile and run (Java example):
javac PolynomialFromRoots.java
java PolynomialFromRoots input.json
3. The program will print polynomial coefficients.
---
■ Repository Structure
repo-name
■ PolynomialFromRoots.java # Main source code
■ input.json # Sample test case input
■ README.md # Project documentation
■ output.txt # Output from program
---
■ Deliverables
- Source code implementation.
- Sample input JSON.
- Output file/screenshot.
- README with explanation.
