# Learning Langgraph

I was following a nice course on langgraph, with exercises and everything. Uploading to github for later reference.

The author of the course also uploaded the ppts on github: [Github: iamvaibhavmehra/LangGraph-Course-freeCodeCamp](https://github.com/iamvaibhavmehra/LangGraph-Course-freeCodeCamp)

This is the video on FreeCodeCamp: [LangGraph Complete Course for Beginners – Complex AI Agents with Python](https://www.youtube.com/watch?v=jGg_1h0qzaM)

## Outputs

### Output from ai1_simple_bot.py
```
Enter: Hi

AI: Hi there! How can I help you today?
====================
Enter: Who made you?

AI: I am a large language model, trained by Google.
====================
Enter: What is 2+2?

AI: 2 + 2 = 4
====================
Enter: My name is Charlie.

AI: Okay, Charlie. It's nice to meet you (virtually)! How can I help you today?
====================
Enter: What is my name?

AI: As an AI, I do not have access to personal information. Therefore, I do not know your name. You have not provided it to me.
==================== # It does not remember!
Enter: q
Goodbye
```

### Output from ai2_short_term_memory.py

```
Enter: Hi                   

AI: Hi there! How can I help you today?
====================
Enter: Hi, I am Steve.

AI: Hi Steve, nice to meet you! How can I help you today, Steve?
====================
Enter: Who am I?

AI: You are Steve, according to what you just told me. I don't have access to any personal information about you beyond that.
====================
Enter: q
Goodbye
```

### ai3_short_term_memory_memsaver.py

```
user@host:~/.../learning_langgraph$ python3 ai3_short_term_memory_memsaver.py 
Enter: Konichiwa, from Japan
Enter ThreadID: 1

AI: Konnichiwa! こんにちは！ How are you doing today? What can I help you with?
====================
Enter: My name is Musashi
Enter ThreadID: 1

AI: Konnichiwa, Musashi-san! It's a pleasure to meet you. どうぞよろしく (Douzo yoroshiku - Nice to meet you). Is there anything I can help you with today?
====================
Enter: Good Morning (Its 7 AM here), I had tofu for breakfast.
Enter ThreadID: 1

AI: Konnichiwa, Musashi-san! 

Ah, so you're in Japan. It's nice to meet you. 

Ohayou gozaimasu! 7 AM is early! Tofu for breakfast sounds healthy and delicious. I hope you have a wonderful day.
====================
Enter: Hello, from the UK
Enter ThreadID: 2

AI: Hello there from across the pond! How can I help you today?
====================
Enter: I am Winston
Enter ThreadID: 2

AI: Hello Winston from the UK! It's a pleasure to meet you. Is there anything I can help you with today?
====================
Enter: I just ate dinner, pancakes.
Enter ThreadID: 2

AI: Hello Winston! Pancakes for dinner sounds lovely. A true British classic... well, maybe not *dinner* pancakes, but pancakes are always a good choice! What kind of toppings did you have?
====================
Enter: What is my name? Where am I talking from? What was my latest meal?
Enter ThreadID: 1

AI: Okay, Musashi! Based on our conversation:

*   **Your name is Musashi.**
*   **You are talking from Japan.**
*   **Your latest meal was tofu.**
====================
Enter: What is my name? Where am I talking from? What was my latest meal?
Enter ThreadID: 2

AI: Okay, Winston, based on our conversation:

*   **Your name is:** Winston
*   **You are talking from:** The UK
*   **Your latest meal was:** Pancakes
====================
Enter: q
Goodbye
```

### python ai4_react_agent.py 

```
user@host:~/.../learning_langgraph$ python ai4_react_agent.py 
Enter: Add 3+4, subtract the result from 40 and find the product of this result with 5
================================ Human Message =================================

Add 3+4, subtract the result from 40 and find the product of this result with 5
================================== Ai Message ==================================
Tool Calls:
  add (247ed163-7194-41d1-8a59-e62abc1eb4b2)
 Call ID: 247ed163-7194-41d1-8a59-e62abc1eb4b2
  Args:
    a: 3.0
    b: 4.0
================================= Tool Message =================================
Name: add

7
================================== Ai Message ==================================
Tool Calls:
  subtract (2c99230d-952b-48c0-873b-2d957dcd7865)
 Call ID: 2c99230d-952b-48c0-873b-2d957dcd7865
  Args:
    a: 40.0
    b: 7.0
================================= Tool Message =================================
Name: subtract

33
================================== Ai Message ==================================
Tool Calls:
  multiply (7f7d3f88-34ac-48f4-b094-23cd49c6d053)
 Call ID: 7f7d3f88-34ac-48f4-b094-23cd49c6d053
  Args:
    a: 33.0
    b: 5.0
================================= Tool Message =================================
Name: multiply

165
================================== Ai Message ==================================

The answer is 165
================================================================================

================================================================================
Enter: Add 3+4 then, do the same for 7 and 8
================================ Human Message =================================

Add 3+4 then, do the same for 7 and 8
================================== Ai Message ==================================
Tool Calls:
  add (881c6b46-0f53-4173-9325-3cc27d3962cd)
 Call ID: 881c6b46-0f53-4173-9325-3cc27d3962cd
  Args:
    a: 3.0
    b: 4.0
  add (4ff0b2e6-610f-4bf7-92f3-287976eb8783)
 Call ID: 4ff0b2e6-610f-4bf7-92f3-287976eb8783
  Args:
    a: 7.0
    b: 8.0
================================= Tool Message =================================
Name: add

15
================================== Ai Message ==================================

The sum of 3 and 4 is 7, and the sum of 7 and 8 is 15.
================================================================================

================================================================================
Enter: q
Goodbye
```