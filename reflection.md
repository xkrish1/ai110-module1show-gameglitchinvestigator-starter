# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

The interface seemed normal and simple off the bat. The developer debug info worked as well, and logged the numbers. For some reason it stopped on 7th attempt. Number kept asking to go higher. Secret Number kept changing. New game doesn't work. Score is negative 

---  

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

Copilot, Claude. One suggestion was changing the if statement logic for whether the banner should display "go higher/lower", and it was correct. Another suggestion is something related to the dev debug info window, and it changed it incorrectly. 

--- 

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I tested to check all bugs and testcases I had taken account of. One test I did was going through all difficuties to check if bugs were fixed for all modes. When going through AIs changes, I saw parts of the code that I didn't account for to test.

--- 

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

The original code had random.randint(low, high) running unconditionally at the top level, so a brand new random number was picked on every single rerun. 
Streamlit every button click or keystroke wipes the board and runs your whole script again. 
Wrapping the secret generation in a "secret" not in st.session_state guard.

--- 

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit is reading and understanding the code before asking for change, as several bugs had overlap with each other in the code. 
One thing to do differently is to test each fix in isolation before moving to the next one. 
AI-generated code can look completely correct and still be subtly wrong in ways that only show up when you actually play the game. It taught me that "it runs without errors" and "it works correctly" are two completely different things, and that AI output always needs a human to verify the application, not just the syntax.