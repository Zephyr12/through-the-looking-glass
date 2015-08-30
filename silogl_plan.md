Into the silicon looking glass
==========================

## Abstract
- The complex made is usually made (too)
- comprehensive (complex) guide to "simple" things

## Main body

### Hard Disk Read



### Program Execution

- bios / efi `cause simple`
- fetch exec [3]
    - MAR <- PC
    - PC += 1
    - MBR <- Memory
- multi core

### Input

- key pressed
- membrane compressed [2]
- signal sent to keyboard microprocessor
- microprocessing happens
- output is sent to a PIC (programmable interrupt controller) [1]
- handled by PIC
- `memory` set PIC `CPU can read`
- BIOS
- OS
- User space programs
- What ever happened

### Output

- CPU sends instructions / data down a bus 
- The GPU reads the data
- Transforms it into screen drawing instructions i.e. fill this block of pixels
- Sends to the monitor
- Tint electro-sensitive filters on an LCD display
- Block the necessary light

### Network

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


## References

1. `http://www.bottomupcs.com/peripherals.html`
2. `http://www.ergopedia.ca/ergonomic_concepts/Mechanical_Keyswitches_Membrane_Keyswitches_and_Scissor_Switch_Membrane_Keyswitches_Ergonomic_Considerations.html`
3. `http://www.ayomaonline.com/academic/fetch-execute-cycle/`
