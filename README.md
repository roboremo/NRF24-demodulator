# NRF24-demodulator
Sniff NRF24L01 (and clones) packets and veiw bit-level structure using GNU Radio.  
GRC flow inspired from here: https://wiki.bitcraze.io/misc:hacks:hackrf  
  
# Hardware setup
Have a NRF24L01+ sending something on channel 80 (2480MHz), at 1Mbps  
The RF signal is picked-up using a MMDS down converter (I use one with LO = 1838MHz and input frequency 2500 to 2700MHz) and is converted to 642MHz  
The 642MHz signal goes to a SDR dongle (820T2), and the GRC reads it.  
The MMDS down converter is powered using 12V DC (see powering-MMDS-down-converter.JPG for details)  
  
# Software setup
After the hardware is ready, open the GRC file  
Change the downconverter_lo and nrf_channel if needed  
Click execute
The scope should appear on screen. Go to Channel Options -> Trig and increase the trigger level by clicking on +, then move T Offset to the right  
Now you should see something like ...
