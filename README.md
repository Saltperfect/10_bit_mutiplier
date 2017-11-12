# 10_bit_mutiplier
This is a structural implemetntation of 10 bit multiplier in vhdl
The whole circuit is syncronous. There are 5 states defined in the whole process.
The first is RESET or IDLE. This state is the reset state in which the machine doesn't do anything. 
The next state is LOAD state where the multiplicand gets loaded in the multiplicand register and the multiplier gets loaded in the temp_register the multiplier_result module.
The next state from there is TEST or CHECK state in which the LSB of Multiplier is checked and according the furthur process is done. 
If LSB is 0 then the Shift command is generate and simply the shifting of the current result takes place as in the multiplication of two binary numbers and if LSB is 1 then the shifted result is fed to the 10 bit adder which adds the multiplicand to it via ADD_cmd and the out is stored in the temp_register by shifting it with one so as in each succsesive check state, 10 checking we would cover the 10 bits of multiplier.
One counter is also placed so that we can count the number of times we have reached the check state.
After the counting to 10 is complete then we will send our machine to idle state and give a stop command to indicate completion as well as our out will be parallely exited. 
