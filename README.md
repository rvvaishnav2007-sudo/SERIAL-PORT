
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i)  Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="Vaishnav";
unsigned char i;
TMOD=0X20;
TH1=0XFA;
SCON=0X50;
TR1=1;
for(i=0;i<=12;i++)
{
SBUF=msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```


### (ii)  Serial Port Transfer a Single Character :
 
```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FDH
MOV SCON,#50H
SETB TR1
MAIN:
MOV SBUF,#'B'
WAIT:
JNB TI,WAIT
CLR TI
SJMP MAIN
END
```

### OUTPUT:
### (i) Serial Port to Transfer a Message
<img width="1917" height="870" alt="image" src="https://github.com/user-attachments/assets/2f890247-0afd-490c-b2f0-846fb36cdb41" />

### (ii) Serial Port Transfer a Single Character :
<img width="1918" height="1136" alt="image" src="https://github.com/user-attachments/assets/782f233f-8928-4d6b-8ef3-78f579a20a4f" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
