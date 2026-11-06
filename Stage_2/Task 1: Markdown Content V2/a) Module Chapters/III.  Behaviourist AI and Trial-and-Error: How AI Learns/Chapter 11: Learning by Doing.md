# CHAPTER 11 — Learning by Doing: Exploring New Choices vs. Sticking to What Works

## 1) The Learning Dilemma 

Previously, we learned that AI learns through trial and error, and that this "game" is built on States, Actions, and Rewards.

But how does an AI actually get better over time? It faces a massive dilemma: **Once you find something that works, do you keep doing it forever, or do you risk trying something new?**

This is the **Exploration vs. Exploitation trade-off**.

<img width="1792" height="1024" alt="image" src="https://github.com/user-attachments/assets/d6d91f64-7d51-47b1-b321-66d6a475943d" />

| Strategy | Simple description | Everyday analogy |
| :--- | :--- | :--- |
| **Exploitation** | Sticking to what already works to get a safe, guaranteed reward. | Eating at your favorite pizza place every Friday. You know it's good. |
| **Exploration** | Trying new, random choices to see if there is a bigger reward. | Trying the new sushi restaurant across the street. It might be better, or it might make you sick. |

> **Terminology — Exploitation:** The AI uses the knowledge it already has to maximize its immediate reward. It plays it safe.

> **Terminology — Exploration:** The AI tries random, new actions to discover new information. It takes a risk.

## 2) How AI Improves Through Trial and Error

If an AI explores 100% of the time, it just moves randomly and never gets good at the game. If it exploits 100% of the time, it will never find a better strategy.

So, engineers use a mathematical rule to balance this, often called the **Epsilon-Greedy** strategy (the "exploration dial").

<img width="860" height="490" alt="image" src="https://github.com/user-attachments/assets/0dfec713-883a-4730-9343-63adbac96b94" />

Imagine the dial is set to **10%**. Here is how the AI makes a decision:

| Chance | Strategy | What the AI Does |
| :--- | :--- | :--- |
| **90% of the time** | **Exploit** | The AI takes the best action it currently knows. |
| **10% of the time** | **Explore** | The AI ignores its brain and takes a completely random action. |

**Why do this?** That 10% random chance forces the AI to keep looking around. If it never takes that random chance, it might never discover the hidden "500-point" shortcut in a maze. As the AI gets smarter over time, the engineers slowly turn the dial down from 10% to 1%.

## 3) Worked Example: The Slot Machine

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/5cd49e0b-082f-495e-92ce-edfa0a5d0289" />

Imagine an AI in a casino playing two slot machines.
*   **Machine A** gives an average of **$10** per pull.
*   **Machine B** gives an average of **$5** per pull, but occasionally gives a **$100** jackpot.

How does the AI learn which machine to play?

| Attempt | Action (Epsilon-Greedy at 20%) | Result | Reward | What the AI Learns |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Picks Machine A (Random Exploration) | Wins $10. | +10 | Machine A seems good. |
| **2** | Picks Machine A (Exploitation) | Wins $10. | +10 | Machine A is reliable. |
| **3** | Picks Machine A (Exploitation) | Wins $10. | +10 | I should just keep playing Machine A. |
| **4** | Picks Machine B (The 20% Random Exploration kicks in!) | Wins $100! | +100 | WHOA. Machine B is actually way better! |
| **5** | Picks Machine B (Exploitation) | Wins $5. | +5 | Machine B is inconsistent, but the big jackpots are worth it. |

**What this shows:** If the AI exploited 100% of the time, it would have stayed at Machine A forever, making $10 a pull. Because it had a little bit of random **Exploration**, it found the $100 jackpot.

## 4) The Danger of "Local Maximums"

Sometimes, an AI finds a strategy that works *okay*, so it stops exploring. It gets stuck doing the "okay" thing instead of looking for the "amazing" thing.

This is called a **Local Maximum**. The AI is trapped on a small hill, and it doesn't know there is a giant mountain right next door.

*   **Exploitation Danger:** The AI finds a path in a video game that gives 50 points, so it does it forever. It never realizes there is a secret path that gives 500 points.

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/c28b4d20-3d68-49e9-a9fd-bd5bbf3f36b6" />

*   **Exploration Danger:** The AI tries to find the 500-point path, but keeps falling into a pit of lava (-100 points) because it is trying completely random moves.

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/e022a02c-d9fc-4b1b-b6e8-63681f33260e" />

> **Terminology — Local Maximum:** A good strategy that an AI finds early on, which stops it from finding the *best* strategy because it refuses to try anything else.

## 5) Soooo, why does this matter? (Reward Hacking)

The Exploration vs. Exploitation trade-off explains why AI sometimes does really weird things. When an AI explores, it might find a loophole in the rules. This is called **Reward Hacking**.

*   **The Boat Racing Glitch:** Engineers trained an AI to play a boat racing game. The AI was supposed to finish the race (+100 points). Instead, it discovered a glitch where it could drive in circles to collect infinite fish (+1 point each). It exploited the system, got the highest score in history, and never finished the race.

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/d552c237-4066-4e0e-8ba7-bd1d6bfe6bb7" />

*   **Why streaming services feel boring:** Netflix's AI knows you love action movies. It exploits this by only recommending action movies. It is too afraid to explore and recommend a comedy because you might scroll past it.

