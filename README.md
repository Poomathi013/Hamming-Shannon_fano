## Exp-8: Huffman-Shannon_fano
## Name: Poomathi S
## Reg No.: 212223060198
### Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
### Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### Aim :
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### Tools Required :
Python IDE with

-> numpy library

-> math library

### Program :
``` python
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
```
### Calculation :

![Screenshot 2025-03-30 143931](https://github.com/user-attachments/assets/098383bb-9640-4c74-8943-37b104b44bf5)

![WhatsApp Image 2025-03-30 at 09 44 51_33d38299](https://github.com/user-attachments/assets/a024decc-9c73-4aee-bc1d-cf13a2b2e06b)

![WhatsApp Image 2025-03-30 at 09 45 03_aa48d9b5](https://github.com/user-attachments/assets/fa8e5e18-5a1c-4855-ae99-ad18fd689a36)

![WhatsApp Image 2025-03-30 at 09 45 23_34e83640](https://github.com/user-attachments/assets/bb212262-03e7-43e6-b8ac-4d099c27a962)

![WhatsApp Image 2025-03-30 at 09 45 41_e196a934](https://github.com/user-attachments/assets/7be60f4b-709c-4200-b87e-fbfdfb017893)


### Results :
The obtained result are

Average Codeword Length is : 2.625

Entropy is : 2.625

Efficiency is : 1.0

Redudancy is : 0.0

Variance is : 0.484
