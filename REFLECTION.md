# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

[In the assignment, I learned how multithreading actually works in a program, not just the theory. I saw how a single process can split into different threads to multiple things at the same time, which makes the app much faster. I spent a lot of time looking at the different threads states like-Runnable- and -Waiting- while I was coding the simulation. It was interesting to see how the java code manage these states to keep the cpu busy. I also realized that managing many threads isn't easy because the system has keep switching between them]

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

[To be honset, the biggest headache wasn't the multithreading theory itself, but just trying to keep my code from becoming a total meess. I used Arraylist to store everything for the final table, and trying to keep synchronized with the actual execution queue eas much trichier than I through it would be. I kept running into small bugs, like the context switch counter giving me werird numbers because I didn't place it correctly in the loop. Also , I had to switch Stime from an integer to a long because System.currentTimeMillis() was throwing errors , Which took me a while to catch. it felt like I was spending more time refactoring the run() and runcompletion() methods just to make the output look clean I was actually writing the scheduler logic. Balancing the priority featurs while making sure the code stayed readable was definitely the most frustrating part of the whole assignment for]

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

[To fix the logic , I basically hard to tear down the scheduling flow and test the priority and waiting time features one by one. I relied heavily on the Arraylist to keep my process data save, otherwise, I would have lost track of the result during all those context switches. I also spent quite a bit of time digging through the java documentation for System.currintTimeMills() becuase my time calcelation were way off at first that's how I caught the bug and switched from integer to long. I acutally reached out to some friends, and we talked through the best way to keep the code from turning into a mess. I even used AI as a tutor to help explain the more complicated parts of the java threads api that I didn't fully get. It was a long process of trial and error, but combining those online docs with some peer feedback is what finally got the simulation running properly]

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

[Honestly, being a gamer makes it easy to see why multithreading is the real backbone of any pc during a heavy ession. In the games I play. you have got one thread handling my inputs and plyer physics while other threads are busy rendering graphics or syncing up the multiplayer network audio. This assignment actually showed me that without solid time quantum management, everything would just feel laggy because one process would be hogging the cpu and bloking the rest. Even the apps I use in the background like discord or googel chrome rely on this so I can voice chat or stream without he system freezing up. Learing about context switching and using that Arraylist to store data helped me understand why having too many tasks open causes those annoying fps drops. It’s  basically how the os balances all these threads to give every task its fair share of the processor. This whole assignment made threads management feel way more relatable to how my gaming setup actually functions daily]

---

## Additional Reflections (Optional)

### What would you like to learn more about?

[I really want to see how games manage thousands of threads without crashing. My pc sometimes lags in heavy matches and I wonder if it is bad schedulding. Seeing how graphics and audio sync up in reltime is fascinating to me. I also want to look into deadlocks and how servers prevent them. Dealing with a frozen system where processes just wait on each other sounds like a total nightmare. Learning the specific code pattern for safe memory in big systems is my next goal. It would be cool to see how professional developers handle these things in the industry]

---

### How confident do you feel about multithreading concepts now?

[Intermediate]

[The theory part is finally clear after finishing this assignment. I get how a thread starts and dies and the quantum switching makes sense. But I am not an expert yet by any means . If I had o write a huge program with shared memory I would probbly struggle. Making sure threads do not overwrite each other’s data is stil pretty confusing, I need to write more practice program to get comfortable with synchronization. It takes a lot of trial and error get the logic perfect every time]

---

### Feedback on the assignment

[Doing the actual code was way better than just reading slides. I liked it because it forced me to figure out the math for context switching myself. It was frustrating at some point but it helped the concepts stick. For next time, adding process arival times would be a huge improvement. Right now everything just starts at once which is not very realistic. Giving them different delays would make the queue behave more like a real os. This would add a nice layer of complexity to the whole simulaton]
