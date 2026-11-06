# CHAPTER 15 — Mini-Project: Building a Simple Decision Game 

## 1) Project Overview 

Previously, we learned how AI learns:

*   It learns through trial and error.
*   It uses States, Actions, and Rewards to make decisions.
*   It balances Exploration (trying new things) and Exploitation (using what it knows) to find the best strategy.

Now, it's time to put it all together. Instead of a confusing maze, we are going to design a **Robot Basketball Game**. This is exactly the kind of simulation used to train AI before putting it into real robots.

## 2) The Game Rules: Setting up the Environment

Imagine a robot standing on a basketball court, 5 meters away from the hoop. The robot has a mechanical arm that can shoot the ball with different levels of power.

Here are the rules (the three building blocks):

*   **State:** The robot's situation (e.g., "I am 5 meters away from the hoop, and the wind is blowing left.").
*   **Action:** The robot can choose a shooting power. Let's give it 3 options:
    *   **Power Level 1:** Soft throw
    *   **Power Level 2:** Medium throw
    *   **Power Level 3:** Hard throw
*   **Reward:** 
    *   If the ball goes in the hoop: **+10 points** (Swish!)
    *   If the ball misses: **-5 points** (Bounce off the rim)

> **Terminology — Simulation:** A computer program that mimics real-world physics so an AI can practice without breaking anything in real life.

## 3) Worked Example: Tracing the AI's First Attempts

When the AI is first turned on, it knows nothing about basketball. It starts by using **Exploration** (choosing actions randomly). Let's trace its first 4 shots.

| Shot | Action (What the AI chooses) | Result (What happens) | Reward | What the AI Learns |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Chooses **Power Level 1** (Random guess) | The ball is too weak and falls short. | -5 | Level 1 is not enough power. |
| **2** | Chooses **Power Level 3** (Random guess) | The ball is too strong and hits the backboard. | -5 | Level 3 is too much power. |
| **3** | Chooses **Power Level 1** (Still exploring) | Falls short again. | -5 | Okay, I'm sure Level 1 is bad. |
| **4** | Chooses **Power Level 2** (Random guess) | The ball goes perfectly through the hoop! | +10 | **WOW! Level 2 works!** |

**What this shows:** After 4 shots, the AI has learned that **Power Level 2** is the magic number.

### The Next 10 Shots (Exploitation)
Previously, we learned about Exploitation. Now that the AI knows Level 2 works, it will stop guessing. For its next 10 shots, it will use **Power Level 2** every single time to keep getting that +10 reward.

## 4) The Hardware Reality 

In a real-world device, this simple game becomes much harder because of **Hardware Limits**.

If this AI was running inside a real robot with a tiny battery, it would face a problem: It takes a lot of battery and processing power to calculate physics (wind, gravity, angle) in real-time.

**How to fix this:**

*   **Offloading to the Cloud:** The robot's Edge chip just detects the distance. It sends that data to the Cloud, which uses massive GPUs to calculate the perfect shooting power, and sends the answer back.
*   **Model Compression:** Shrink the AI model so it runs directly on the robot's local chip without draining the battery.

## 5) Soooo, why does this matter?

This simple basketball game is exactly how multi-million dollar AI systems are trained.

*   **Why self-driving cars use simulations:** Before a self-driving car goes on a real road, it plays a game in a computer simulation millions of times. The "hoop" is staying in the lane, and the "miss" is crashing.
*   **Why warehouse robots use this:** Amazon trains its warehouse robots using games to figure out the perfect speed and angle to grab items without dropping them.
*   **Why video game NPCs use this:** Enemy AI in shooting games use this exact logic (State: player is hiding behind a wall. Action: throw grenade. Reward: player takes damage).

## 6) QnA

**1. In the Robot Basketball game, what is the "State"?**
A. The robot's shooting power.
B. The robot's distance from the hoop and the wind speed.
C. The +10 points.
D. The basketball.

**2. Why did the AI choose Power Level 1 on its very first shot?**
A. Because it knew Level 1 was the best.
B. Because it was using Exploration (random guessing).
C. Because it wanted to lose points.
D. Because the battery was low.

**3. If the AI shoots (Power Level 3) and the ball hits the backboard, what should the AI learn?**
A. Power Level 3 is the best.
B. Power Level 3 is too strong and should be avoided.
C. It should never shoot again.
D. It needs more points.

**4. After the AI learns that Power Level 2 works, it uses it 10 times in a row. What is this called?**
A. Exploration
B. Exploitation
C. Hardware Limits
D. Network Latency

**5. How do Hardware Limits affect this basketball robot?**
A. It makes the robot taller.
B. It limits how much physics math the robot can do on its local chip without draining the battery.
C. It makes the ball bounce higher.
D. It forces the robot to use Power Level 3.

**6. Open-Ended: The Broken Reward System**
Imagine you are designing the rules for this game. You decide to give the AI **+1 point every time it shoots the ball**, and **+10 points if it gets a swish**. 
Based on what you know about Reward Hacking, what is the flaw in this design? How will the AI behave?

**7. Open-Ended: The Multi-Agent Game**
You put **two** basketball robots on the court at the same time. They are playing against each other in a game of 1-on-1. How does the reward system need to change to make them **compete** instead of cooperate?

## 7) Answer Key

1. **B** (The State is the current situation, like distance and wind).
2. **B** (A new AI knows nothing, so it starts with random exploration).
3. **B** (The AI learns that Level 3 produces a negative reward, so it avoids it).
4. **B** (Exploitation is using the known best action to maximize the reward).
5. **B** (Small devices have limited RAM and battery, making real-time physics calculations difficult).
6. **Expected Answer:** The flaw is that the AI will engage in **Reward Hacking**. If it gets +1 point just for shooting, it will just spam the shoot button over and over again, regardless of whether it makes the basket or not. It will throw 100 balls a minute just to farm points. The reward should only be given for making the shot (+10), and it should lose points for missing (-5).
7. **Expected Answer:** For them to compete, you need a "zero-sum" reward system. The robot that scores the basket gets **+10**, and the robot that is scored on gets **-10**. This forces them to try to win while preventing the other from scoring.

## 8) References

1. Sutton & Barto, *Reinforcement Learning: An Introduction* — Chapter 6: Temporal-Difference Learning (The math behind learning from rewards).
2. IBM Research, "What is a Simulation Environment?" — Explanation of simulated environments for training AI.
3. OpenAI, "Emergent Tool Use From Multi-Agent Autocurricula" — How AI interacts in shared environments.

## 9) Image References

*(Add images here of a robot shooting a basketball, a basketball hoop, and a physics simulation screen)*
1. 
2. 
3. 

## Notes

- **Simulation:** A computer program that mimics real-world physics so an AI can practice without breaking anything in real life.
- **State:** The AI's current situation (e.g., distance from the hoop).
- **Action:** The move the AI makes (e.g., choosing Power Level 1, 2, or 3).
- **Reward:** The points given for a successful action (+10).
- **Penalty:** The negative points given for a failed action (-5).
- **Reward Hacking:** When an AI finds a loophole in the rules to get a high score without doing the actual task.
