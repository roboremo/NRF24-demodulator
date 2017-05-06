# NRF24-demodulator
Sniff NRF24L01 (and clones) packets and view bit-level structure using GNU Radio.  
GRC flow inspired from here: https://wiki.bitcraze.io/misc:hacks:hackrf  
  
## Hardware setup  
Inspired from http://blog.cyberexplorer.me/2014/01/sniffing-and-decoding-nrf24l01-and.html  
Have a NRF24L01+ sending something on channel 80 (2480MHz), at 1Mbps  
The RF signal is picked-up using a MMDS down converter  
(I use one with LO = 1838MHz and input frequency 2500 to 2700MHz)  
The resulting frequency is 642MHz  
The 642MHz signal goes to a SDR dongle (820T2), and the GRC reads it.  
The MMDS down converter is powered using 12V DC  
![MMDS powering diagram](https://raw.githubusercontent.com/roboremo/NRF24-demodulator/master/powering-MMDS-down-converter.JPG "MMDS powering diagram")
  
## Software setup
After the hardware is ready, open the GRC file  
Change the downconverter_lo and nrf_channel if needed  
Click execute  
The scope should appear on screen.  
Go to Channel Options -> Trig and increase the trigger level by clicking on +  
Then move T Offset to the right  
Now you should see something like this:  
![NRF24L01 packet waveform](https://raw.githubusercontent.com/roboremo/NRF24-demodulator/master/NRF24L01p-1Mbps-addr-0x0000000000-payload-0x414243-DPL-noCRC.JPG "NRF24L01 packet waveform")  
  
Related project:  
https://github.com/roboremo/NRF24-total-control
