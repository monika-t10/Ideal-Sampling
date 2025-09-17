# Ideal, Natural, & Flat-top -Sampling
# Aim
Write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
google collab
# Program
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample

fs = 100
t = np.arange(0, 1, 1/fs)
f = 5
signal = np.sin(2 * np.pi * f * t)

# Plot continuous signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Sampling
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)

plt.figure(figsize=(10, 4))
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstruction using resample
reconstructed_signal = resample(signal_sampled, len(t))

plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Original Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

```
# Output Waveform
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/0c23a86a-503b-4b21-94db-b08c648c8b86" />
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/0a6e6981-62b6-4d47-9cee-b707609875a1" />
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/87e6329b-ffb0-4778-9393-2f80ae8dfbdd" />



# Results
Thus the code is successfully executed.
