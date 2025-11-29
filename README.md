# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-16 at 22 37 12_e7beb8e8](https://github.com/user-attachments/assets/2315d4fc-42c1-4697-a5b2-3e96de13ba1f)

![WhatsApp Image 2025-11-16 at 22 37 12_5232775e](https://github.com/user-attachments/assets/7c8114ac-53ce-4502-9187-c168c8e28a64)




## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
![WhatsApp Image 2025-11-29 at 13 57 45_531a9057](https://github.com/user-attachments/assets/acf3d62c-c2bf-47e4-ac29-4bb672ba168e)


## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = -23.10 db<br>
Phase Margin = -50.48 degree<br>
Gain crossover frequency = 0.9534 rad/s<br>
Phase crossover frequency =0.3162 rad/s <br>
The system is  ------------
