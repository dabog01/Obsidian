A complete  ==**set of known commands**== is called an **instruction list**, sometimes abbreviated to ==**IL**==

>IL's also is known as the alphabet of a machine language

But still we need a bridge...

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~Modified~~Art by Nina Butorac
Humans
         @\_______/@
        @|XXXXXXXX |
       @ |X||    X |                                        :3
      @  |X||    X |
     @   |XXXXXXXX |
    @    |X||    X |             V
   @     |X||   .X |
  @      |X||.  .X |                      V
 @      |%XXXXXXXX%||                High level-    
@       |X||  . . X||        Programming Languages
        |X||   .. X||                                @     @          
        |X||  .   X||.                              ||====%
        |X|| .    X|| .                             ||    %
        |X||.     X||   .                           ||====%
       |XXXXXXXXXXXX||     .                        ||    %
       |XXXXXXXXXXXX||         .                 .  ||====% .     Computers
       |XX|        X||                .        .    ||    %  .
       |XX|        X||                   .          ||====%   .
       |XX|        X||              .          .    ||    %     .
       |XX|======= X||============================+ || .. %  ........
===== /            X||                              ||    %
                   X||           /)                 ||    %
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A program written in a **high-level programming language** is called a **source code** and the file containing the source code is called the **source file**.

## Compilation vs Interpretation

There are two different ways of **transforming a program from a high-level programming language into machine language**:

**Compilation** – the source program is translated once (however, this act must be repeated each time you modify the source code) by getting a file (e.g., an _.exe_ file if the code is intended to be run under MS Windows) containing the machine code. Now you can distribute the file worldwide; the program that performs this translation is called a **compiler** or **translator**

**Interpretation** – you (or any user of the code) can translate the source program each time it has to be run. The program performing this kind of transformation is called an **interpreter**, as it interprets the code every time it is intended to be executed. It also means that you cannot just distribute the source code as-is, because the end-user also needs the interpreter to execute it

| |Compilation|Interpretation|
|---|---|---|
|Advantages| **✓ **the execution of the translated code is usually faster;<br>**✓ **only the user has to have the compiler – the end-user may use the code without it;<br>**✓**the translated code is stored using machine language – as it is very hard to understand it, your own inventions and programming tricks are likely to remain your secret.| **✓ **you can run the code as soon as you complete it – there are no additional phases of translation;<br>**✓**the code is stored using programming language, not machine language - this means that it can be run on computers using different machine languages; you don't compile your code separately for each different architecture.|
|Disadvantages|**❌ **the compilation itself may be a very time-consuming process – you may not be able to run your code immediately after making an amendment;<br> **❌ **you have to have as many compilers as hardware platforms you want your code to be run on.| **❌ **don't expect interpretation to ramp up your code to high speed - your code will share the computer's power with the interpreter, so it can't be really fast;<br> **❌ **both you and the end user have to have the interpreter to run your code.|


