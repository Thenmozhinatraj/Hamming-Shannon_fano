# Hamming-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

Aim:
To implement Huffman and Shannon-Fano coding for a discrete memoryless source with given probabilities and analyze the efficiency, redundancy, and variance.

Software Required:
Python 3.x

Program:
#Huffman and Shannon-Fano code
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
for i in range (n): 
    l = float(input(f"Enter the length of the sample values {i + 1}: "))  
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
print(f"Variance is : {var}")

Calculation:
![WhatsApp Image 2025-03-23 at 13 11 17_d46dc832](https://github.com/user-attachments/assets/ca7e42e6-7813-4ceb-8fb2-2a6c6d84d969)
![WhatsApp Image 2025-03-23 at 13 05 48_515ed167](https://github.com/user-attachments/assets/562dcd56-b618-4ea1-a4a1-78bea54d9aad)
![WhatsApp Image 2025-03-23 at 13 05 48_d375cdcf](https://github.com/user-attachments/assets/9f102936-dda6-426a-9014-17e8b319babe)

Results:
The experiment demonstrates the successful application of Shannon-Fano or Huffman coding, achieving optimal efficiency with no redundancy, which is ideal for data compression. The observed Parameters are:
Average Codeword Length is : 2.625
Entropy is : 2.625
Efficiency is : 1.0
Redudancy is : 0.0
Variance is : 0.484
