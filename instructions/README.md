# list of instructions

## arithmetic instructions
* add (OP1) (OP2) (RES)
* sub (OP1) (OP2) (RES)
* mov (OP1) (RES)
* rol (OP1) (RES)
* ror (OP1) (RES)
* slz (OP1) (RES)
* srz (OP1) (RES)

## logic instructions
Not sure about the dedicated logical operations, since it may be simple to implement them with multiple instructions.
* compare (OP1) (OP2) (RES)
* not (OP1) (RES)
* and (OP1) (OP2) (RES)
* or  (OP1) (OP2) (RES)
* xor (OP1) (OP2) (RES)

## MMU usage instructions
* ramload (DEST-REGISTER) (SRC-ADRESS)
* ramstore (SRC-REGISTER) (DEST-ADRESS)
* setpage (PAGENUMBER)
* push (SRC)
* pop (DEST)
* call (symbol/address)

## MMU manipulation instructions (tid 0 only)
tbd
