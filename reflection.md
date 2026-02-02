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
 - Hint misled players (says higher when it should be lower)  -- FIXED
 - Can guess out of bounds (should not be able to guess out of bounds) -- FIXED
 - New game button doesn't make a new game (Should reset the game after one game) -- FIXED
 - Score was inconsistent (Displayed score didn't match developer info)
 - Difficulty attempts for guesses didn't match (Difficulty attempts should match display) -- FIXED
 - Range for Easy and Hard were displayed on screen wrong (Easy should have a range of 1 - 20. Hard should have 1 - 50.) -- FIXED
 - Can't press enter after making a guess (Can't use enter key to submit guess.) 

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion you accepted and why.
- Give one example of an AI suggestion you changed or rejected and why.

---
For this project, I utilized Copilot within my VSCODE IDE to assist me.

What I accepted:
Example from copilot: Reset All Variables and Ensure all session state variables related to the game are reset (attempts, secret, status, history, score).
if new_game:
    # Reset all relevant session state variables
    st.session_state.attempts = 0
    st.session_state.secret = random.randint(1, 100)
    st.session_state.status = "playing"  # Reset game status
    st.session_state.history = []  # Clear guess history
    st.session_state.score = 0  # Reset score
    st.success("New game started.")
    st.experimental_rerun()

I accepted this cause it seemed reasonable and I utilized Agent mode so I could see the changes to the application before commiting to the code.
Resetting all values would make it easier to have a completely new game than rather the previous code resetting a few values.

What I rejected:
Example from copilot: To enable the "Enter" key to submit the guess, you can use Streamlit's st.form and st.form_submit_button. Here's how you can modify your code:

Form for guess submission
with st.form(key="guess_form"):
    guess = st.text_input("Enter your guess:")
    submit_button = st.form_submit_button("Submit Guess")

if submit_button:
    # Handle guess submission logic here
    st.write(f"You guessed: {guess}")

I rejected this AI fix because it does indeed fix the problem of "Being able to submit a guess using the enter key", it creates a completely separate asset the accomplish this. Which is not what I intended when I asked for this problem to be fixed. I intended to improve the already functioning input field that's in the application.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---
I decided a bug was truly fixed, when I checked the application and it runs as intended without producing more errors. I'm not proficient at pytests so checking the application was easier for me to debug.

One test I ran was a combination of manuel and pytest tests for making sure the hints that were given were correct.
I utilized a good number of python tests to check whether the hints will work when you're in range. I also checked the actual application to make sure the user can see the hints work correctly as well.
AI did help me in creating the python tests that tests a good majority of cases. Along with examining the problem within app.py at the time of how to fix the hints.

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

One strategy I want to utilize next time is being able to examine and find problems within the application. I felt that I found a lot of issues that needed to be resolved pretty well so I hope I can do the same for future projects.
The next time I do such I project I'll curate my language when prompting the AI better. Due to how I wrote the prompt, the AI would not identify the specifc problem I had and would look over every piece of code whether it was apart of what I was asking or not. 
Through this project, I realized how helpful AI is in recommending fixes as before AI you'd use any information on the internet and he could be revelent but majority was not. I also liked how helpful the AI was when creating tests. Made the repeativeness easier to overcome.
