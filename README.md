# Blackbeard-Technologies-dstask

**Understanding the data:**

The Dataset contained EEG signals from a Sleep Study. This data was used by experts to assess the Sleep Stage the Subject was experiencing.
Each **PSG-EDF* file contains signal data from multiple sensors such EEG, EMG, EOG, Temperature etc. The **Hypnogram-EDF file contained the annotations of the experts marking events and the Sleep Stages identified.

**Preprocessing:**

For Preprocessing I have used a Band Pass filter which was part of the mne library ( built to handle EEG singal DATA ). I used this library to create a band pass region between 0.25 hertz to 10 hertz and attenuated all other frequencies. I have used a lower freq of 0.25 since the low frequency drift seen after plotting the channels has a frequency of 0.1 hertz and the filter needs to attenuate regions of frequencies lower than  0.1 hz. I have attenuated Signals Higher than 10 Hertz since they are usually caused by irregularities in the electrodes

Documentation Referred to for MNE filtering:

https://mne.tools/stable/auto_tutorials/preprocessing/25_background_filtering.html

https://mne.tools/stable/auto_tutorials/preprocessing/30_filtering_resampling.html

**Visulaizing the Data and Plotting It:**

For data visulaization i have used the inbuilt plot functions of the raw object created using MNE when reeading EDF files. This has allowed me to select certain sections of the signal data as well as add annotations to demarcate the different Sleep Stages visually. It has also allowed me to overlay the various sensor data which reside on different channels onto the same plot. Individual Scalings for each of the channels has been used to allow all plots to be seen simultaneously

Documentation Referred to for Visualization Tools:

https://mne.tools/stable/auto_tutorials/raw/40_visualize_raw.html

https://mne.tools/stable/auto_tutorials/evoked/20_visualize_evoked.html

https://mne.tools/stable/auto_tutorials/epochs/20_visualize_epochs.html

![image](https://user-images.githubusercontent.com/43317025/136463672-b0a2aa77-e28a-444c-9e4b-6b487f4926eb.png)


**Fast Fourier Transform:**

For implementing the fft i have extracted teh raw eeg channel data from the raw data structure and passed it to the scipy.fft module to convert the signal tot the frequency domain. I have then used pyplot module to plot the graphs using the absolute vaule of the complex valued frequencies

Documentation Referred to for FFT Implementation:

https://mne.tools/stable/auto_tutorials/raw/10_raw_overview.html

https://docs.scipy.org/doc/scipy/reference/tutorial/fft.html

https://realpython.com/python-scipy-fft/

![image](https://user-images.githubusercontent.com/43317025/136463785-9103f757-8680-48d8-b48c-8d665da542de.png)

**DeepSleepNet Model:**
 Using the github Implementaiton of the model I was able to Train the Model and Use it to the Predict on the validation set. It was done using python Scripts and Data Downloaded Externally
 
 Documentation Referred to for DeepSleepNet Model:
 
 https://github.com/akaraspt/deepsleepnet
 
 https://mne.tools/stable/auto_tutorials/clinical/60_sleep.html
