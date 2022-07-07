# Jonesforth-ARM

An ARM port of X86 JonesForth by Richard W.M. Jones <rich@annexia.org>
at <http://annexia.org/forth>.

## What have I changed ?

Very little. When reading tokens with KEY from a stream, the end of the stream causes
the buffer to be cleared, the stream closed and then re-opened for /dev/tty. You can then
continue using the interpreter interactvly with the added forth words.

The NEXT word is one instruction less (faster ?)
    .macro NEXT
    ldr r0, [r10], #4
    ldr r15,[r0]
    .endm


## To Compile

gcc -nostdlib -static forth.s -oforth


## To Run

forth < forth.f


## Background reading

Threaded Interptetive Languages by R. G. Loeliger



ChiefEngineer
