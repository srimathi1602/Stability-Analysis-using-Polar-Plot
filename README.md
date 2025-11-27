# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
Stability analysis using a polar plot in MATLAB examines how the system’s frequency response encircles the critical point ((-1,0)) based on the Nyquist stability criterion. If the polar plot does not encircle the ((-1,0)) point for an open-loop stable system, the closed-loop system is considered stable.

![WhatsApp Image 2025-11-27 at 21 40 28_a8f93bbb](https://github.com/user-attachments/assets/5a48aae3-d1c7-4188-8e2a-b3393aede89c)
![WhatsApp Image 2025-11-27 at 21 41 05_5ce43cab](https://github.com/user-attachments/assets/1e4ab139-b778-49b2-981c-04a6283de91c)
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/9e71bbd6-b039-4d8f-9eae-96359e90ce51" />


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="813" height="716" alt="Screenshot 2025-11-24 180519" src="https://github.com/user-attachments/assets/7491bf95-6330-4331-a9c7-b7f1708f9548" />

## Result:
```
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.
Gain margin = 0.7
Phase Margin = -8.8865
Gain crossover frequency = 3.7565
Phase crossover frequency = 3.1623
The system is unstable
```
