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
clear all; % clear screen
close all; % close all figure windows
wc1=input('enter the value of wc1');
wc2=input('enter the value of wc2');
N=input('enter the value of filter');
alpha=(N-1)/2;
eps=0.001;
%Band Stop Filter Coefficient 
n=0:1:N-1;
hd=(sin(pi*(n-alpha+eps))-sin((n-alpha+eps)*wc1)+sin((n-alpha+eps)*wc2))./(pi*(n-alpha+eps)) 
%Hamming Window Sequence
n=0:1:N-1;
wh=0.5-0.5*cos((2*pi*n)/(N-1))
hn=hd.*wh
% Plot the Low Pass Filter with Hamming Window Technique
w=0:0.01:pi;
h=freqz(hn,1,w);
plot(w/pi,abs(h),'blue');

~~~
## OUTPUT:

<img width="1629" height="868" alt="image" src="https://github.com/user-attachments/assets/2ab16866-e38f-489d-9777-b3ee79cea5f0" />

## RESULT:

Thus the design of Band pass FIR digital filter using Hanning waveforms were plotted and 
output was verified. 
