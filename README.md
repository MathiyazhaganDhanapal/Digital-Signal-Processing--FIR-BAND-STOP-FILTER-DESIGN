# Digital-Signal-Processing--FIR-BAND-STOP-FILTER-DESIGN
## AIM:
To generate design of Band Stop FIR digital filter using Hanning Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Stop filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
~~~

clc; % clear screen 
clear all; % clear workspace 
close all; % close all figure windows 

Wc1=input('enter the value of Wc1=');  
Wc2=input('enter the value of Wc2=');  
N=input('enter the value of N='); 

alpha=(N-1)/2;  
eps=0.001;  

% Band stop Filter Coefficient 
n=0:1:N-1;  
hd=(sin(pi*(n-alpha+eps)) - sin((n-alpha+eps)*Wc2) + sin((n-alpha+eps)*Wc1))./(pi*(n-alpha+eps));

% Bartlett Window Sequence  
n=0:1:N-1;  
wh=1 - 2*abs(n-alpha)/(N-1);  

% Final impulse response
hn=hd.*wh;  

% Plot the Band stop Filter with Bartlett Window Technique 
w=0:0.01:pi;  
h=freqz(hn,1,w); 

plot(w/pi,abs(h),'b');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Stop FIR Filter using Bartlett Window');
grid on;

~~~
## OUTPUT:

<img width="1630" height="886" alt="Screenshot 2026-03-29 101013" src="https://github.com/user-attachments/assets/2e0b3b26-cf2d-4654-9192-b5f5e5b12678" />

## RESULT:

![WhatsApp Image 2026-03-30 at 2 21 22 PM (4)](https://github.com/user-attachments/assets/7a0eed64-8893-4917-afa0-8b019174a415)
