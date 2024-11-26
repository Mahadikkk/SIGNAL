Design of Low Pass IIR Filter using Bilinear Transformation Technique.

clc; 
close all; 
clear all; 
alphap=input('maximum passband attenuation in db = '); 
alphas=input('minimum Stopband attenuation in db =') ; 
wpn=input(' passband edge frequency in rad = '); 
wsn = input(' stopband edge frequency in rad = '); 
[N,wc] =buttord(wpn,wsn,alphap,alphas,'s'); 
[b,a] =butter(N,wc,'s'); 
[bz,az]=bilinear(b,a,50); 
subplot(2,1,1) 
[y,w] =freqz(bz,az); 
plot(w/pi,abs(y)); 
xlabel(" Normalized Frequency "); 
ylabel("Magnitude");





