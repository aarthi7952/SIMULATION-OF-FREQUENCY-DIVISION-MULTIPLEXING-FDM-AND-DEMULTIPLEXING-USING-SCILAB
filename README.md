# SIMULATION-OF-FREQUENCY-DIVISION-MULTIPLEXING-FDM-AND-DEMULTIPLEXING-USING-SCILAB
## AIM:

To write a Scilab program to simulate frequency division multiplexing and demultiplexing for six different frequencies, and verify the demultiplexed outputs correspond to the original signals.

## EQUIPMENTS Needed

Computer with Scilab installed

## ALGORITHM

1.Define six different frequencies to generate six sine wave signals.
2.Generate the time vector to represent time samples.
3.Compute six sine signals for each frequency over the time vector.
4.Frequency Division Multiplexing: sum all six sine signals to make one multiplexed signal.
5.Frequency Division Demultiplexing: for each frequency, multiply the multiplexed signal by a sine wave of that frequency (mixing), then apply a lowpass filter to extract the baseband (original) signal.
6.Plot original signals, multiplexed signal, and demultiplexed signals for verification.

## PROCEDURE

Refer Algorithms and write code for the experiment.
• Open SCILAB in System
• Type your code in New Editor
• Save the file
• Execute the code
• If any Error, correct it in code and execute again
• Verify the generated waveform using Tabulation and Model Waveform

## PROGRAM:
```
fs = 10000; 
t=0:1/fs:0.01-1/fs; 
// Frequencies 
f = [300 400 500 600 700]; 
 
// Generate 5 signals 
m1 = sin(2 * %pi * f(1) * t); 
m2 = sin(2 * %pi * f(2) * t); 
m3 = sin(2 * %pi * f(3) * t); 
m4 = sin(2 * %pi * f(4) * t); 
m5 = sin(2 * %pi * f(5) * t); 
 
// Plot message signals 
scf(0); 
subplot(5,1,1); plot(t, m1); title("Message Signal 1"); 
subplot(5,1,2); plot(t, m2); title("Message Signal 2"); 
subplot(5,1,3); plot(t, m3); title("Message Signal 3"); 
subplot(5,1,4); plot(t, m4); title("Message Signal 4"); 
subplot(5,1,5); plot(t, m5); title("Message Signal 5"); 
 
// TDM modulation 
tdm = zeros(1, 5 * length(t)); 
for i = 1:length(t) 
    tdm(5*(i-1)+1) = m1(i); 
    tdm(5*(i-1)+2) = m2(i); 
    tdm(5*(i-1)+3) = m3(i); 
    tdm(5*(i-1)+4) = m4(i); 
    tdm(5*(i-1)+5) = m5(i); 
end 
 
// Time vector for TDM 
tdm_t = 0:1/fs:(length(tdm)-1)/fs; 
 
// Plot TDM 
scf(1); 
plot(tdm_t, tdm, 'm'); 
title("TDM Modulated Signal"); 
xlabel("Time"); 
ylabel("Amplitude"); 
xgrid(); 
 
// Demodulate 
m1_d = tdm(1:5:$); 
m2_d = tdm(2:5:$); 
m3_d = tdm(3:5:$); 
m4_d = tdm(4:5:$); 
m5_d = tdm(5:5:$); 
 
// Plot demodulated 
scf(2); 
subplot(5,1,1); plot(t, m1_d); title("Demodulated Signal 1"); 
subplot(5,1,2); plot(t, m2_d); title("Demodulated Signal 2"); 
subplot(5,1,3); plot(t, m3_d); title("Demodulated Signal 3"); 
subplot(5,1,4); plot(t, m4_d); title("Demodulated Signal 4"); 
subplot(5,1,5); plot(t, m5_d); title("DemodulatedSignal 5");
```

## TABULATION:
<img width="781" height="487" alt="516871368-35760e4c-8e6e-450f-9d9b-8e60f5627106" src="https://github.com/user-attachments/assets/1962a6ff-538e-4bb2-b07f-220ddb4951cf" />

## GRAPH:
<img width="783" height="442" alt="516871457-25b8331d-70d3-4f90-a649-618b037c8261" src="https://github.com/user-attachments/assets/c5c621cd-57e4-4cd0-b421-b74a0aea7360" />
<img width="796" height="547" alt="516871609-1001729e-13fb-41de-9ebe-c5164f0123d9" src="https://github.com/user-attachments/assets/a44dee0c-c0cc-40eb-a71c-9d431610f990" />

## RESULT:
Thus, the time division multiplexing is done experimentally and the output is verified.
