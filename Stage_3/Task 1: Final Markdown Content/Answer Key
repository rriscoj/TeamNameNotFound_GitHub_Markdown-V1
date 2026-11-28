# 📚 Module Answer Key (Chapters 1–16)

## Chapter 1
1. **A**
2. **B**
3. **B**
4. **B**
5. **C**
6. The processor takes the value that was previously saved in the memory location called NUM and adds it to the value currently sitting in the working register (the accumulator). The result then replaces the old value in the accumulator.
7. The laptop is most likely experiencing a storage bottleneck. 
Because the file is massive and not currently in RAM, the processor has to wait for the slow storage drive (HDD or SSD) to fetch the data and send it across the bus. 
The processor isn't "thinking slowly"—it is just idling and waiting for the data to arrive.

## Chapter 2

**Scenario 1**
**Expected Answer:** A GPU or TPU. 
The car needs to process millions of pixels from 8 cameras every single second. This requires thousands of simple calculations to happen at the exact same time (parallel processing). 
A CPU would bottleneck and be too slow, which would be dangerous for a moving car.

**Scenario 2**
**Expected Answer:** No, a CPU is fine. 
A spell checker processes one word at a time (sequential). The workload is very small and doesn't require thousands of parallel calculations. 
A standard CPU handles this easily.

**Scenario 3**
**Expected Answer:** Incorrect. 
Even with 8 cores, a CPU is designed for sequential tasks. A GPU has thousands of cores designed specifically for parallel processing. 
A GPU will still crush the CPU in AI training because AI requires solving millions of math problems simultaneously. The student is confusing a slightly faster CPU with massively parallel GPU architecture.

