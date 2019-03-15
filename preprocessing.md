***
This document covers functions and programs in the `programs` folder for preprocessing the model inputs, including the following topics 

* Shadow

* MakeChannelState

* (to be continued)

  

## Shadow

The `monthly_shadow_bin.scr`generates two sets of monthly shadow file by default: `Shadow.xx.bin`and `Shadow.xx.hourly.bin` , which are shadow files for 3-hourly and hourly time step correspondingly. 

* **How to change shadow file from 3-hour time step to hourly time step? **

When changing model run timestep, you'll need to change corresponding shadow map time step. Use "hourly.bin" for "Shading data extension" option in the configuration file.

* **Is it possible to use timestep other than hourly or 3-hourly?**

Yes. Open `monthly_shadow_bin.scr`in a text editor and find the following command line

`./average_shadow $outpath/Shadow.$mon.hourly.bin $outpath/Shadow.$mon.bin 24 8 $rows $cols`

change it to 

`./average_shadow $outpath/Shadow.$mon.hourly.bin $outpath/Shadow.$mon.bin 24 X $rows $cols`

where X = 24 / new_timestep, for example X = 8 for 3hourly timestep. 



### MakeChannelState

* **Error message "-bash: ./MakeChannelState.scr: /bin/tcsh: bad interpreter: No such file or directory"**

  This error message is likely to occur if you're using Cygwin on Win machine. Try "tcsh ./Make..." first and if it doesn't work it probably means you did not have the shell "tcsh" installed. To check if you have the shell, type `which tcsh`. Use your Cygwin installer to install "tcsh" as needed.



