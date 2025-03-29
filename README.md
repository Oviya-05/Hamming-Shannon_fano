# Huffman-Shannon_fano

## Aim:
  The aim of this experiment is to compare the efficiency of Huffman coding and Shannon-Fano coding in compressing data by analyzing their encoding processes and evaluating the compression ratios achieved.
  
## Tools Required:

  * Colab (for executing Python code)
  * Libraries: NumPy, Matplotlib
    
## Program:
~~~
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
~~~
## Output:
  
  Enter the number of Samples : 5
  Enter the probability of sample values 1: 0.4
  Enter the probability of sample values 2: 0.3
  Enter the probability of sample values 3: 0.2
  Enter the probability of sample values 4: 0.05
  Enter the probability of sample values 5: 0.05
  Enter the length of the sample values 1: 2
  Enter the length of the sample values 2: 3
  Enter the length of the sample values 3: 3
  Enter the length of the sample values 4: 4
  Enter the length of the sample values 5: 4
  ![image](https://github.com/user-attachments/assets/04223445-070f-4bf5-a4a9-c32b1173dc74)

## Results:
  The results indicate that Huffman coding generally provides better compression efficiency compared to Shannon-Fano coding, achieving lower average code lengths and improved overall data compression in most test cases.
