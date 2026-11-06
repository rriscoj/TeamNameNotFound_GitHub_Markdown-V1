# CHAPTER 10 — Rules of the Game: States, Actions, and Rewards

## 1) The Foundation of AI Decisions

Previously, we learned that AI learns through trial and error, just like training a dog with treats. But how does the AI actually know what the "game" is? How does it know what moves are allowed?

To teach an AI to make decisions, computer scientists have to set up a formal environment—like a board game. To build this game, we use three fundamental building blocks: **States, Actions, and Rewards**.

Once you understand these three concepts, you understand exactly how an AI makes every single decision, from a robot vacuum cleaning a room to a self-driving car navigating traffic.

| Building Block | Simple Description | Board Game Analogy |
| :--- | :--- | :--- |
| **State** | The current situation or snapshot of the environment. | Where your game piece is on the board right now. |
| **Action** | The choices the AI can make from its current state. | Rolling the dice to move forward, or drawing a card. |
| **Reward** | The points (positive or negative) given for an action. | Landing on a snake (-10 points) or reaching the finish line (+100 points). |

<img width="1999" height="1125" alt="image" src="https://github.com/user-attachments/assets/937b407e-2208-4bbf-82a9-1b8d5ee094c0" />


> **Terminology — State:** A snapshot of the current situation the AI is in (its location in a maze, or the speed of a car).

> **Terminology — Action:** A specific move the AI can take ("move left," "hit the brakes," or "say hello").

> **Terminology — Reward:** A numerical score given to the AI after it takes an action, telling it if it did a good job or a bad job.

## 2) The Decision Loop

An AI doesn't just look at the world once. It plays the game in a continuous loop.

This is the **State-Action-Reward Loop**:

1. **Look at the State:** The AI checks where it is. (e.g., "The traffic light is red.")
2. **Choose an Action:** The AI picks a move based on its training. (e.g., "Press the brake.")
3. **Get a Reward:** The environment gives a score. (e.g., "+5 points for stopping safely.")
4. **New State:** The environment updates. (e.g., "The car is now stopped.")

<img width="420" height="420" alt="image" src="https://github.com/user-attachments/assets/f33d441f-b4b9-49dc-9b6a-c3cb708a466c" />


### Worked Example 1: The Grid-World Maze (Trial and Error)

<img width="353" height="315" alt="image" src="https://github.com/user-attachments/assets/957e7743-0b0a-462d-9598-e236c7e4ca0e" />

Imagine an AI trapped in a 4x4 grid. It wants to reach the exit (Dest.) in the bottom right corner. But it doesn't know the way yet! Let's watch it make a mistake by hitting a grey wall, learn from the penalty, and then follow the green path to win.

