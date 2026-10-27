# CHAPTER 1 — What is a Computer? Hardware Basics, Processors, Memory, the Instruction Loop, and Why Devices Slow Down

## 1) What is a Computer?

Before getting further, what exactly is a computer? We always use it in daily life, but do you really know what it is?

A computer is a programmable device that stores, retrieves, and processes data. It is made of physical materials called hardware. Hardware has 4 components used for computation: processor, memory, network, and storage.

| Component | Simple description | Everyday analogy |
| :--- | :--- | :--- |
| **Processor** | The computer’s brain processes input data with algorithms to create output. | A worker following a recipe step by step |
| **Memory** | Addresses information in a computer and stores it in consistent locations. | A desk holding the materials you are using right now |
| **Network** | The connection between several technological devices that can share information. | Roads and delivery routes between buildings |
| **Storage** | The hardware that permanently stores a computer’s data. | A filing cabinet or pantry |
| **GPU** | A specialized chip intended to perform thousands of calculations at the same time. | 1,000 average students doing calculations at the same time |

Besides hardware, there is something called software. Software consists of programs and instructions written in a programming language (such as Python, C, C++, Java) to process data and produce results.

### A brief history of computer hardware

| Period | Development | Why it matters |
| :--- | :--- | :--- |
| Early tools | Abacus | A mechanical aid for arithmetic — computation is older than electronic computers. |
| 19th century | Charles Babbage, “father of computing,” designed the Analytical Engine | A mechanical computing machine that introduced important ideas related to programmable computers. |
| 19th century | Ada Lovelace | Recognised that “a machine could perform a sequence of operations”; she created an algorithm to compute the Bernoulli numbers — an early algorithm principle. |
| 20th century | ENIAC — Electronic Numerical Integrator and Computer | One of the earliest electronic digital computers; originally used for the US Army. It used thousands of vacuum tubes and required a large room. |
| Later 20th century | Transistors, integrated circuits, and microprocessors | Made computers smaller, faster, and more effective. Computer development increased significantly. |

## 2) How Does a Computer Actually Work? The Instruction Loop

The processor does not “understand” a whole program at once. It works through a program one instruction at a time, using a repeating cycle.

**The fetch–decode–execute cycle**
1. **Fetch.** The processor gets the next instruction from memory. A special counter — the program counter — keeps track of where the next instruction is located.
2. **Decode.** The processor figures out what the instruction means: “add these two numbers,” “load this value from memory,” or “jump to a different instruction if the result is zero.”
3. **Execute.** The processor performs the operation. For arithmetic, this may use the arithmetic logic unit (ALU). For load/store, it reads from or writes to memory.
4. **Write-back (optional).** The result is written back into a register or into memory.

Then the cycle repeats: fetch the next instruction, decode it, execute it, and so on.

### Worked example: adding two numbers (toy computer)

Suppose a program is meant to add two numbers and print the result. In a simplified instructional model, the steps look like this:

| Step | Instruction | What happens |
| :--- | :--- | :--- |
| 1 | `GET` | The processor fetches a number from the input and places it in a working register (an accumulator). |
| 2 | `STORE NUM` | The value in the accumulator is saved into a memory location called NUM. |
| 3 | `GET` | A second number is fetched from the input into the accumulator. |
| 4 | `ADD NUM` | The value stored at NUM is added to the accumulator; the result replaces the accumulator’s old value. |
| 5 | `PRINT` | The value in the accumulator is sent to the output. |
| 6 | `STOP` | The program ends. |

**What this example shows:** The processor does not “see” the whole addition in one glance. It sees `GET`, then `STORE`, then `GET`, then `ADD`, then `PRINT`, then `STOP`. Each instruction is fetched, decoded, and executed before the next one begins. The power of a computer comes from repeating this simple loop extremely quickly.

**The visual: the loop as a diagram**
```text
Fetch Instruction -> Decode Instruction -> Execute Operation -> (Repeat)
