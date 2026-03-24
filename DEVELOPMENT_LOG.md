# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 18, 2026 and 5:00 PM]
**What I did**: 
Forked the repository and set up my student ID
**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 150 to my actual ID (445050097)
- Compiled and ran the program successfully
**Challenges**: 
 At first, I didn’t know how to download the assignment from GitHub and use it in VS Code.
**Solution**: 
I cloned the repository and opened the project folder in VS Code.
**Time spent**: 40 minutes

---

### Entry 2 - [March 19, 2026 and 7:40 PM]
**What I did**: 
I incorporated a priorty-based feture into the process model and randomized its genration 
**Details**: 
- Modified the process class to include a priority field (integer 1-5)
- The process constructor now accept the priority  value as a parameter
- I used randomness, The main procedure uses nextInt(5)+1 to generate a   unique priority for each process
- addProcessToQueue method now display the priority along with the process name
**Challenges**: 
Adding the priority field to the constructor generted issues in the main proedure until all process instantiations were update with the new input 
**Solution**: 
Improved the process constructor signature and made sure the main loop produces a random priority before generating the process object
**Time spent**: 1 Hour

---

### Entry 3 - [March 22, 2026 and 5:35 AM]
**What I did**: 
Added a static counter to track the total number of context transitions executed by the scheduler  
**Details**: 
- To keep track of the overall count I added a static integer context switch variable to the schedulersimulation class 
- The incerment logic context++, is inserted within the main while loop, just before each therad starts 
- I added a final output statement display the entire counter e.g. "Total context swiches: 36"
**Challenges**: 
- The goal is to use java threads to detemine the switch point in a Round Robin simulation 
- I needed to make sure the counter didn’t incerment while the queue was empty or during internal process steps
**Solution**: 
Adding the counter after procsessQueue.poll() ensures the any change from "ready" to "running" is regarded as a context switch 
**Time spent**: 40

---

### Entry 4 - [March 24, 2026 and  1:00 AM]
**What I did**: 
I worked on tracking the processes and saving their info
**Details**: 
- I added Stime and Wtime in the process class, one for the creation time one for waiting time 
- I used currentTimeMillis() in the contructor to get the time when each process is created 
- Also I made an Arraylist<Process> to keep all processes from the start , so even after they finish I stil have their data
**Challenges**: 
The problem was the processQueue keeps changing , and once a process finishes it gets removed , so I couldn’t use it to print the final summary
**Solution**: 
So I just saved all processes in the Arraylist from the beginning , and used it later to print the summary
**Time spent**: 1 Hour

---

### Entry 5 - [March 24, 2026 and  2:00 AM]
**What I did**: 
I finished the waiting time math made the final table
**Details**: 
- I used the formula (Current time -Creation time ) - Burst time to calculate the waiting time each process
- At the end, I used an enhanced for-Loop  to go through the Arraylist and print the summary table > Name, Burst , Waiting time 
**Challenges**: 
The waiting time numbers were way off at first because I forgot to subtract the burst time from the total time , so the numbers didn't make sense
**Solution**: 
I fixed the formula and ran the code again until the result in the terminal looked correct and logical
**Time spent**: 1:15 Hour

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [6:10 hours]

**Most challenging part**: 
The messiest part was the terminal output. At first the program kept printing the same process names every time they run , so the output was full of repeated lines and hard to read. I couldn’t use it to make a final table. After that I used an Arraylist > I named Abdulaziz to store all processes  once from the beginning, so I can just print them at the end in a clean way
**Most interesting learning**: 
I liked how the context switching counter works. Every time the cpu moves from one process to another, The counter increments, so i could see how often switching happens, Also using System.currentTimeMillis() helped me calculate real waiting time instead of random numbers 
**What I would do differently next time**: 
I wasted time trying to fix the printing inside the loop.
The better ieda was to store the data and print it later.
Next time I will plan this form the beginning