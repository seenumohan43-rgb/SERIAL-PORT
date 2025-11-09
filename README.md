
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include <reg51.h>

void main(void)
{
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    SBUF = 'A';
    while(TI == 0);
    TI = 0;

    while(1);
}



```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "SHYAM";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}


```

### OUTPUT:
![WhatsApp Image 2025-10-29 at 2 35 03 PM](https://github.com/user-attachments/assets/4682a171-d393-4c99-b65c-d43cbdc5fd21)

![WhatsApp Image 2025-10-29 at 2 37 44 PM](https://github.com/user-attachments/assets/a4de4087-f0e0-422e-b26a-ef7ef8d40b0c)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
