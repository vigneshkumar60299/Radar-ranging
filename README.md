# EVALUATION OF RADAR RANGE USING PYTHON

## Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

## Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:


<img width="457" height="528" alt="image" src="https://github.com/user-attachments/assets/114f1b0f-bf00-48db-be01-3f65d10e7dda" />



## Procedure
1.	Set Up the Python Environment: Ensure that Python is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2.	Import Necessary Libraries: Import the math library in Python.
3.	Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4.	Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power.
5.	Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6.	Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


## PROGRAM
```
lambda = 0.03;
sigma  = 1;

Pt_vals = [320 280 240 200 160];
Gt_const = 35;
Pm_const = 1e-13;

Rmax_Pt = ((Pt_vals .* (Gt_const.^2) .* (lambda.^2) .* sigma) ./ (((4*%pi).^3) .* Pm_const)).^(1/4);

Gt_vals  = [10 20 30 40 50];
Pt_const = 2;
Pm_const = 1e-13;

Rmax_Gt = ((Pt_const .* (Gt_vals.^2) .* (lambda.^2) .* sigma) ./ (((4*%pi).^3) .* Pm_const)).^(1/4);

Pm_vals  = [1e-15 5e-15 1e-14 5e-14 1e-13];
Pt_const = 2;
Gt_const = 35;

Rmax_Pm = ((Pt_const .* (Gt_const.^2) .* (lambda.^2) .* sigma) ./ (((4*%pi).^3) .* Pm_vals)).^(1/4);

clf();

subplot(3,1,1);
plot(Pt_vals, Rmax_Pt, 'r', 'LineWidth', 2);


subplot(3,1,2);
plot(Gt_vals, Rmax_Gt, 'g', 'LineWidth', 2);


subplot(3,1,3);
plot(Pm_vals, Rmax_Pm, 'b', 'LineWidth', 2);

disp("Pt variation  ->  [Pt , Rmax]");
disp([Pt_vals'  Rmax_Pt']);

disp("Gt variation  ->  [Gt , Rmax]");
disp([Gt_vals'  Rmax_Gt']);

disp("Pm variation  ->  [Pm , Rmax]");
disp([Pm_vals'  Rmax_Pm']);
```
## TABULATION
![WhatsApp Image 2025-12-04 at 12 24 25_c2142148](https://github.com/user-attachments/assets/09ab782f-ea60-4119-8020-9fad2adde002)





Result:
<img width="1919" height="928" alt="Screenshot 2025-12-04 123044" src="https://github.com/user-attachments/assets/8ecf693f-6328-4ab6-8675-c0c00920b057" />




Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Python program.

