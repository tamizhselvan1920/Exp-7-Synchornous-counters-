# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
/* write all the steps invloved */



### PROGRAM
```
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: tamizh selvan.R
RegisterNumber:  212222230158
*/
# UP COUNTER:


module UC(input CLK,input reset,output[0:3]counter);
reg[0:3]counter_up;
always@(posedge CLK or posedge reset)
begin 
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule


# DOWN COUNTER:

module DC(input CLK,input reset,output[0:3]counter);
reg[0:3]counter_down;
always@(posedge CLK or posedge reset)
begin 
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule




```
### RTL LOGIC UP COUNTER AND DOWN COUNTER  
 ### UP COUNTER


<img width="1130" alt="169742530-572d815d-582f-49eb-9a0e-3fafd037b889" src="https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/8e61d27c-a6c2-40f0-96a2-cf89f493a270">


### DOWN COUNTER

<img width="990" alt="169742545-8cf6aea9-42d7-4ab7-b66d-9cca69d5c359" src="https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/1c906053-28a7-4f94-b0ce-e82709002bbc">






### TIMING DIGRAMS FOR COUNTER  

 ### UP COUNTER
![169742560-7239a387-9f5b-4068-87a1-57760c65ae84](https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/3be0b94b-3460-4969-8dfd-a213369aff34)


### DOWN COUNTER



![169742567-caf75d78-ebc9-4d18-995f-8d64b3194606](https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/ce68c50e-15aa-4f58-99f3-a777c54f805d)





### TRUTH TABLE 

### UP COUNTER




<img width="860" alt="169742597-a9bac2cb-65f7-452c-b253-651e4184a1c1" src="https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/4d7ace29-b4e5-4c08-a6bb-e55259b1fada">


### DOWN COUNTER

<img width="860" alt="169742615-86947d04-d1a5-4612-84fc-1aa502f5d2dc" src="https://github.com/tamizhselvan1920/Exp-7-Synchornous-counters-/assets/121148386/35effdc3-e7b8-485b-baf0-ab1993223633">






### RESULTS 

The 4 bit up and down counters has been implemented and validated the functionality.






