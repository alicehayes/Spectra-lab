# Spectra-lab
This is code for converting raw .csv files of power and spectra data gathered from my radio telescope into useful plots and speed calculations.
# The Telescope
pictures of telescope: https://imgur.com/gallery/YVTq2lO

This is a home built radio telescope with a 1.5 meter dish constructed out of bamboo. This telescope easily picks up the galactic hydrogen line (https://en.wikipedia.org/wiki/Hydrogen_line) and records it. I use a rtl-sdr software defined radio usb dongle connected to a raspberry pi to collect the data using https://github.com/0xCoto/Virgo setup to shift frequencies periodically to calibrate the data. Astro virgo outputs individual power, spectra, and plots which I then further process to extract useful data. Two important pieces of data can be calculated using this information: the amount of hydrogen in that part of the sky, and how fast that hydrogen is moving relative to earth. The speed is calculated using the difference between the observed frequency of the hydrogen line and the frequency of the emitted hydrogen line. Further information about calculating speed can be found here: https://en.wikipedia.org/wiki/Redshift, and here: https://en.wikipedia.org/wiki/Relativistic_Doppler_effect.
# The Data
The examples folder contains both the raw data from the telescope and the outputs this code produces for a representative period. The pwr and spectra folders hold the raw data from the telescope. The plot folder holds the plots output by astro virgo. The 290x69-spectra.csv is the joined version of all of the spectra files for this 24 hour period. Note the 290x69-spectra.csv and 290x69-data.csv files contain data for which I did not include plots or individual files. The 290x69-data.csv file includes the detected peak frequency, the speed of relative motion of the hydrogen source in meters per second (negative is towards earth, positive is away), and the relative power of the signal (does not have strict units but is helpful for understanding the comparative signal strength across locations). The python-plots folder contains matplotlib figures that visualize the data, the detected peak, and the processed data used to detect it.