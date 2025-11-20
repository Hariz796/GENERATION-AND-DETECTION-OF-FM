# GENERATION-AND-DETECTION-OF-FM
## AIM:
To write a program for Frequency Modulation and Demodulation using SCILAB and to observe and measure the frequency deviation and the modulation index of FM.

## EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

## THEORY
  Frequency modulation is a type of modulation in which the frequency of the high frequency (carrier) is varied in accordance with the instantaneous value of the modulating signal.
  
  #### FREQUENCY DEVIATION Δf  and MODULATION INDEX m f :
  
  The frequency deviation Δf represents the maximum shift between the  modulated signal
  frequency, over and under the frequency of the carrier.
  
  We define modulation index m f the ratio between Δf and the modulating frequency
  m= Δf / fm


#### FREQUENCY MODULATION GENERATION:
  The circuits used to generate a frequency modulation must vary the frequency of a high frequency signal (carrier) as function of the amplitude of a low frequency signal (modulating signal). In practice there are two main methods used to generate FM.

## ALGORITHM
  1.	Define Parameters:
     
      •	Fs: Sampling frequency.
      •	T: Duration of the signal.
      •	Fc: Carrier frequency.
      •	Fm: Frequency of the modulating signal.
      •	Beta: Modulation index, which controls the extent of frequency deviation.
  2.	Generate Signals:
     
      •	modulating_signal: Sinusoidal signal used for modulation.
      •	carrier_signal: The high-frequency carrier signal.
      •	modulated_signal: FM modulated signal calculated by varying the carrier frequency according to the modulating signal.
      
  3.	FM Modulation:
     
      •	Modulated_signal is obtained by modulating the carrier signal with the modulating signal.
 
  4.	FM Demodulation:
     
      •	Differentiation: Computes the derivative of the modulated signal to extract frequency variations.
      •	Envelope Detection: Takes the absolute value to retrieve the envelope of the signal.
      •	Low-pass Filtering: Applies a Butterworth low-pass filter to smooth the envelope and recover the original modulating signal.
      
  5.	Visualization:
      
      •	Plots the modulating signal, carrier signal, FM modulated signal, and demodulated signal for analysis.


## PROCEDURE

    •	Refer Algorithms and write code for the experiment.
    •	Open SCILAB in System
    •	Type your code in New Editor
    •	Save the file
    •	Execute the code
    •	If any Error, correct it in code and execute again
    Verify the generated waveform using Tabulation and Model Waveform

## MODEL GRAPH:
<img width="512" height="365" alt="image" src="https://github.com/user-attachments/assets/dfe6bc64-2b6f-4afa-ae79-95391859ab04" />

## PROGRAM
```
Am = 6.7;
fm = 537;
fs = 537000;
Ac = 13.4;
fc = 5370;
b = 5; 
t = 0:1/fs:2/fm;
m = Am * cos(2 * 3.14 * fm * t);
subplot(4,1,1);
plot(t, m);
title('Message Signal');
xlabel('Time (s)');
ylabel('Amplitude');
c = Ac * cos(2 * 3.14 * fc * t);
subplot(4,1,2);
plot(t, c);
title('Carrier Signal');
xlabel('Time (s)');
ylabel('Amplitude');
s = Ac * cos(2 * 3.14 * fc * t + b * sin(2 * 3.14 * fm * t));
subplot(4,1,3);
plot(t, s);
title('FM Modulated Signal');
xlabel('Time (s)');
ylabel('Amplitude');
demod = 10*abs(diff(s)); 
demod = demod * (Am / max(demod));
N = 255;                      
h = ones(1, N) / N;           
demod = conv(demod, h, 'same'); 
demod = demod - mean(demod);        
demod = demod * (Am / max(abs(demod)));       
t_demod = t(1:length(demod));
subplot(4,1,4);
plot(t_demod, demod);
title('Demodulated Signal');
xlabel('Time (s)');
ylabel('Amplitude');

```
## TABULATION
![WhatsApp Image 2025-11-20 at 18 31 56_325a30d2](https://github.com/user-attachments/assets/3f2599d9-4f32-4107-b98b-174d9687b942)


## CALCULATION
![WhatsApp Image 2025-11-20 at 18 32 48_3c4fccb4](https://github.com/user-attachments/assets/9457ba38-26a2-40c2-b1df-082e0ae8b088)


## OUTPUT
<img width="393" height="349" alt="image" src="https://github.com/user-attachments/assets/8420d40c-406d-4ad5-bce0-bb999b9cd284" />


## RESULT
Thus, the Frequency Modulation and Demodulation is successfully done and the output is experimentally verified.


