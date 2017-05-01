# list of instructions

* add (OP1) (OP2) (RES)
* sub (OP1) (OP2) (RES)
* mov (OP1) (RES)
* rol (OP1) (RES)
* ror (OP1) (RES)
* slz (OP1) (RES)
* srz (OP1) (RES)

* ramload (DEST-REGISTER) (SRC-ADRESS)
* ramstore (SRC-REGISTER) (DEST-ADRESS)
* setpage (PAGENUMBER)

* compare (OP1) (OP2) (RES)
* not (OP1) (RES)
* and (OP1) (OP2) (RES)
* or (OP1) (OP2) (RES)
Not sure about the dedicated logical operations, since it may be simple to implement them with multiple instructions.

* call (symbol/address)
* push (SRC)
* pop (DEST)
