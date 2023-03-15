RDT 2.0 cont.
duplication error, state stuck in forever wait if ack is corrupted

RDT2.1
fixed duplication error by adding XOR of prev packet number
twice as many states as rdt2.0
- Get rid of NACK
	- 