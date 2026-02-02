# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

---
The game looked relatively normal when looking at it first glance. However, the first thing I noticed was how hard it 
was to guess the answer without the developer info because the hints were misleading. There are some other problems I noticed once I actually started checking if everything does as specified.


Problems noticed:
 - Hint misled players (says higher when it should be lower)
 - Can guess out of bounds (should not be able to guess out of bounds)
 - New game button doesn't make a new game (Should reset the game after one game)
 - Score was inconsistent (Displayed score didn't match developer info)
 - Difficulty attempts for guesses didn't match (Difficulty attempts should match display)
 - Range for Easy and Hard were displayed on screen wrong (Easy should have a range of 1 - 20. Hard should have 1 - 50.)
 - Can't press enter after making a guess (Can't use enter key to submit guess.)

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion you accepted and why.
- Give one example of an AI suggestion you changed or rejected and why.

---
For this project, I utilized Copilot within my VSCODE IDE to assist me.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
