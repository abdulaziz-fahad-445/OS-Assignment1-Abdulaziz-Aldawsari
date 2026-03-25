# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A process, to put it simply,is a fully autonomous program with its own separate memory sapce, As a result, generating amd switching between them requires a significant amount of system resources, A therad,on the other hand, has a substantiallu smaller creation overhead because it oprerates inside that process and shares the smae memory and resouces. Because threads allowed all simulated processes ti directly share the ProcessQueue and update the static contextswitch counter, we decided to employ them for this simulation by making the process class implement Runnable. The speed of our Round-Robin scheduler would have been severly hampered if we had attempted to construct genuine distinct processes instead. This would have required setting up complicated IPC only to share those basic variables]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[When a process doesn't finish its execution within the assigend time quantum , the scheduler triggers a context switch to ensure fairness, In my code , the running thread is interrupted , and I use the addProcessToQueue method to move it from the cpu back to the end of the ready queue .This allows the next process in line to start its turn while the interrupted one waite to reach the front again. You can see this logic in my output where the remaining time is calculated, and the process is requeued immediately after yielding the CPU]

Example from my output:
```
[ ? P2 executing quantum [3000ms]
  ? Quantum progress: [███████████████] 100%
  ? P2 completed quantum 3000ms │ Overall progress: [████████████░░░░░░░░] 63%
     Remaining time: 1694ms
  ? P2 yields CPU for context switch

  ? P2 Priority: 4 enters the ready queue │ Burst time: 4694ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P4 ? P5 ? P6 ? P7 ? P8 ? P9 ? P10 ? P11 ? P12 ? P13 ? P14 ? P15 ? P16 ? P2]]
```

**Explanation of example:**
[Looking at this snippet, P2 had a total burst time of 4694ms , but the quantum limit was only 3000ms, Since it only reached 63% progress, it still 1694ms left to go. My program -yield cpu for context switch- and, as shown in the ready queue box, P2 was moved to the very end of the list behind P16, This allows the next process in line, P4, to start its turn while P2 waits for its next cycle]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[In my simulation, P1 moves through several states during its lifecycle. Even though it finished its work very quickly in my specific run, we can still trace every stage it went through]

1. **New**: [P1 is in the new state the moment it's created using the > new process() constructor in the code. At this point, the program has assigned it a burst time 2593ms, but the thread hasn't actually started running yet]

2. **Runnable**: [Once the process is added to the processqueue, it becomes Runnable. In my output, you can see it was sitting at the front of the ready queue box, which means it was alive and ready to works, just waiting for scheduler to give it the CPU]

3. **Running**: [This state happens when the scheduler picks P1 and calls is run() method. My terminal shows this clearly with the message - P1 executing quantum [2593ms], Where the thread is actively using the cpu to complete its task]

4. **Waiting**: [Noramlly , a process enters a waiting or ready state if it's interrupted by a context switch finishing. Since P1 finished in its very first turn, it didn't have to wait after starting, but it technically-watied-in the queue ealier while the system was starting up]

5. **Terminated**: [This is the final state where the thread's work is done.Because P1's burst time less than the quantum , its remaining time hit 0ms immediately, and the program printed ? P1 finished execution, neaning the thread has officially exited the system]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Multi-tab /browsing-Google]

**Description**: 
[When you have 10 tabs open at once e.g.-outlook-discord-youtube, each tab runs as aseparete thread or process. The browser has to manage all of them so one tab doesn't -freeze- the whole window]

**Why Round-Robin works well here**: 
[It provides responsiveness. By giving each tab a tiny silce of time quantum , the browser ensures that your music keeps playing in one tab while you are scorlling through a news site in another . Even if one page is -heavy- and loading lots of images, Round-Robin prevents it from stealing all the cpu time from your other tabs]

### Example 2: [ Online Gaming Servers /Multiplayer Matchmaking]

**Description**: 
[In a game server with 40 players, the server needs to update the position and actions of every player constantly to keep the game-synced-]

**Why Round-Robin works well here**: 
[It ensures fairnees and low latency. The server uses Round-Robin to quickly cycle through every players data packet. This way, no single player gets a faster update then others, and everyone experiences a smooth game without -lag- caused by the server getting stuck on one person's connection]

---

## Summary

**Key concepts I understood through these questions:**
1. Fairness in scheduling: How the Round-Robin algorthm prevents any single task from-hogging-the CPU
2. Context switching overhead: The cost of saving and loading thread states when the time quantum ends 
3. Thread lifecycle: How a process moves from being-New-to -Terminated-after finishing its burst time

**Concepts I need to study more:**
1. Stravation in priority scheduling: What happens to low priority tasks when high priority ones keep coming 
2. Optimal quantum sizing: How to choose the perfect time slice so the system doesn't waste too mush time switching
