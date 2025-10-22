# EVALUATION OF RADAR RANGE USING PYTHON

Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:


<img width="457" height="528" alt="image" src="https://github.com/user-attachments/assets/114f1b0f-bf00-48db-be01-3f65d10e7dda" />



Procedure
1.	Set Up the Python Environment: Ensure that Python is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2.	Import Necessary Libraries: Import the math library in Python.
3.	Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4.	Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power.
5.	Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6.	Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


PROGRAM
c = 3e8;  
f = 10e9;  
lambda = c / f;  
sigma = 1;  
L = 1;  
G_dB = 30;  
G = 10^(G_dB/10);  
Pt = 1e3;  
R = linspace(1e2, 1e5, 500);  
Pr_range = (Pt * G^2 * lambda^2 * sigma) ./ ((4 * %pi)^3 * R.^4 * L);  
Pt_array = linspace(1, 1e5, 500);  
R_fixed = 1e4;  
Pr_pt = (Pt_array * G^2 * lambda^2 * sigma) ./ ((4 * %pi)^3 * R_fixed^4 * L);  
G_dB_array = linspace(0, 50, 500);   
G_array = 10.^(G_dB_array / 10);  
Pr_gain = (Pt * G_array.^2 * lambda^2 * sigma) ./ ((4 * %pi)^3 * R_fixed^4 * L);  
subplot(3,1,1);  
plot(R/1000, 10*log10(Pr_range));  
subplot(3,1,2);  
plot(10*log10(Pt_array), 10*log10(Pr_pt));  
subplot(3,1,3);  
plot(G_dB_array, 10*log10(Pr_gain));  


Result:
<img width="1919" height="930" alt="Screenshot 2025-10-22 160007" src="https://github.com/user-attachments/assets/d7c26355-312a-4e12-bf5f-8b1d79decfc4" />



Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Python program.

