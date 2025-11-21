# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
//HPF
```
clc;
clear;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency (in radians) = ');

alpha = (M - 1) / 2; // Center value

// Ideal High Pass filter coefficients
for n = 1:M
    if (n == alpha + 1) then
        hd(n) = 1 - (Wc / %pi);
    else
        hd(n) = -sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
    end
end

// Rectangular Window
for n = 1:M
    W(n) = 1;
end

// Apply window to ideal filter
h = hd .* W;
disp(h, 'Filter Coefficients are:');

// Frequency response
[hzm, fr] = frmag(h, 256);

subplot(2, 1, 1);
plot(2 * fr, hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Rectangular Window');

hzm_dB = 20 * log10(hzm);
subplot(2, 1, 2);
plot(2 * fr, hzm_dB);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude (dB)');
title('Frequency Response of FIR HPF using Rectangular Window');
```
//LPF
```
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha= (M -1)/2 // Center Value
for n = 1:M
if (n ==alpha+1)
hd(n) = Wc/ %pi ;
else
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);
end
end
for n = 1:M
W(n) = 1;
end
h = hd.*W;
disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR LPF using Rectangular Window ')
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR LPF using Rectangular Window');
```

# OUTPUT

<img width="841" height="628" alt="image" src="https://github.com/user-attachments/assets/f7f7da7b-291b-4334-8ff0-489ae27d6411" />

<img width="841" height="628" alt="image" src="https://github.com/user-attachments/assets/8c6a4a46-8671-48f6-b33d-00052aff9f2a" />

<img width="691" height="576" alt="image" src="https://github.com/user-attachments/assets/c3061456-07d3-4089-b525-296518c6656b" />

<img width="691" height="576" alt="image" src="https://github.com/user-attachments/assets/4b27cf64-9f57-4a40-8bab-f87ccb275108" />

# RESULT
The design of low pass fir digital filter is successfully completed using scilab
