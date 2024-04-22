Binary string where ONLY ONER of the bits is 1 is called on-hot encoded
	10000000
	00000010
	00100000

Convert one format to another

### Decoder 
n + 1 inputs and 2^n outputs
first n inputs are an unsigned int
outputs form 2^n one-hot encoded string

Additional Enable input that sets the output to 0 when set to 0
	![[Pasted image 20240414223145.png]]2 bit input 4 bit output
active high output bc functions when enable is 1

![[Pasted image 20240414223443.png]]
same but active low bc functions when enable is 0

![[Pasted image 20240414223736.png]]
generalization of decoder
	n inputs and 2^n outputs
