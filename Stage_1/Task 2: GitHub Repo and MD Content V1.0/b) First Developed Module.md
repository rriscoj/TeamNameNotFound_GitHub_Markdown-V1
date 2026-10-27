
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
```

## 3) Memory and Why Devices Slow Down When Overwhelmed with Data

If the processor is so fast, why does it ever slow down? Because fast memory is small and expensive; large memory is slower and cheaper.

The memory hierarchy

Level Typical role Speed (relative) Size (order of magnitude) Persistence
Registers Values the processor is using right now Fastest Tens of locations Lost on power-off
L1 cache Recently used instructions and data Very fast Tens of kilobytes Lost on power-off
L2 / L3 cache Larger staging areas for main memory Fast Megabytes Lost on power-off
Main memory (RAM) Program and data currently in use Moderate Gigabytes Lost on power-off
Storage (SSD / disk) Programs and files not currently needed Slow Hundreds of gigabytes to terabytes Kept when power is off

The bottleneck idea

A bottleneck is the part of a system that limits overall performance. Even if one part is extremely fast, the whole system cannot go faster than its slowest necessary step.

In a stored-program computer, the processor and main memory share a communication pathway — the bus. The processor can often perform arithmetic faster than instructions and data can be delivered from memory through that pathway. When the amount of data or the complexity of the program increases, the pathway becomes congested, and the processor is forced to wait.

This specific limitation is widely called the von Neumann bottleneck: the lag that occurs because data moves between memory and the processor more slowly than the processor can compute.

What “overwhelmed with data” actually looks like

When a device is “overwhelmed,” it is usually not because the processor has suddenly become slow. It is because one or more of these has happened:

1. The working data no longer fits in cache. More data must travel from RAM through the slower bus, so the processor waits more often.
2. Main memory itself becomes the limit. If the processor is constantly fetching from RAM, performance is capped by RAM bandwidth and latency, not by processor speed.
3. Storage becomes involved. If the data is not even in RAM and must be read from a disk or SSD, the wait becomes much longer.
4. The bus becomes congested. Instructions and data compete for the same pathway, and the processor idles while waiting for one or the other.

A useful diagnostic question is: “Where is the data coming from right now?”

· If it is in a register → effectively instant.
· If it is in cache → fast.
· If it is in RAM → noticeably slower.
· If it is on storage → much slower still.

When a device slows down, the processor is often not “thinking slowly.” It is waiting for data to arrive.

### Bottleneck reference table

| Situation | Where the processor gets data | Likely result |
| :--- | :--- | :--- |
| Small calculation on values already loaded | Registers | Fast; processor is the limit |
| Repeated loop over a small array that fits in cache | Cache | Fast; cache hit rate is high |
| Large dataset that does not fit in cache | Main memory (RAM) | Slower; memory bandwidth and bus become the limit |
| Opening a large file that is not in RAM | Storage (SSD or disk) | Much slower; storage I/O is the bottleneck |
| Many programs competing for memory and bus | RAM and bus shared across tasks | Variable slowdown; bottleneck shifts between memory and bus |

## 4) Soooo, why does this matter?

Computer hardware is not just an abstract topic — it explains everyday behaviour you have probably noticed:

· Why does a phone slow down when you open too many apps? The working data no longer fits comfortably in RAM, so the system swaps data to storage, and the processor waits.

· Why does a laptop fan spin up during heavy tasks? The processor is working hard, generating heat, and the system must cool it down to keep it running safely.

· Why a smart device with a tiny battery cannot run a huge AI model. Low-power microchips have limited memory and processing capacity; the bottleneck shows up as battery drain and slow responses.

· Why AI training needs specialised hardware (GPUs, TPUs). Standard processors spend too much time waiting for data; AI chips are designed to move and process many data items in parallel.

Understanding the instruction loop and the bottleneck gives you the foundation to understand why real-world smart devices behave the way they do — and why hardware choice matters for AI applications.

## 5) QnA

1. What are the four main hardware components of a computer?
A. Processor, memory, network, and storage.
B. Keyboard, mouse, monitor, and printer.
C. Python, C, C++, and Java.
D. Abacus, ENIAC, transistor, and microprocessor.

2. What happens during the “fetch” stage of the instruction cycle?
A. The processor performs the arithmetic operation.
B. The processor reads the next instruction from memory.
C. The processor writes the result to storage.
D. The processor turns off.

3. Why can the processor not keep all programs and data in registers?
A. Registers are too slow.
B. Registers are extremely small and expensive; they can only hold a handful of values.
C. Registers are stored on the hard disk.
D. Registers only work with software, not hardware.

4. What is the von Neumann bottleneck?
A. A type of network cable.
B. The lag occurs because instructions and data share a pathway between memory and the processor.
C. A programming language used in AI.
D. A chip designed only for graphics.

5. A computer has a very fast processor but slow performance when working with a large database. What is the most likely bottleneck?
A. The processor is too slow.
B. The keyboard is broken.
C. Memory or storage — the data cannot be delivered fast enough.
D. The monitor resolution is too low.

6. Using the toy computer example from the text, explain in your own words what the processor does during the ADD NUM instruction.

7. A user complains that their laptop is running very slowly while trying to open a massive video file, but their processor is barely working (low CPU usage). Based on the concept of the memory hierarchy and the "von Neumann bottleneck," what is the most likely cause of the slowdown?

## 6) Answer Key

1. A
2. B
3. B
4. B
5. C
6. The processor takes the value that was previously saved in the memory location called NUM and adds it to the value currently sitting in the working register (the accumulator). The result then replaces the old value in the accumulator.
7. The laptop is most likely experiencing a storage bottleneck. Because the file is massive and not currently in RAM, the processor has to wait for the slow storage drive (HDD or SSD) to fetch the data and send it across the bus. The processor isn't "thinking slowly"—it is just idling and waiting for the data to arrive.

## 7) References

1. Princeton University, “Inside the CPU” (COS 109) — fetch–decode–execute cycle and toy computer instruction set.
2. MIT Computer Science, “The von Neumann Model” — memory holds both data and instructions; CPU fetches, interprets, and executes.
3. Taylor & Francis, The Deep Learning Revolution, chapter 2 extract — definition of the von Neumann bottleneck.
4. IBM Research, “How the von Neumann bottleneck is impeding AI computing” — bottleneck as lag between data movement and computation.
5. Princeton University, “Computer Architecture” (COS 217) — memory hierarchy: registers, L1/L2/L3 cache, DRAM, disks.
6. University of Oklahoma, NCSI parallel computing workshop slides — CPU waits for data because memory transfer is slower than calculation; cache helps.
7. Computer Hope — computer definition: https://www.computerhope.com/jargon/c/computer.htm
8. OpenStax — Introduction to Computer Science: https://openstax.org/books/introduction-computer-science/pages/1-introduction

## 8) Image References

· Figure 1.1 Computer: https://sl.bing.net/cJloFEdO9T2
· Figure 1.2 Abacus: https://sl.bing.net/j5DaIqjyikK
· Figure 1.3 Charles Babbage: https://sl.bing.net/giQcgyDAqMm
· Figure 1.4 Ada Lovelace: https://sl.bing.net/dhoYGZV8tuS
· Figure 1.5 ENIAC: https://openstax.org/apps/image-cdn/v1/f=webp/apps/archive/20260604.144757/resources/26786a448eea38805e96b447da176c3d70ac15c3

## Notes

- **Algorithm** — A sequence of instructions that enables computing. An input can be processed step by step to create an output.
- **Transistor** — A semiconductor device used to amplify or switch electrical signals and power.
- **Integrated Circuit (IC)** — Also called a chip; an electronic circuit formed by electronic components such as transistors, resistors, and capacitors, and their interconnections.
- **Microprocessor** — An integrated circuit that contains all the functions of a central processing unit (CPU) of a computer.
- **Instruction** — A single basic operation that the processor can carry out, such as “add,” “load from memory,” “store to memory,” or “compare.”
- **Program counter** — A special storage location inside the processor that holds the memory address of the next instruction to be fetched.
- **Register** — A very small, very fast storage location inside the processor, used to hold the values the processor is working on right now.
- **Cache** — A smaller, faster storage area that holds a copy of data from a larger, slower memory. A *cache hit* means the data was found in cache; a *cache miss* means the processor must wait for it to be fetched from a slower level.
- **von Neumann bottleneck** — The performance limit that arises because, in a stored-program computer, instructions and data share a pathway between memory and the processor, and memory cannot supply them as fast as the processor can consume them.

```
