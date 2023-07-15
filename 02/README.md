# 02 Boolean Arithmetic

- [HalfAdder](#halfadder)
- [FullAdder](#fulladder)
- [Add16](#add16)
- [Inc16](#inc16)
- [ALU](#alu)

## HalfAdder

Half adders take in two bits as input, `a` and `b`, and produce two bits of output, `sum` and `carry`. The right most bit (least significant bit) represents the sum while the left most bit (most significant bit) represents the carry bit.

`a`  +  `b`  =  `carry` `sum`

0  +  0  =  00

1  +  0  =  01

0  +  1  =  01

1  +  1  =  10

<img width="498" alt="half_adder" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/dab66d1a-cfa7-4b5c-9cb9-805d4130411a">

## FullAdder

A full adder is composed of two half adders (hence the name) plus an Or gate. Full adders receive three bits as input, `a`, `b`, and an additional carry bit `c`. This allows us to chain addition operations while including a carry bit from one addition operation in the next addition operation.

<img width="498" alt="full_adder" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/39c2cef7-52bd-4a81-a451-96a01b5c1da2">

## Add16

Add16 simply adds two 16-bit busses, `a` and `b`. The bits at index 0 (`a[0]` and `b[0]`) are added through a HalfAdder which produces a sum bit and a carry bit. The sum bit is then stored in `out[0]` while the carry bit is forwarded to a FullAdder. The bits at index 1 are also fed into this FullAdder so that the sum produced at index 1 considers `a[1]`, `b[1]`, and the carry bit from index 0. This sum is then stored in `out[1]` and the carry bit is again forwarded to the next operation. This cycle repeats for all 16 bits and the final carry bit is "thrown away".

## Inc16

Inc16 makes use of Add16 and simply adds one to a given input `in`. We represent one by encoding `0000 0000 0000 0001`. This means that we can forward `in` to the `a` bus of Add16 and forward a bus of all zeros and a single one to the `b` bus of Add16.

## ALU

An Arithmetic Logic Unit is responsible for executing arithmetic and logical operations within a CPU. Our ALU takes two inputs, `a` and `b`, both of which are 16 bit busses. An ALU also has a set of opcodes that dictate which operation to perform on the input busses. The number of operations an ALU can perform is determined by the number of opcodes it includes.

At the core of our ALU we can either Add or And the two inputs. Prior to performing this operation, we can also zero out or negate either (or both) of the input busses. We can also negate the out of the Add/And operation. These operations combined equate to the operations of: `x + y, x - y, y - x, 0, 1, -1, x, y, -x, -y, !x, !y, x + 1, y + 1, x - 1, y - 1, x & y, x | y`. The result of this operation is sent to the output `out`.

In addition to producing `out`, the ALU also sets a bit for `zr` and `ng` to denote if the output is zero or negative, respectively.

<img width="574" alt="ALU" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/bc091647-6afc-415d-9fc6-b7f1e44a4956">

> A simple overview of the inputs and outputs of our ALU

<img width="1510" alt="ALU_exploded" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/8e828b10-a4d8-4077-ac8f-8fa454be0a24">

> Opcodes are embedded within the boundaries for a cleaner diagram, however these would be fed into the ALU just like `a` and `b` would be.
