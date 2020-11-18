.MODEL SMALL
DISP MACRO MSG
  LEA DX,MSG
  MOV AH,09H
  INT 21H                               ;   dh 12      mov ah,01h    0102
ENDM                                     ;  dl  23    int 21h         AAD-0012
.DATA
ROW DB 02 DUP(0)
COL DB 02 DUP(0)
MSG1 DB 0DH,0AH,"ENTER X-CO-ORDINATE: $"
MSG2 DB 0DH,0AH,"ENTER Y-CO-ORDINATE: $"
msg3 db 0dh,0ah,"cursor displayed at the correct coordinates$"
.CODE
    MOV AX,@DATA
    MOV DS,AX              ;          AX
    DISP MSG1               ;   Row=3132   ax=0102
    MOV SI,OFFSET ROW        ;  Col=3233    aad=0012
    CALL READ
    DISP MSG2                 ;            0023
    MOV SI,OFFSET COL
    CALL READ
    MOV SI,OFFSET ROW
    MOV AH,[SI]
    INC SI
    MOV AL,[SI]
    SUB AX,3030H  
    AAD           
    MOV DH,AL ;row
    MOV SI,OFFSET COL
    MOV AH,[SI]     
    INC SI
    MOV AL,[SI]
    SUB AX,3030H    
     AAD                
    MOV DL,AL  ;col
    
    MOV AH,00
    MOV AL,03H
    INT 10H
    MOV AH,02H
    INT 10H
   
    JMP FINAL


 READ PROC NEAR              
     MOV CX,02H
BACK:MOV AH,01H             
     INT 21H                
     MOV [SI],AL
     INC SI
     DEC CX
JNZ BACK
RET
READ ENDP
FINAL:MOV AH,01H
      INT 21H
      MOV AH,4CH
       INT 21H
       END
