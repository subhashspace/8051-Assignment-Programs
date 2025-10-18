# SQUARE WAVE ASSEMBLY

### AIM
Write a 8051 assembly language program to generate a square wave with frequency of 50khz

### APPARATUS REQUIRED
- Personal Computer
- Keil µVision Software

### PROGRAM
```asm
CLR  P1.0          
MOV  TMOD, #01H    
AGAIN:
 MOV  TL0, #0F7H  
MOV  TH0, #0FFH   
CPL  P1.0         
SETB TR0          
WAIT:
 JNB  TF0, WAIT    
CLR  TR0          
CLR  TF0         
SJMP AGAIN       
END
```

### OUTPUT
<img width="700" height="600" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/632c456a-bccc-4150-b88e-cdd82b5212da" />


### RESULT
Thus the 8051 prpgram to generate a square wave with the frequency of 50khz using 8051 KEIL was done and shown the output.

____________________________

# SQUARE WAVE C PROGRAM

### AIM
Write a 8051 c program to generate a square wave with frequency of 50khz

### APPARATUS REQUIRED
- Personal Computer
- Keil µVision Software

### PROGRAM
```c
#include <reg51.h>
 sbit sqWave = P1^0;
 void main()
 {
    unsigned char TH0_val = 0xFF;
    unsigned char TL0_val = 0xF6;
    TMOD = 0x01; 
    while(1)
    {
        TH0 = TH0_val;
        TL0 = TL0_val;
        TR0 = 1;
        while(TF0 == 0);  
        TR0 = 0;          
        TF0 = 0;
        sqWave = ~sqWave;      
    }
 }
```

### OUTPUT
<img width="700" height="600" alt="Screenshot 2025-10-18 210642" src="https://github.com/user-attachments/assets/fa5d0802-a04d-4cc4-9d6f-ed481bdae386" />


### RESULT
Thus the 8051 C program to generate a square wave with frequency of 50khz using keil was done and shown the output.
