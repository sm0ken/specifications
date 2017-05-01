# Memory
This subsection is dedicated to the memory handling components of the smøken architecture. The basic idea is to have the kernel assign pages to processes and the MMU checking that processes only access the pages they are privileged to.

## MMU
To facilitate hardware-level concurrency, the MMU needs to be designed with extra care in mind. The MMU needs to be able to move data in parallel, since that is the only way to properly ensure that each ALU cycle can process multiple sets of data, enabling single-core MIMD (Multiple Instruction, Multiple Data) operation.

### Addressing modes
With the page-access operation giving processes as way to access certain pages, there is no need for a page+address adressing mode in the instructions, which helps simplify the instruction set. The necessary addressing modes will be:
* Literal access (setting a register to a predefined value)
* Direct access (fetching or writing from/to an address)
* Register direct access
[For reference](https://en.wikipedia.org/wiki/Addressing_mode#Simple_addressing_modes_for_data), please add any that you feel will make a good addition to the instruction set.

### Privilege control
The MMU will have to check if a certain page is allowed to be accessed by the process that is currently requesting memory access.

### Asynchronous memory access
Since access to main memory or worse yet, mass storage can be a very slow ordeal, memory access is done in an asynchronous mode where a memory read will lock a register while the execution of the currently executing program or, in case there is no further execution possible, a different program that is ready will execute for some time, until the memory access reports a finished state and unlocks access to the register for the process that requested the memory access.

## ? Variable page sizes ?
Should pages be able to have variable sizes and if so, how will addressing be handled efficiently? If not, what size would be reasonable to not have to switch pages excessively while also not allocating lots of unneeded memory to processes?