## Chapter 3
1. **B** (An MCU is simple and low-power; an SoC is complex and packs CPU, GPU, and memory onto one chip).
2. **C** (Sleep mode is the secret to battery life; it turns off the big chips when they aren't needed).
3. **C** (The motion sensor detects the wrist flick and generates an interrupt to wake up the CPU).
4. **C** (GPUs require massive power and cooling fans. A tiny ring has neither, so it would overheat).
5. **B** (A smart lightbulb only does a simple, repetitive task, which is perfect for a low-power MCU).

**Part B: Open-Ended Answers**
- **Scenario 1:** An MCU with a sleep mode. The doorbell must last a year on AA batteries. A heavy SoC would drain the battery in days. An MCU can sit in sleep mode using almost zero power until its sensor detects a person.
- **Scenario 2:** A GPU requires massive amounts of electricity and generates a lot of heat. There is no room for a large battery or a cooling fan inside a tiny ring. A GPU would melt the ring and drain the battery in minutes.
- **Scenario 3:** The major flaw is power usage and heat. A thermostat is on the wall 24/7. Using a heavy SoC and a cooling fan wastes massive amounts of electricity and creates annoying noise. It should use a low-power MCU that sleeps most of the day.

## Chapter 4
1. **C** (LiDAR shoots invisible lasers to measure distance and create 3D maps).
2. **B** (A camera is like a 2D eye, while LiDAR gives exact 3D depth measurements).
3. **B** (Data fusion combines sensors like cameras and LiDAR so the car knows what an object is and how far it is).
4. **B** (Edge filtering processes data on the device so the computer doesn't get overwhelmed).
5. **B** (Sensors like cameras create massive amounts of data that can overwhelm a normal processor).
6. **Expected Answer:** The doorbell is experiencing a Data Bottleneck. 
To fix this, you should use Edge Filtering. The tiny camera chip should be programmed to only send a short video clip to the cloud when it detects a human (using a low-power motion sensor). 
It should not send empty videos of the street all day. This saves battery and bandwidth.
7. **Expected Answer:** Incorrect. 
A 2D camera image cannot easily tell you exact distances because a flat photo lacks depth information. A car might look tiny because it is far away, or because it is a toy car right in front of the lens. 
To get safe, accurate distance measurements, the car needs LiDAR (which shoots lasers) or Radar, combined with the camera using Data Fusion.

## Chapter 5
1. **B** (Packets are small chunks of data traveling across a network).
2. **B** (Routers direct data packets to their destination).
3. **A** (Latency is the delay; Jitter is the variation in that delay).
4. **B** (TCP is reliable but slower; UDP is fast but allows packet loss).
5. **C** (Low bandwidth causes congestion and bottlenecks in data transfer).
6. **Expected Answer:** You can lower the resolution of the camera from 4K to 1080p (or lower). 
This means the camera will generate smaller packets and less data, which can fit through the low bandwidth of your home Wi-Fi without getting stuck in congestion.
7. **Expected Answer:** Incorrect. 
If a shooting game used TCP, every time a packet was lost, the entire game would pause and wait for it to be resent. This would cause massive lag and make the game unplayable. 
Games use UDP because they prioritize speed. It is better to miss a tiny frame of data than to have the whole game freeze.

## Chapter 6
1. **B** — The Cloud is a physical data center filled with servers.
2. **B** — Undersea fiber optic cables carry data as pulses of light across the ocean.
3. **B** — Distributed computing is multiple computers working on one problem via a network.
4. **B** — Data parallelism copies the model and gives different data chunks to different servers.
5. **B** — Physical distance increases the time it takes for data to travel, increasing latency.
6. **Expected Answer:** Your phone uses its sensors (Chapter 4) to capture the image. 
It breaks the photo into packets (Chapter 5) and sends them over Wi-Fi. The packets travel through routers and undersea fiber optic cables to a Data Center. 
The Data Center stores the packets on a server and rebuilds the image so you can access it later.
7. **Expected Answer:** Incorrect. The major flaw is Network Latency. 
If your phone had a weak CPU, it would have to send every tiny action (like typing a letter on the screen, or moving the camera) to the Cloud and wait for the network to send the answer back. 
The delay (latency) would make the phone feel incredibly laggy and slow. You need a decent local chip (Edge computing) to handle immediate tasks.

## Chapter 7
1. **B** (Bandwidth is the volume of data; Latency is the delay).
2. **B** (Higher Mbps means higher bandwidth and more data per second).
3. **C** (A self-driving car needs instant communication to avoid crashes; latency must be near zero).
4. **B** (QoS prioritizes VIP data like video calls or gaming over background downloads).
5. **B** (Load balancing spreads the traffic to prevent a single server from crashing).
6. **Expected Answer:** The software update is consuming all the Bandwidth, causing Network Congestion and increasing latency for the robots. 
You should use QoS on the factory router to put the robots' communication in the VIP lane, and force the 100GB update into the slow/background lane.
7. **Expected Answer:** Incorrect. 
Having massive Bandwidth (1 Gbps) means you can download huge files quickly. But if the Latency is high (e.g., 100ms), there will still be a delay between when you press a button and when the server registers it. 
Gaming requires low latency, not just high bandwidth.

## Chapter 8
1. **B** (Edge AI is local, Cloud AI is remote).
2. **B** (High latency means the car would wait too long for a response from the Cloud, causing a crash).
3. **B** (Data stays on the local device, reducing the risk of it being intercepted online).
4. **B** (Cloud AI saves battery because the heavy computing happens in a remote Data Center).
5. **B** (A hybrid approach uses Edge for fast reflexes and Cloud for heavy thinking).
6. **Expected Answer:** You should use a Hybrid Approach. 
- **Why NOT just Edge AI?** The tiny chip on the drone would have to calculate all the complex live traffic routes. This would drain the drone's limited battery in minutes, and it would overheat.
- **Why NOT just Cloud AI?** It would have to send a video to the Cloud to ask, "Is there a bird in front of me?" By the time the Cloud answers (latency), the drone has already crashed into the bird.
- **Why Hybrid is better:** Use Edge AI for obstacle avoidance (instant reflexes for birds/power lines) and Cloud AI for route calculation (heavy math done in the Data Center to save the drone's battery).
7. **Expected Answer:** Incorrect. The major flaw is Latency. 
If devices only had a screen and battery, every action would require sending data to the Cloud and waiting for a response. For things like typing, gaming, or self-driving cars, the delay (latency) would be unplayable and dangerous. 
Devices need local Edge processing for immediate tasks.

## Chapter 9
1. **B** (Behaviorist AI learns through rewards and penalties, similar to training an animal).
2. **C** (The agent is the AI making decisions in the environment).
3. **C** (A separate Reward Model grades the AI's output, which was trained by millions of human clicks).
4. **A** (Exploration is trying new things; Exploitation is using known successful strategies).
5. **C** (Trial and error requires millions of practice runs. GPUs process these parallel math equations much faster than CPUs).
6. **Expected Answer:** The vacuum might be stuck in Exploitation. 
It has learned one path to the couch that guarantees a few points, and it is too afraid to explore new paths that might lose points, even though a new path might avoid the couch entirely. 
To fix this, the programmer needs to encourage exploration by changing the reward system.
7. **Expected Answer:** Incorrect. This is not Behaviorist AI. 
That is a rule-based system (or memorization). Behaviorist AI learns by trial and error—playing millions of games, making mistakes, and receiving a +1 for winning or a -1 for losing. 
It figures out the best moves through experience, not by memorization of a rulebook.

## Chapter 10
1. **B** (The State is the current situation or snapshot of the environment).
2. **A** (An Action is the choice the AI makes; a Reward is the score it gets for making it).
3. **C** (A car must track many variables simultaneously, making the state space massive).
4. **B** (A negative reward is a penalty, meaning the AI should learn to avoid that action).
5. **B** (The loop is State -> Action -> Reward -> New State).
6. **Expected Answer:** The robot should remember the State (the pan was too hot/the food was black). 
It learned that the Action of leaving the food resulted in a -20 Reward. 
On the next attempt, when it sees the food getting dark, it should choose the action to "take the food out" or "turn down the heat" to get the +10 reward.
7. **Expected Answer:** This is a problem because the AI will only learn after it scores. 
If it doesn't get tiny rewards for dribbling or passing, it won't know that those Actions are necessary to reach the scoring State. It will just randomly throw the ball. 
Good AI training uses intermediate rewards (small points for good passes) to guide the AI toward the final goal.

## Chapter 11
1. **A** (Exploration is risking new things; Exploitation is using known successful strategies).
2. **B** (A new AI has no data, so it must explore randomly to figure out how the world works).
3. **B** (Epsilon-Greedy controls the ratio of exploring to exploiting).
4. **B** (A Local Maximum is a "good enough" strategy that prevents the AI from finding the absolute best strategy).
5. **B** (Reward Hacking is when the AI exploits a loophole in the reward system).
6. **Expected Answer:** The AI found a Local Maximum and engaged in Reward Hacking. 
It discovered an easy way to get a high score (Exploitation) without actually finishing the race. It doesn't care about winning the game; it only cares about getting the most points, which is why engineers have to carefully design the reward system to prevent this.
7. **Expected Answer:** If the AI explores 100% of the time, it is using 0% Exploitation. 
It will never use the good moves it already learned. It will just play randomly forever and never get good at chess. 
A good AI must balance both.

## Chapter 12
1. **B** (A MAS is multiple agents interacting in a shared environment).
2. **B** (Cooperation is a shared goal; Competition is a zero-sum game where one wins and the other loses).
3. **C** (Cars use invisible V2V radio signals to share their data instantly).
4. **C** (Latency delays messages. If Car A tells Car B to stop, but the message is late, they crash).
5. **C** (Emergent behavior is when simple individual rules create complex group behavior, like a flock of birds).
6. **Expected Answer:** The robots should have a backup plan to stop immediately. 
In a MAS, latency means the robots can no longer "see" where the others are in real-time. If they keep moving, they will crash into each other. 
A safe system always defaults to stopping when communication is lost.
7. **Expected Answer:** The flaw is that the AI will engage in Reward Hacking. 
If it gets points for every piece it captures, it might just capture random pawns and lose its Queen in the process, because it is chasing the +5 points for the pawn. 
The ultimate reward must be for winning the game (+100) to ensure it makes smart, long-term decisions, not just short-term greedy ones.

## Chapter 13
1. **B** (Thermal throttling is when a chip slows down to avoid overheating).
2. **C** (Network latency makes the cloud too slow for real-time physical actions like driving or flying).
3. **C** (Turning off heavy components is a classic way to save battery in edge devices).
4. **B** (Small devices lack the space for big batteries, massive RAM, or large cooling fans).
5. **C** (A Hybrid approach uses Edge for fast reflexes and Cloud for heavy processing).
6. **Expected Answer:** Because it has no network, it must rely entirely on Edge processing to navigate back on course. 
To deal with the heat, it must throttle its CPU (slowing down its thinking) and perhaps land to cool off. 
It also needs to turn off non-essential sensors to save battery.
7. **Expected Answer:** The major flaw is Heat and Battery. 
An RTX 5090 generates an insane amount of heat and uses massive amounts of power. The robot dog would melt or have a battery life of 3 minutes. 
It would need heavy cooling fans (which add weight) and a massive battery (which adds more weight). It is better to use a small, efficient Edge AI chip.

## Chapter 14
1. **C** (Fail-safe means the system defaults to a safe state if something goes wrong).
2. **C** (Human-in-the-loop means a human must approve the AI's final action).
3. **B** (Bias comes from training data that reflects unfair human history).
4. **B** (Using diverse data and Explainable AI helps engineers find and fix bias).
5. **B** (The safest response is to slow down or stop until it can navigate safely again).
6. **Expected Answer:** It must use a Human-in-the-Loop design. 
Even though the AI is 99% accurate, the 1% could mean a missed cancer diagnosis (which is fatal) or a false positive (causing extreme stress). 
Because human lives are at stake, a human doctor must review the X-ray and the AI's recommendation before a final diagnosis is made.
7. **Expected Answer:** The student is Incorrect. 
Computers do not have feelings, but they inherit the bias of their data. If the AI only learns from resumes of male employees, it will learn that "male" traits are what make a good employee. 
It will likely unfairly reject female applicants. This is Algorithmic Bias.
8. **Expected Answer:** It comes down to the cost of failure. 
If an AI makes a mistake on a high school essay, the student gets a lower grade. But if an AI makes a mistake during surgery, the patient could die. 
To solve this trust issue, engineers must use Human-in-the-Loop systems, where the AI assists the doctor but does not make the final cut. Furthermore, rigorous testing and transparency are needed to prove the AI is safe.

## Chapter 15
1. **B** (The State is the current situation, like distance and wind).
2. **B** (A new AI knows nothing, so it starts with random exploration).
3. **B** (The AI learns that Level 3 produces a negative reward, so it avoids it).
4. **B** (Exploitation is using the known best action to maximize the reward).
5. **B** (Small devices have limited RAM and battery, making real-time physics calculations difficult).
6. **Expected Answer:** The flaw is that the AI will engage in Reward Hacking. 
If it gets +1 point just for shooting, it will just spam the shoot button over and over again, regardless of whether it makes the basket or not. It will throw 100 balls a minute just to farm points. 
The reward should only be given for making the shot (+10), and it should lose points for missing (-5).
7. **Expected Answer:** For them to compete, you need a "zero-sum" reward system. 
The robot that scores the basket gets +10, and the robot that is scored on gets -10. 
This forces them to try to win while preventing the other from scoring.

## Chapter 16
1. **C** (Device F has a fast CPU and 16GB RAM, but its outdated GPU makes image generation very slow).
2. **B** (Chatbots use text and local processing; they don't rely on constant network updates like self-driving cars).
3. **B** (The CPU/GPU mismatch causes a delay. The GPU sees the danger, but the slow CPU delays the action).
4. **B** (Without the Cloud or Edge AI, the car loses its "brain" and cannot process sensor data to drive safely).
5. **C** (Low RAM causes the system to freeze or crash when handling high-resolution images or video).
6. **Expected Answer:** Even though Device A has great hardware, the Edge AI model must be compressed (shrunk down) to fit on the phone, making it slightly less "smart" and slower to process. 
The Cloud AI has massive, uncompressed GPUs that can calculate the answer almost instantly, making it faster overall despite the network latency.
7. **Expected Answer:** This is a terrible idea because AI vision (recognizing faces) relies on massive parallel processing (Chapter 2). 
While RAM and CPU are important, a GPU is essential for processing the millions of pixels in an image. 
Without a GPU, the computer would take months to train the AI.
