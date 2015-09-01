Through The Silicon Looking Glass
=================================

## Abstract
There are many parts of the modern world that seem to run on a strange type of magic. A sorcery based on doped silicates and rare earths. With a little attention this magic looses it's sheen and the sufficiently advanced technology can be revealed. In this article I will cover how some of the most fundamental parts of modern computing can be demystified.

### Program Execution
To run a program it must be read from *Secondary storage*, storage that is not immediately available to the processor. This is because *Primary storage*, storage that is directly available to the processor, such as *Random Access Memory, RAM* or Cache cannot survive reboots i.e. when you reboot the computer the data does not persist. So upon booting the CPU asks the primary storage for the first *Partition* on it. This partition usually contains the *Basic Input Output System, BIOS* on older computers or the *Extended Firmware Interface, EFI* loader on newer ones. The purpose of these peices of software is to set up hardware in a way that allow it to be used by the *Operating System*, and usually to start the *Boot loader* which finally loads the *Operating System*: all this, by the way, happens in a fraction of a second well before any `Windows` logo shows up. Lets go into one of the smallest parts of the bios, the single *Instruction*; Lets assume that the CPU has just finished handling the last instruction. A *Register*, a fast segment of memory under direct control of the CPU, called the *Program counter* is copied into another register called the *Memory address register*. The contents of this register is sent to the RAM on a pathway called an *Address bus*, busses used to be parrelel bundles of cable but they like other old parts of compter archetecture have been updated and nowerdays they refer to any way of transferring signals from one component to another. Once at the RAM, the *Ram controller* searches the RAM for the data and sends it back to the CPU on the *Data bus*. While it arrives the CPU, the program counter is incremented the data from the data bus is copied into the *Memory Buffer Register*; from here it is copied by the CPU's *Control Unit* into the *Current Instuction Register*. The control unit then splits up the instruction into *Opcode, The Type of Operation* and *Operand, The things to be operated on*. These get sent to the *Arithmatic Logic Unit, ALU* which finally performs the operation and stores it in a temporary register called the accumulator untill it can be put to better use.


### User Input
When you press the key on a key board a *Membrane* under the key is compressed. This compression generates a signal which is sent to the *Microprocessor* on the keyboard itself. The microprocessor handles and processes this data into a form that the rest of the computer can read. This is then sent to the aptly named *Programmable interrupt controller, PIC* in the form of *Scan codes*, which are usually a list of numbers indicating which keys have been pressed. Once at the scan codes have arrived the controller sends the *Central Processing Unit, CPU* an *Interrupt*, a signal that tells the CPU to drop everything and handle the request. Upon finishing it's current instruction the CPU checks the PIC for an interrupt and if one has happened the CPU jumps to the location in memory that contains the part of the *Operating System, OS* that handles that type of request. Once the operating system acknowledges the interrupt it then gathers data i.e. what keys were pressed, which modifiers were pressed (Shift, Control), bundles this data up and sends it to the currently running program. This program then decides how to handle the *Key-event*, e.g. to display it on screen in a Search Bar. On average this happens 3-4 times a second for the keyboard, and much more often for things like mouse movement which follows a similar process.


### Visual Output
Your *monitor* and *graphics cards* are *periferals* just like the keyboard and mouse: but unlike the keyboard and mouse, which use interrupts the graphics card use something called mapped memory. This means that for example setting the value of the 753664th memory could be the start of the screen buffer, an area of memory that contains the colours of the screen pixels. So to display an image a program would have to load the image into RAM from whatever source it needed, set the mode of the display to tell it to render graphics and not text and then display it into the *buffer* that the graphics card expects. As well as this if the program needs complex image manipulations it could send commands from a standard like OpenGL or Direct3D which provide high-level interfaces to the graphics hardware. The graphics card converts this data into digital (or analogue depending on age and connection type) signals that the monitor can understand. The monitor, which is essentially a backlight covered by color and polarising filters, then blocks out light by using a filter polarised at 90 degrees to the constant filter at the sub-pixel level. See [Fig 1] for a visual representation.

### A Cat Photo

So now we have the three of the four main aspects of modern computing: input, processing and output. The final one, abstraction is one of the harder ones to describe due to its abstract nature. So lets tackle it with something simple, a cat photo. When you click on a button you are interacting with the *application layer*, this layer deals with the *protocols and interfaces* used by the sender and reciever, in this case you are **usually** using *http* a protocol for sending documents over the internet in the form of *requests* and *responses*. The request looks something like `GET www.mycoolsite.tldshavegonetoofar/imgs/cat.gif HTTP/1.1`, breaking this down the `GET` portion means that the request one that retrives data, there are others like PUT, DELETE and TRACE but for now get will do; the 
`www.mycoolsite.tldshavegonetoofar/imgs/cat.gif` tells the reciever, in this instance known as a *server* that the thing we want is stored at the location `/imgs/cat.gif` on the web server at `mycoolsite.tldshavegonetoofar`. 

- You click on a button
- Application sends HTTP request to netcard
- Netcard sends the data + protocol info to router
- router splits up the data into packets and adds source and dest ports
- adds source and dest ip and sends it across the network
- physical layer adds frame header and footer

#### Routing

- each router checks if it is the dest and if it knows the dest
- if not sends it to everyone
- complex routing algos
- W-shaped routing

#### Back on topic

- server looks up
- forms response
- sends response
- same routing on the way back
