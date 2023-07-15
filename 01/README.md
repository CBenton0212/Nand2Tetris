# 01 Boolean Logic

- [Elementary Logic Gates](#elementary-logic-gates)
  - [Nand](#nand)
  - [Not](#not)
  - [And](#and)
  - [Or](#or)
  - [Xor](#xor)
- [(De)Multiplexers](#demultiplexers)
  - [Mux](#mux)
  - [DMux](#dmux)
- [N-Bit Logic Gates](#n-bit-logic-gates)
  - [Not16](#not16)
  - [And16](#and16)
  - [Or16](#or16)
  - [Mux16](#mux16)
- [N-Way Logic Gates](#n-way-logic-gates)
  - [Or8Way](#or8way)
- [N-Way (De)Multiplexers](#n-way-demultiplexers)
  - [Mux4Way16](#mux4way16)
  - [Mux8Way16](#mux8way16)
  - [DMux4Way](#dmux4way)
  - [DMux8Way](#dmux8way)

## Elementary Logic Gates

### Nand

<img width="490" alt="nand" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/1c3efbc2-1ee3-4752-b36f-b6b98a3b7419">

As the title of the book suggests, this is our most basic building block. All logic gates/chips can be created solely from Nand gates. We compose several other gates to make the chips more efficient.

### Not

<img width="657" alt="not" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/2e7c789f-3e9b-42c3-afbe-e4cd11f16ae9">

### And

<img width="657" alt="and" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/91ea5e02-8174-47a1-a855-808aa69f68c5">

> Notice the Not gate could be replaced with a Nand gate to have the same effect.

### Or

<img width="657" alt="or" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/375c2575-d70c-4323-8d62-53b601f4cf13">

> Again, the Not gates could be swapped with Nand gates to have the same effect.

### Xor

<img width="657" alt="xor" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/ab3590b2-f6a0-4a65-b015-781ff0aff3b4">

> Both the Or and the And gates could be replaced by series of Nand gates.

## (De)Multiplexers

Multiplexers allow us to select from a number of multiple inputs. So for a multiplexer with two inputs, `a` and `b`, we can add an additional `sel` bit to choose `0` (`a`) or `1` (`b`). Demultiplexers allow us to select from a number of multiple outputs in which we broadcast some input. So for a demultiplexer with one input `in`, we can add a `sel` bit to choose to broadcast `in` to `0` (`a`) or `1` (`b`).

### Mux

<img width="657" alt="mux" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/0c02517d-5b8c-49d5-b0d7-1f5c1a69213e">

### DMux

<img width="657" alt="dmux" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/575da251-4fed-4d5f-bd32-9eaba9739b84">

## N-Bit Logic Gates

N-Bit log gates allow us to apply our elementary logic gates to a bus of input bits. For example, instead of Anding a single `a` bit with a single `b` bit, we can And an `a` bus of 16 bits with a `b` bus of 16 bits. We do this by mapping indices across busses and apply the elementary logic gate to each pair of bits.

**Single Bit And Gate**

`a`  And  `b`  -->  `out`

**4-Bit And Gate**

`a[0]`  And `b[0]`  -->  `out[0]`

`a[1]`  And `b[1]`  -->  `out[1]`

`a[2]`  And `b[2]`  -->  `out[2]`

`a[3]`  And `b[3]`  -->  `out[3]`

### Not16

Apply a Not gate to all 16 bits of the `in` input bus.

### And16

Apply an And gate to all 16 bits of the `a` and `b` input busses.

### Or16

Apply an Or gate to all 16 bits of the `a` and `b` input busses.

### Mux16

Apply a Mux gate to all 16 bits of the `a` and `b` input busses.

## N-Way Logic Gates

N-Way logic gates allow us to chain logic gates, in serial, across an input bus.

### Or8Way

Apply an Or gate to all 8 bits of the `in` input bus. Conceptually this can be described as the following:

`in[0]`  Or `in[1]`  Or  `in[2]`  Or `in[3]`  Or  `in[4]`  Or `in[5]`  Or  `in[6]`  Or `in[7]`  -->  `out`

## N-Way (De)Multiplexers

By increasing the size of the `sel` input from a single bit to multiple bits, we increase the amount of options we can choose from. A single `sel` bit allows us to choose from two options, a two bit `sel` input allows us to choose from four options, a three bit `sel` input allows us to choose from eight options, etc.

In general, if we want to be able to choose from N options, we need log<sub>2</sub>N `sel` bits.

### Mux4Way16

<img width="632" alt="mux4way" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/71a18c7c-b521-4f33-b3ca-b16d09578c76">

### Mux8Way16

<img width="449" alt="mux8way" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/32b18752-7fd8-46ee-9d87-96f37355f165">

### DMux4Way

<img width="632" alt="dmux4way" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/03690fe1-ff0e-412a-bda7-7368fd2e9b41">

### DMux8Way

<img width="449" alt="dmux8way" src="https://github.com/CBenton0212/Nand2Tetris/assets/30737974/f5fb7082-ba65-4c23-81c5-6ac9c2f70cc4">
