# list of instructions

## Synchronous instructions

### arithmetic instructions
* add (OP1) (OP2) (RES)
* sub (OP1) (OP2) (RES)
* mov (OP1) (RES)
* rol (OP1) (RES)
* ror (OP1) (RES)
* slz (OP1) (RES)
* srz (OP1) (RES)

### logic instructions
Not sure about the dedicated logical operations, since it may be simple to implement them with multiple instructions.
* compare (OP1) (OP2) (RES)
* not (OP1) (RES)
* and (OP1) (OP2) (RES)
* or  (OP1) (OP2) (RES)
* xor (OP1) (OP2) (RES)

### tid 0 instructions
* getstats (tid) (DEST-REGISTER)
* setstats (tid) (value or register)
* getiptr (tid) (DEST_REGISTER)
* setiptr (tid) (value or register)
* halttrhead (tid)
* startthread (tid)

## Asynchronous instructions

### MMU usage instructions
* ramload (DEST-REGISTER) (SRC-ADRESS)
* ramstore (SRC-REGISTER) (DEST-ADRESS)
* setpage (PAGENUMBER)
* push (SRC)
* pop (DEST)
* call (symbol/address)

### MMU manipulation instructions (tid 0 only)
* actinplace (tid)
* haltmmufor (tid)
* tbd

### timer instructions
* requesttimer (register to save timer number, 0 indicates failure)
* inittimer (timer number) (FREQ) (interrupt symbol/address)
* getfreq (timer number) (DEST-REGISTER)
* getinterrupt (timer number) (DEST-REGISTER)
* hastimer (timer number) (DEST-REGISTER)
* isrunning (timer number) (DEST-REGISTER)
* starttimer (timer number)
* stoptimer (timer number)
* tid-0 only: timertid (timer number) (DEST-REGISTER)

### hardware control instructions
* tbd
