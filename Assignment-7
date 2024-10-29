1 Write a program in assembly language to take a single-digit integer from the user and print it on the screen.
Code:

ORG 100h           ; Origin, to specify that the program starts at 100h (COM file format)

; Display message "Enter an uppercase letter: "
MOV DX, OFFSET msg_input  ; Load the address of the message
MOV AH, 09h        ; Function 09h of INT 21h is used to display a string
INT 21h            ; Call DOS interrupt to print the message

; Read a single character from the user
MOV AH, 01h        ; Function 01h of INT 21h is used to read a character
INT 21h            ; Call DOS interrupt to get the character
MOV AL, AL         ; Store the input character in AL

; Check if the character is an uppercase letter (A-Z)
CMP AL, '0'        ; Compare AL with 'A'
JL NotDigit        ; If the input is less than 'A', it is not uppercase
CMP AL, '9'        ; Compare AL with 'Z'
JG NotDigit        ; If the input is greater than 'Z', it is not uppercase
mov cl,al    

; Convert the uppercase letter to lowercase
;ADD AL, 20h       ; Add 32 (20h) to convert uppercase to lowercase

; Print the message "The lowercase letter is: "
MOV DX, OFFSET msg_output  ; Load the address of the output message
MOV AH, 09h        ; Function 09h of INT 21h is used to display a string
INT 21h            ; Call DOS interrupt to print the output message        

; Print the converted lowercase letter
MOV DL, CL         ; Move the lowercase letter to DL
MOV AH, 02h        ; Function 02h of INT 21h is used to print a single character
INT 21h            ; Call DOS interrupt to print the character
JMP EndProgram     ; Jump to the end of the program

NotDigit:
; If the input is not an uppercase letter, display an error message
MOV DX, OFFSET msg_error  ; Load the address of the error message
MOV AH, 09h        ; Function 09h of INT 21h is used to display a string
INT 21h            ; Call DOS interrupt to print the error message

EndProgram:
; Terminate the program
MOV AH, 4Ch        ; Function 4Ch of INT 21h terminates the program
INT 21h            ; Call DOS interrupt to exit

msg_input  DB 'Enter a digit: $'
msg_output DB 0Dh, 0Ah, 'The entered digit is: $'  ; Output message
msg_error  DB 0Dh, 0Ah, 'Error: Not a digit! $'  ; Error message

END                ; End of program

2. Write a program in assembly language to take two single-digit integers from the user and print the result of subtraction on the screen.
Code:
org 100h
 mov dx,offset msg_input1
 mov ah,09h
 int 21h
mov ah,01h
 int 21h 
mov bl,al
 cmp al,'0'
 jl NotDigit
 cmp al,'9'
 jg NotDigit 
mov dx,offset msg_output1
 mov ah,09h
 int 21h     
mov dl,bl
 mov ah,02h
 int 21h 
mov dx,offset msg_input2
 mov ah,09h
 int 21h
 mov ah,01h
 int 21h 
mov cl,al
 cmp al,'0'
 jl NotDigit
 cmp al,'9'
 jg NotDigit 
mov dx,offset msg_output2
 mov ah,09h
 int 21h     
mov dl,cl
 mov ah,02h
 int 21h
 mov dx,offset msg_sub
 mov ah,09h
int 21h       
sub bl,cl
 js NegativeResult
 add bl,30h
 mov dl,bl
 mov ah,02h
 int 21h 
jmp endprogram         
NegativeResult:
 mov dl, '-'
 mov ah, 02h
 int 21h  
neg bl   
add bl, 30h  
mov dl, bl
 mov ah, 02h
 int 21h
 jmp endprogram
 NotDigit:
 mov dx,offset msg_error
 mov ah,09h
 int 21h
 endprogram:
 mov ah,4Ch
 int 21h   
msg_input1 DB "enter first digit:$"
 msg_output1 Db 0dh,0ah,"The entered digit is: $"
 msg_input2 DB 0dh,0ah,"enter second digit:$"
 msg_output2 Db 0dh,0ah,"The entered digit is: $" 
msg_sub db 0dh,0ah,"The subtraction of given two digits is: $"
 msg_error db 0dh,0ah,"Error: Not a digit!$ "
END




