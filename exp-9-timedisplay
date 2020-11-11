.MODEL SMALL
.CODE
   MOV AH,2CH
   INT 21H                   ; ch cl dh
                              ;14:24:36
   MOV AL,CH                   ; AAM-14=0104
   AAM                          ;       3030
   MOV BX,AX                     ;    ax=3134
   CALL DISP                      ;      mov dl,ah
   MOV DL,':'                      ;     mov ah,02h
   MOV AH,02H                       ;    int 21h
   INT 21H

  MOV AL,CL
   AAM
   MOV BX,AX
   CALL DISP
   MOV DL,':'
   MOV AH,02H
   INT 21H

   MOV AL,DH
   AAM
   MOV BX,AX
   CALL DISP

   MOV AH,4CH
   INT 21H

   DISP PROC NEAR
   MOV DL,BH      ;BX=0104
   ADD DL,30H      ;  31
   MOV AH,02H ;display character
   INT 21H
   MOV DL,BL
   ADD DL,30H
   mov ah,02h
   INT 21H
   RET
   DISP ENDP
   END
