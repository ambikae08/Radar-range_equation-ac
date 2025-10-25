# Radar-range_equation-ac
# Evaluation of Radar Range Using Scilab
---

## Aim
To calculate the **maximum range of a radar system** using the **Radar Range Equation** and verify the results through **Scilab programming**.

---

## Theory
The **Radar Range Equation** is a key relationship used in radar system design to determine the maximum distance (**range**) at which a radar can detect a target.  

It is expressed as:



---
## Algorithm: Radar Range Calculation and Plotting

1. Start the program.  
2. Clear workspace and close all figures.  
3. Initialize constants:  
   - `Gr = 400`  
   - `λ = 0.025`  
   - `σ = 25`  
   - `Pm = 1e-12`  
   - `Gt = 4000`  
4. Vary `Pt = 0:1:10` → Compute `Rmax1`.  
5. Vary `Gt1 = 100:100:10000`, set `Pt1 = 10` → Compute `Rmax2`.  
6. Vary `Pm1 = logspace(-15, -9, 100)`, set `Pt2 = 10`, `Gt2 = 4000` → Compute `Rmax3`.  
7. Plot results in subplots:  
   - `Rmax1` vs `Pt` (red)  
   - `Rmax2` vs `Gt1` (blue)  
   - `Rmax3` vs `Pm1` (green)  
8. End the program.


## Procedure

1. **Refer to the Algorithm** and write the Scilab code for the experiment.  
2. **Open Scilab** on your system.  
3. **Create a New Editor File:**  
   - Go to `File → New → Script`.  
4. **Type Your Code** in the editor window.  
5. **Save the File** with a suitable name (e.g., `radar_range.sce`).  
6. **Execute the Code:**  
   - Press **F5** or click **Execute → File with echo**.  
7. **If Any Errors Occur:**  
   - Review and correct the code.  
   - Save and **run it again** until it executes successfully.

---

##  Code 
```scilab
clc;
clear;
close;
Gr = 400;           
l = 0.025;          
sigma = 25;   
      
Pm= 1e-12;       
Gt = 4000;         
Pt = 0:1:10;  
Rmax1 = ((Pt .* Gt .* Gr .* l^2 .* sigma) ./ ((4*%pi)^2 .* Pm)).^(1/4);

Gt1 = 100:100:10000; 
Pt1 = 10;           
 
Rmax2 = ((Pt1 .* Gt1 .* Gr .* l^2 .* sigma) ./ ((4*%pi)^2 .* Pm)).^(1/4);

Pm1 = logspace(-15, -9, 100); 
Pt2 = 10;                       
Gt2 = 4000;  
                   
Rmax3 = ((Pt2 .* Gt2 .* Gr .* l^2 .* sigma) ./ ((4*%pi)^2 .* Pm1)).^(1/4);
subplot(3,1,1);
plot(Pt, Rmax1, 'r');

subplot(3,1,2);
plot(Gt1, Rmax2, 'b');

subplot(3,1,3);
plot(Pm1, Rmax3, 'g');




```

## Output




## Manual Calculation




## Result

Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.
