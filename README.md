
# EXP 2 : COMPUTATION OF DFT USING DIRECT DFT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
```
clc;
clear;
xn=[1 2 3 4 4 3 2 1];
n1=0:1:length(xn)-1;
subplot(3,1,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude xn');
title('Input Sequence');
j=sqrt(-1);
N=length(xn);
Xk=zeros(1,N);
    for k=0:N-1;
    for n=0:N-1;  
    Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
    end
end
disp(Xk)
K1=0:1:length(Xk)-1;
magnitude=abs(Xk)
subplot(3,1,2);
plot2d3(K1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle=atan(imag(Xk),real(Xk))
subplot(3,1,3);
plot2d3(K1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('Phase spectrum');
```
// FAST FOURIER TRANSFORM
```
clear;
clc;
close all;
xn = [1 2 3 4 4 3 2 1];
n1 = 0:1:length(xn)-1;
subplot(2,2,1);
plot2d3(n1, xn);
xlabel('Time n');
ylabel('Amplitude');
title('Input Sequence');
Xk = fft(xn);
K1 = 0:1:length(Xk)-1;
magnitude = abs(Xk);
subplot(2,2,2);
plot2d3(K1, magnitude);
xlabel('Frequency (Hz)');
ylabel('Magnitude (gain)');
title('Magnitude Spectrum');
angle = atan2(imag(Xk), real(Xk));
subplot(2,2,3);
plot2d3(K1, angle);
xlabel('Frequency (Hz)');
ylabel('Phase');
title('Phase Spectrum');
y = ifft(Xk);
n2 = 0:1:length(y)-1;
subplot(2,2,4);
plot2d3(n2, y);
xlabel('Time n');
ylabel('Amplitude');
title('Inverse FFT of X(k)');
```
# CALCULATIONS: 

// DISCRETE FOURIER TRANSFORM 

<img width="705" height="1280" alt="image" src="https://github.com/user-attachments/assets/46fc8f77-7974-45b0-beee-6f2eee00719f" />
<img width="735" height="1280" alt="image" src="https://github.com/user-attachments/assets/31eba1cf-ff06-4e17-9248-06485c3c082e" />
<img width="706" height="1280" alt="image" src="https://github.com/user-attachments/assets/f6e2535b-31fd-4daf-b2b8-864fba2c1fdc" />




// FAST FOURIER TRANSFORM 

<img width="730" height="1280" alt="image" src="https://github.com/user-attachments/assets/c4ad607a-1083-483e-886e-6a0b6ed8decf" />
<img width="783" height="1280" alt="image" src="https://github.com/user-attachments/assets/e9aa63e6-127e-47f5-995e-2d14e2fdcec3" />




# SAMPLE OUTPUT: 

// DISCRETE FOURIER TRANSFORM 

<img width="756" height="715" alt="DFT dtsp" src="https://github.com/user-attachments/assets/aa0c7ff0-4927-4c84-8242-654cbe473753" />

// FAST FOURIER TRANSFORM 

<img width="876" height="697" alt="DFT using FFT" src="https://github.com/user-attachments/assets/79c7d5f1-7c8b-4090-bf88-1d75724fd0f1" />

# RESULT: 

Thus, the Discrete Fourier Transform and Fast Fourier Transform of the given sequence were    obtained 
and its magnitude and phase spectrum were plotted.
