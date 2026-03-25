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

clc;            % Clear command window
clear all;      % Clear workspace
close all;      % Close all figures

wc1 = input('Enter lower cutoff frequency wc1 = ');
wc2 = input('Enter upper cutoff frequency wc2 = ');
N = input('Enter the value of N = ');

alpha = (N-1)/2;
eps = 1e-6;     % Small value to avoid division by zero

n = 0:N-1;

% Ideal Band Pass Filter impulse response
hd = (sin(wc2*(n-alpha+eps)) - sin(wc1*(n-alpha+eps))) ./ (pi*(n-alpha+eps));

% Hanning Window
wh = 0.5 - 0.5*cos((2*pi*n)/(N-1));

% Final impulse response
hn = hd .* wh;

% Frequency response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'b');
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('Magnitude');
title('Band Pass FIR Filter using Hanning Window');
grid on;

~~~
## OUTPUT:

<img width="1624" height="870" alt="Screenshot 2026-03-25 200405" src="https://github.com/user-attachments/assets/9fcbcb89-b2ad-49b6-b5fd-099927274bb1" />

## RESULT:

Thus the design of Band pass FIR digital filter using Hanning waveforms were plotted and 
output was verified. 
