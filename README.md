
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
WAIT:JNB TI, WAIT
 CLR TI 
END

```
### (ii) Serial Port to Transfer a Message

```
ORG 00H 
MOV DPTR, #4500H
 MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
AGAIN: MOVX A,@DPTR
 MOV SBUF, A
 WAIT:JNB TI, WAIT
 CLR TI 
INC DPTR
 SJMP AGAIN
 END


```

### OUTPUT:
### (i) Serial Port Transfer a Single Character

<img width="1366" height="982" alt="image" src="https://github.com/user-attachments/assets/b8f724e5-3fca-4c98-a77d-d02381d500b6" />

### (ii) Serial Port to Transfer a Message

<img width="1670" height="849" alt="image" src="https://github.com/user-attachments/assets/a5137d47-ed38-4d28-87f8-e9c7075f3b7a" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
