# Foundations of Computer Science & AI
## Module 1: Understanding Computer Hardware and Its Role in Artificial Intelligence

* **Level:** Beginner
* **Learning area:** Foundations of Computer Science and Artificial Intelligence
* **Estimated learning time:** 30–40 minutes
* **Prerequisite knowledge:** Basic familiarity with computers and digital devices

### Learning Objectives
By the end of this lesson, learners should be able to:
1. Define computer hardware and explain why AI systems need it.
2. Describe the main functions of the Central Processing Unit (CPU), Graphics Processing Unit (GPU), Random Access Memory (RAM), and storage.
3. Distinguish between memory and storage.
4. Explain how these components work together when an AI system processes an input.
5. Apply their knowledge by tracing a simple AI task from input to output.

---

## 1. Introduction: Why does hardware matter?

Artificial Intelligence (AI) is used in many everyday applications, including chatbots, facial recognition, recommendation systems, and autonomous robots. Although these applications may appear to work through software alone, they depend on physical computer components to perform calculations, store information, and produce results.

* **Computer hardware** refers to the physical parts of a computer system that can be seen or physically handled. Examples include processors, memory modules, storage drives, cameras, keyboards, and displays.
* **Software** refers to the programs and instructions that tell the hardware what operations to perform. An AI application, for example, uses software to process an image and determine whether it contains a cat or a dog.

Hardware and software work together. Software defines the operations, while hardware executes those operations.

Consider an AI chatbot. When a user submits a question, the system must receive the text, represent it as data, process it using an AI model, and generate a response. These steps require computing resources such as processors and memory.

**The central question of this lesson is:**  
*How do the physical components of a computer enable an AI system to transform input data into a useful output?*

---

## 2. Four Essential Hardware Components

To understand how an AI system works, we must first understand four important hardware components: the CPU, GPU, RAM, and storage.

### 2.1 Central Processing Unit (CPU)
The **Central Processing Unit (CPU)** is a general-purpose processor that executes program instructions and coordinates many computer operations. It helps run the operating system, manage applications, perform calculations, and coordinate work between hardware components.

* *Analogy:* Think of the CPU as a **manager** who organizes the tasks that need to be completed.

In an AI system, the CPU may:
* Receive and prepare input data.
* Run the application and its instructions.
* Coordinate the movement of data between memory and the GPU.
* Manage the steps required to produce the final output.

### 2.2 Graphics Processing Unit (GPU)
The **Graphics Processing Unit (GPU)** is a processor designed to perform graphics operations and many other calculations efficiently. Modern GPUs are particularly useful for AI tasks that require large numbers of similar mathematical operations to be performed in parallel.

* **Parallel processing** means performing multiple calculations at the same time rather than completing every calculation one after another.

In AI systems, GPUs commonly help with:
* Training large machine-learning models.
* Running neural networks.
* Processing images and other numerical data.
* Generating predictions from trained models.

*Note:* A GPU does not replace the CPU. Both processors have important roles, and smaller AI workloads can often run effectively on a CPU.

### 2.3 Random Access Memory (RAM)
**Random Access Memory (RAM)** is the computer's temporary working memory. It holds data and instructions that programs need while they are running.

* *Analogy:* Think of RAM as a **worktable**. A larger worktable allows you to keep more materials close at hand while working.
* RAM is generally **volatile**, meaning its contents are lost when the system loses power.

### 2.4 Storage: SSD and HDD
**Storage** is the hardware used to retain information over time, including when a computer is switched off. Two common types are:
* **Solid-State Drive (SSD):** Stores data using flash memory and generally provides fast data access.
* **Hard Disk Drive (HDD):** Stores data magnetically on rotating disks and uses mechanical components.

---

## 3. Comparing the Four Components

| Component | Main function | Role in an AI system | Simple analogy |
| :--- | :--- | :--- | :--- |
| **CPU** | Executes instructions and coordinates tasks | Runs application logic and manages processing | Manager |
| **GPU** | Performs suitable calculations in parallel | Accelerates many AI computations | Team of workers |
| **RAM** | Temporarily holds active data | Provides working space for computation | Worktable |
| **SSD/HDD** | Retains data over time | Stores models, software, and datasets | Filing cabinet |

---

## 4. Worked Example: How an AI System Recognizes a Cat

* **Step 1: The user provides an input** — The user uploads a photograph of a cat.
* **Step 2: The system loads the required data** — Model files stored on the SSD are loaded into RAM or GPU memory so processors can access them.
* **Step 3: The input is prepared** — The image is resized and converted via **preprocessing** to match the model's expected format (e.g., 224 × 224 pixels).
* **Step 4: The model processes the image** — The CPU and GPU execute mathematical operations.

| Possible class | Model score |
| :--- | ---: |
| Cat | 0.92 |
| Dog | 0.06 |
| Rabbit | 0.02 |

*The cat class has the highest score.*

* **Step 5: The system generates an output** — The application interprets the scores and displays `Prediction: Cat`.

---

## 5. Learner Activity: Apply Your Understanding

* **Scenario:** A school wants to install an AI-powered security camera to identify humans entering a classroom.
* **Question 1:** Which component is responsible for coordinating the application and executing its general instructions? *(Answer: CPU)*
* **Question 2:** Why does the system need RAM? *(Answer: To hold active data and instructions while processing takes place)*

---