| Step | State (Where am I?) | Action (What do I do?) | Reward | New State |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Top-Left corner (Source) | Move Down | 0 points (Safe) | Row 2, Col 1 |
| **2** | Row 2, Col 1 | Move Down | -10 points (Hit a grey wall!) | Row 2, Col 1 (Didn't move) |
| **3** | Row 2, Col 1 | Move Right | 0 points (Safe) | Row 2, Col 2 |
| **4** | Row 2, Col 2 | Move Right | 0 points (Safe) | Row 2, Col 3 |
| **5** | Row 2, Col 3 | Move Down | 0 points (Safe) | Row 3, Col 3 |
| **6** | Row 3, Col 3 | Move Down | 0 points (Safe) | Row 4, Col 3 |
| **7** | Row 4, Col 3 | Move Right | +100 points (Reached Dest!) | Game Over (Win) |

**What this shows:** The AI made a mistake on Step 2 by trying to move Down into a grey wall. By getting a **-10 penalty**, it learned that moving Down from Row 2, Col 1 is a bad **Action**. It then chose to move Right instead, which allowed it to follow the safe green path and eventually earn the **+100 Reward**. This is exactly how AI learns through trial and error!

### Worked example 2: The Self-Driving Car

<img width="576" height="347" alt="image" src="https://github.com/user-attachments/assets/135cd1a5-2cbc-42ee-9245-6c004aa6b3f5" />

In the real world, the "game" is much faster and more dangerous.

| Step | State | Action | Reward | New State |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Approaching a red light at 50 km/h. | Accelerate | -100 points (Run a red light!) | Crashed into cross-traffic. |
| **2** | Approaching a red light at 50 km/h. | Brake | +10 points (Stopped safely) | The car stopped at the line. |

**What this shows:** If the car was trained well, it will choose "Brake" every time it sees the "Red Light" state because it knows the long-term reward is much higher.

## 3) The "State Space" and Hardware Limits

Previously, we learned that computers have memory and processing limits. This becomes incredibly important for AI because of the **State Space**.

The **State Space** is the total number of possible situations the AI could be in.

*   In a 4x4 maze, there are only **16 states**. A cheap CPU can easily calculate the best action for 16 states.
*   In a self-driving car, the state includes the speed, the steering angle, the location of 10 other cars, the color of the traffic light, and the weather. The state space is almost **infinite**.

To calculate the best action for millions of different states, the AI needs to process massive amounts of data. This is why we need powerful GPUs and TPUs!

<img width="503" height="491" alt="image" src="https://github.com/user-attachments/assets/01332227-b726-4df7-b82d-95d2e615201d" />


> **Terminology — State Space:** The collection of every possible state an AI can be in within its environment.

## 4) Soooo, why does this matter?

By breaking down an AI's behavior into States, Actions, and Rewards, we can train computers to solve incredibly complex problems.

*   **Why Netflix recommends movies:** **State:** Your watch history. **Action:** Recommend a movie. **Reward:** You click play (+1) or you scroll past (-1).

<img width="384" height="520" alt="image" src="https://github.com/user-attachments/assets/dd7fe6b9-ded3-4730-86f1-875b334405ae" />

*   **Why robots can play chess:** **State:** The layout of the pieces on the board. **Action:** Moving a knight. **Reward:** Checkmate (+100) or losing a queen (-50).

<img width="700" height="471" alt="image" src="https://github.com/user-attachments/assets/39bc45f7-f1dd-4e90-9331-7483c1167bf8" />

  
*   **Why AI can trade stocks:** **State:** The current market prices. **Action:** Buy or sell. **Reward:** Making money (+10) or losing money (-10).

  <img width="738" height="414" alt="image" src="https://github.com/user-attachments/assets/699ebbe6-a67c-4387-b0d9-d1c3c5661911" />


Understanding this "Rules of the Game" framework gives you the vocabulary to understand how AI actually decides what to do next.

## 5) QnA

**1. In an AI environment, what is the "State"?**
A. The score the AI gets for winning.
B. The current snapshot of the situation the AI is in.
C. The programming language used to build the AI.
D. The hardware the AI is running on.

**2. What is the difference between an "Action" and a "Reward"?**
A. An Action is the move the AI makes, while a Reward is the score it receives for that move.
B. An Action is the score it receives, while a Reward is the move it makes.
C. An Action is where the AI is located, while a Reward is what it sees.
D. They are exactly the same thing.

**3. Why does a self-driving car have a much larger "State Space" than a simple maze game?**
A. Because cars are bigger than mazes.
B. Because self-driving cars use Wi-Fi.
C. Because the car has to track speed, weather, traffic lights, and other cars all at once.
D. Because maze games don't have rewards.

**4. If an AI takes an action and gets a -50 reward, what should it learn?**
A. It should repeat that action immediately.
B. It should avoid taking that action in the future.
C. It should shut down completely.
D. It should ignore the reward.

**5. How does the State-Action-Reward loop work?**
A. Reward -> Action -> State.
B. State -> Action -> Reward -> New State.
C. Action -> State -> Reward -> Old State.
D. State -> Reward -> Action -> Game Over.

**6. Open-Ended: Training a Robot Chef**
You are designing an AI robot chef.
*   **State:** The temperature of the pan and the color of the food.
*   **Action:** Turn up the heat, turn down the heat, or take the food out.
*   **Reward:** +10 for perfectly cooked food, -20 for burnt food.

The robot leaves the food in the pan and it turns black. It gets a -20 reward. On its next try, how should the AI use its memory of the "State" and "Reward" to make a better decision?

**7. Open-Ended: Finding the Error**
A student says: "To train an AI to play basketball, we should only give it a +100 reward at the exact moment it scores a point. We don't need to give any rewards for dribbling or passing." Based on what you know about States, Actions, and Rewards, why might this make it very hard for the AI to learn?

## 6) Answer Key

1. **B** (The State is the current situation or snapshot of the environment).
2. **A** (An Action is the choice the AI makes; a Reward is the score it gets for making it).
3. **C** (A car must track many variables simultaneously, making the state space massive).
4. **B** (A negative reward is a penalty, meaning the AI should learn to avoid that action).
5. **B** (The loop is State -> Action -> Reward -> New State).
6. **Expected Answer:** The robot should remember the **State** (the pan was too hot/the food was black). It learned that the **Action** of leaving the food resulted in a -20 **Reward**. On the next attempt, when it sees the food getting dark, it should choose the action to "take the food out" or "turn down the heat" to get the +10 reward.
7. **Expected Answer:** This is a problem because the AI will only learn *after* it scores. If it doesn't get tiny rewards for dribbling or passing, it won't know that those **Actions** are necessary to reach the scoring **State**. It will just randomly throw the ball. Good AI training uses **intermediate rewards** (small points for good passes) to guide the AI toward the final goal.

## 7) References

1. Sutton & Barto, *Reinforcement Learning: An Introduction* — Chapter 3: Finite Markov Decision Processes (the formal math behind States, Actions, and Rewards).
2. IBM Research, "What is Reinforcement Learning?" — Explanation of the agent-environment interaction loop.
3. Massachusetts Institute of Technology (MIT), "Introduction to Deep Reinforcement Learning" — Explanation of State Spaces and Action Spaces.

## 8) Image References

Figure 1.1 https://www.kdnuggets.com/2023/07/reinforcement-learning-teaching-computers-make-optimal-decisions.html

Figure 2.1 https://snusforsale.com/loop/loop-red-chili-melon-strong/?srsltid=AYCX9vKizEvz_1pjIGW11EDCOFrcOngjCEhXqLGy8SbSYCOhMSDNoDTa

Figure 2.2 https://www.geeksforgeeks.org/dsa/tutorial-on-path-problems-in-a-grid-maze-or-matrix/

Figure 2.3 https://ingenia.org.uk/articles/how-do-self-driving-cars-navigate-roads-and-traffic/

Figure 3.1 https://www.geeksforgeeks.org/artificial-intelligence/state-space-search-in-ai/

Figure 4.1 https://www.facebook.com/brittany.simms.524035/posts/whats-some-good-movies-to-watch-on-netflix/1139352945321686/

Figure 4.2 https://blog.arduino.cc/2023/04/11/the-weird-and-wonderful-history-of-chess-playing-robots/

Figure 4.3 https://www.linkedin.com/pulse/can-ai-predict-market-what-traders-should-shouldnt-trust-cptconnect-htghf


## Notes

- **State** — A snapshot of the current situation the AI is in (e.g., location, speed, or temperature).
- **Action** — A choice or move the AI can make from its current state.
- **Reward** — A numerical score given to the AI after it takes an action (positive for good, negative for bad).
- **State Space** — The collection of every possible state an AI can be in within its environment.
- **Decision Loop** — The cycle of observing a state, taking an action, receiving a reward, and moving to a new state.
