# Nand2Tertris

This is my implementation of a simple computer, from logic gates to an OS, as I follow along _The Elements of Computing Systems: Building a Modern Computer from First Principles_ by Noam Nisan and Shimon Schocken. Visit their website for more details about the book and demo projects from others: https://www.nand2tetris.org/

## Layout

Each chapter in the book focuses on a specific topic and concludes with a set of things for the reader to implement. Each directory represents a chapter and includes the associated projects for that chapter. The README at the root of each directory contains my notes and diagrams to go along with each topic.

1. [Boolean Logic](https://github.com/CBenton0212/Nand2Tetris/tree/main/01#readme)
2. [Boolean Arithmetic](https://github.com/CBenton0212/Nand2Tetris/tree/main/02#readme)
3. [Memory](https://github.com/CBenton0212/Nand2Tetris/tree/main/03#readme)
4. Machine Language
5. Computer Architecture
6. Assembler
7. Virtual Machine I: Processing
8. Virtual Machine II: Control
9. High-Level Language
10. Compiler I: Syntax Analysis
11. Compiler II: Code Generation
12. Operating System

## Tools

There is also a tools directory to house all required executables for testing and executing each piece of the project.

## Testing

To test a chip design (.hdl file), you can run the respective .tst script. For example, to test `./01/And.hdl`, execute `./tools/HardwareSimulator.sh ./01/And.tst`. This will find the implemented hardware description, run a series of tests to produce and output file, and then compare it to `./01/And.cmp` to check for correctness.

All tests are also included in a GitHub workflow to run automatically against each pull request.
