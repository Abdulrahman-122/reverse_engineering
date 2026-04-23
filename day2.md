what is the x86 assembly language?
  - an instruction that was built to be detected by the processors (intel 8000)
  - this language is so powerful as it makes you understand how system talks at low level .
  - also we will study the 32bit systems as the malware will be written in 32bit -> this works on 64 bits
  - notes on hexadecimal language ;
    - First Column (4+9=13): 13 is less than 16. In hex, we represent 13 with the letter D. Since we didn't hit 16, there is no "group of 16" to carry to the next column.

        Second Column (8+2=10): 10 is less than 16. In hex, we represent 10 with the letter A. Again, no carry.
    
        Third Column (C+3=12+3=15): 15 is less than 16. In hex, we represent 15 with the letter F. Still no carry.

        The "Golden Rule" for Hex Addition
      
        Think of it like an odometer
      
        Add the numbers in decimal.
    
        If the sum is 0 to 15, just write the hex equivalent (0–F).
    
        If the sum is 16 or more, subtract 16, write the remainder, and carry 1 to the next column.
-> look at the notebook to understand the examples of hexadecimal

----
  now focus on Transistor;
    -it's a device that are used to build the chips on the computer ...
    - it has pins for input,output -> if you connect two pins with voltage -> current will pass between them
    - if you removed the volt -> no current will be passed between them
    - the most important type of transistors -> Field effect transistors.
    - <img width="288" height="175" alt="image" src="https://github.com/user-attachments/assets/26751bae-6235-451f-a9ee-f2a03896e8f4" />
    -as you know it has 3 gates -> drain,source,gate.
    - volt -> 1 ,no volt->0 
    - 
    - just know transistor is used to build the circuits of computer very well

----
- byte -> 8bits
- 2bytes -> word
- 4bytes-> double words
- 8bytes(64bits) -> equad  word
  computer handle any value using bits+memory address
  you will know later how to know the address of any instruction after decompile it using esp inside gdb
  - instruction pointer -> indicate to the next instruction to be run inside memory.

 ----
 Any computer contain;
   - memory
   - cpu
   - I/O devices

    - for cpu 
    we have control unit , Alu,Execution unit,registers,flags
      <img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/42dbcd20-4ef4-42f5-b89a-78f225945e9a" />
        - as you know -> Alu for arithmatic operations...
        -Control unit -> control retrieving data from memory and execute it 
        - Execution unit -> where data is brought and being executed 
        - registers -> internal memory storage inside cpu
        - flags -> do events inside cpu (hold 1, 0 ) 
        
-------
General-purpose Registers of x86 32bits;
    - store data temporarily on the processor
    - types;
      1.EAX -> accumulator -> arithmatic calculation + hold data of arithmatic operation
      2.EBX -> base register -> points to the DS -> store base address of program.
      3.ECX ->counter register ->hold number of times process is to be repeated + used for loop,string..
      4.EDX -I/O operation+extend EAX to 64bits
      5.ESI ->index register+pointer to data that are pointed by DS register+used as offset in string+array ,holds address for reading the data.
      6.EDI ->Destination index register+point to data that are  pointed by ES register,used as offset address in string,array,holds address of string 
      7.EBP -> indecate to the data on the  bottom of the stack frame +reference local variables   
      8.ESP -> points to  data on the top of the  stack  frame+reference local  variables
      <img width="960" height="720" alt="image" src="https://github.com/user-attachments/assets/b163a56e-d55f-4b8d-8f38-cf023d16a1f9" />
      - notes;
        -EAX,EBX,ECX,EDX -> are divided into (16,16)bits
          the least significant bits of them are divided into (8,8)bits -> these maybe (AL,BL,CL,DL)  and (AH,BH,CH,DH) 
        - while any ESI,EDI,ESP,EBP -> are divided into 16,16
          -the lower bits called;SI,DI,SP,BP
          <img width="1085" height="318" alt="image" src="https://github.com/user-attachments/assets/5841ec1c-d2c3-4ddc-b807-66614117db7c" />

--------

Segment Registers;
  -(CS) Code segment register ->stores the base location of code section for data access.
  -(DS)Data segment register ->store default location of  variables for data access.
  -(ES) Extra segment register ->  used  in string operation.
  -SS ->stack segment register -> store base location of stack segment + used when using stack pointer or base  pointer.
  -Fs -> extra segment register
  -GS -> extra segment register.
  <img width="300" height="168" alt="image" src="https://github.com/user-attachments/assets/c1683466-314d-48bf-beb1-5d23029f91d4" />

notes;
  -;segment registers -> 16bits + points to the memory specific segment.
  -Cs -> has pointer to code segment in memory.
  - processor -> retrieve codes from  memory based on CS register+ offset value of EIP(instruction pointer register)
  - 