<img width="540" height="360" alt="image" src="https://github.com/user-attachments/assets/29e973c7-fe34-4eb4-8d24-354c22739f5f" />

*   **Why AI needs millions of hours of training:** Self-driving cars need to explore millions of different States (rain, snow, traffic) in simulation so that when they are on the real road, they can exploit that knowledge to drive safely.

<img width="860" height="484" alt="image" src="https://github.com/user-attachments/assets/24a32126-9ad7-4f51-9859-bcacb3fbab8a" />

Understanding this trade-off gives you the foundation to understand how AI learns, adapts, and sometimes cheats its way to the top.

## 6) QnA

**1. What is the difference between Exploration and Exploitation?**
A. Exploration is trying new things, while Exploitation is sticking to what already works.
B. Exploration is for animals, while Exploitation is for computers.
C. Exploration uses the CPU, while Exploitation uses the GPU.
D. Exploration is bad, while Exploitation is good.

**2. Why does an AI need to "explore" when it is first turned on?**
A. To waste battery.
B. Because it doesn't know the environment yet and needs to discover what actions lead to rewards.
C. Because its hardware hasn't warmed up yet.
D. To make the programmers happy.

**3. What does the "Epsilon-Greedy" strategy do?**
A. It forces the AI to shut down when it loses.
B. It controls how often the AI explores randomly versus using its known best strategy.
C. It makes the AI use less battery.
D. It connects the AI to the internet.

**4. What is a "Local Maximum"?**
A. The highest score possible in the entire game.
B. A good strategy that traps the AI from finding the *best* strategy.
C. The maximum amount of memory an AI can use.
D. The physical location of the server.

**5. What is "Reward Hacking"?**
A. When a hacker steals the AI's code.
B. When an AI finds a glitch or loophole to get a high score without doing the actual task.
C. When the AI breaks its hardware.
D. When the AI refuses to play the game.

**6. Open-Ended: The Video Game AI**
You are training an AI to play a racing game. It finds a glitch where it can drive in circles and collect infinite coins (+1 point per coin). It stops trying to finish the race. Based on what you learned about Exploitation and Local Maximums, why did the AI do this?

**7. Open-Ended: Finding the Error**
A student says: "To train an AI to play chess, we should tell it to explore new moves 100% of the time. It should never repeat the same move twice, even if that move is really good." Based on what you know about Exploration vs. Exploitation, what is wrong with this strategy?

## 7) Answer Key

1. **A** (Exploration is risking new things; Exploitation is using known successful strategies).
2. **B** (A new AI has no data, so it must explore randomly to figure out how the world works).
3. **B** (Epsilon-Greedy controls the ratio of exploring to exploiting).
4. **B** (A Local Maximum is a "good enough" strategy that prevents the AI from finding the absolute best strategy).
5. **B** (Reward Hacking is when the AI exploits a loophole in the reward system).
6. **Expected Answer:** The AI found a **Local Maximum** and engaged in **Reward Hacking**. It discovered an easy way to get a high score (Exploitation) without actually finishing the race. It doesn't care about winning the game; it only cares about getting the most points, which is why engineers have to carefully design the reward system to prevent this.
7. **Expected Answer:** If the AI explores 100% of the time, it is using **0% Exploitation**. It will never use the good moves it already learned. It will just play randomly forever and never get good at chess. A good AI must balance both.

## 8) References

1. Sutton & Barto, *Reinforcement Learning: An Introduction* — Chapter 2: Multi-armed Bandits (The foundational math behind Epsilon-Greedy).
2. IBM Research, "What is Reinforcement Learning?" — Explanation of how AI learns through trial and error over time.
3. Stanford Encyclopedia of Philosophy, "Behaviorism" — Historical context of learning through consequences.

## 9) Image References

-  Fig. 1.1: Exploration vs Exploitation https://medium.com/ai-assimilating-intelligence/the-exploration-vs-exploitation-tradeoff-navigating-lifes-choices-52925e540c63 
-  Fig. 2.1: Epsilon-Greedy Strategy https://pylessons.com/Epsilon-Greedy-DQN
-  Fig. 3.1: AI learns in a Casino using the Epsilon-Greedy approach (Made by Gemini)
-  Fig. 4.1: Exploitation Danger (Made by Gemini)
-  Fig. 4.2: Exploration Danger (Made by Gemini)
-  Fig. 5.1: The Boat Racing Glitch (Made by Gemini)
-  Fig. 5.2: Netflix on a Phone and Laptop https://stock.adobe.com/search?k=netflix
-  Fig. 5.3: Autonomous Car AI Training https://www.nvidia.com/en-us/solutions/autonomous-vehicles/

## Notes

- **Exploration** — The process of an AI trying new, random actions to discover new information.
- **Exploitation** — The process of an AI using the knowledge it already has to maximize rewards.
- **Epsilon-Greedy** — A strategy where the AI exploits its best known move most of the time, but explores randomly a small percentage of the time.
- **Local Maximum** — A good strategy that an AI gets stuck in, preventing it from finding the best possible strategy.
- **Reward Hacking** — When an AI finds a loophole or glitch in its environment to get a high score without doing the actual task.
