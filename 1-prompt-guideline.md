# Guidelines for Prompting

In this lesson, you'll practice two prompting principles and their related tactics in order to write effective prompts for large language models.

## Prompting Principles

**Content Table**

- [**Principle 1: Write clear and specific instructions**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#principle-1-write-clear-and-specific-instructions)

  - [Tactic 1: Use delimiters](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-1-use-delimiters-to-clearly-indicate-distinct-parts-of-the-input)
  - [Tactic 2: Ask for a structured output](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-2-ask-for-a-structured-output)

  - [Tactic 3: Ask the model to check whether conditions are satisfied](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-3-ask-the-model-to-check-whether-conditions-are-satisfied)

  - [Tactic 4: "Few-shot" prompting](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-4-few-shot-prompting)

- [**Principle 2: Give the model time to “think”**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#principle-1-write-clear-and-specific-instructions)

  - [Tactic 1: Specify the steps required to complete a task](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-1-specify-the-steps-required-to-complete-a-task)

  - [Tactic 2: Instruct the model to work out its own solution before rushing to a conclusion](https://github.com/SOLUNTECH/prompt-engineering/blob/main/1-prompt-guideline.md#tactic-2-instruct-the-model-to-work-out-its-own-solution-before-rushing-to-a-conclusion)

- [**Model limitations**]()

---

### **Principle 1: Write clear and specific instructions**

#### **Tactic 1:** Use delimiters to clearly indicate distinct parts of the input

- Delimiters can be anything like: ```, """, < >, `<tag> </tag>`, `:`

`Example prompt:`

```text
Summarize the text delimited by triple backticks into a single sentence.

```ChatGPT, isn't an average natural language processing model—it's Large language model feed with a massive dataset of text and code. Its have become an AI-powered creative partner at your disposal anytime, anywhere all at once (like the movie). Let's say you're working late, aiming to meet a deadline. Suddenly, you receive a series of urgent requests from your client. These aren't small changes, they're complex adjustments and you're uncertain how to handle them. This is where ChatGPT becomes essential.```
```

#### **Tactic 2:** Ask for a structured output

- JSON, HTML

`

```text
Generate a list of three made-up book titles along with their authors and genres. 
Provide them in JSON format with the following keys: 
book_id, title, author, genre.
```

#### **Tactic 3:** Ask the model to check whether conditions are satisfied

`Example prompt 1:`

```text
You will be provided with text delimited by triple quotes. 
If it contains a sequence of instructions, re-write those instructions in the following format:

Step 1 - ...
Step 2 - …
…
Step N - …

If the text does not contain a sequence of instructions, then simply write "No steps provided."

"""
Making a cup of tea is easy! First, you need to get some water boiling. While that's happening, grab a cup and put a tea bag in it. Once the water is hot enough, just pour it over the tea bag. Let it sit for a bit so the tea can steep. After a few minutes, take out the tea bag. If you like, you can add some sugar or milk to taste. And that's it! You've got yourself a delicious cup of tea to enjoy.
"""
```

`Example prompt 2:`

```text
You will be provided with text delimited by triple quotes. 
If it contains a sequence of instructions, re-write those instructions in the following format:

Step 1 - ...
Step 2 - …
…
Step N - …

If the text does not contain a sequence of instructions, then simply write "No steps provided."

"""
The sun is shining brightly today, and the birds are singing. It's a beautiful day to go for a walk in the park. The flowers are blooming, and the trees are swaying gently in the breeze. People are out and about, enjoying the lovely weather. Some are having picnics, while others are playing games or simply relaxing on the grass. It's a perfect day to spend time outdoors and appreciate the beauty of nature.
"""
```

#### **Tactic 4:** "Few-shot" prompting

`Example prompt:`

```text
Your task is to answer in a consistent style.

<child>: Teach me about patience.

<grandparent>: The river that carves the deepest valley flows from a modest spring; the grandest symphony originates from a single note; the most intricate tapestry begins with a solitary thread.

<child>: Teach me about resilience.
```

---

### **Principle 2: Give the model time to “think”**

#### **Tactic 1:** Specify the steps required to complete a task

`Example prompt 1:`

```text
Perform the following actions: 
1 - Summarize the following text delimited by triple backticks with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the following keys: french_summary, num_names.

Separate your answers with line breaks.

Text:
```In a charming village, siblings Jack and Jill set out on a quest to fetch water from a hilltop well. As they climbed, singing joyfully, misfortune struck—Jack tripped on a stone and tumbled down the hill, with Jill following suit. Though slightly battered, the pair returned home to comforting embraces. Despite the mishap, their adventurous spirits remained undimmed, and they continued exploring with delight.```
```

#### Ask for output in a specified format

`Example prompt 2:`

```text
Your task is to perform the following actions: 
1 - Summarize the following text delimited by <> with 1 sentence.
2 - Translate the summary into French.
3 - List each name in the French summary.
4 - Output a json object that contains the following keys: french_summary, num_names.

Use the following format:
Text: <text to summarize>
Summary: <summary>
Translation: <summary translation>
Names: <list of names in Italian summary>
Output JSON: <json with summary and num_names>

Text: <In a charming village, siblings Jack and Jill set out on a quest to fetch water from a hilltop well. As they climbed, singing joyfully, misfortune struck—Jack tripped on a stone and tumbled down the hill, with Jill following suit. Though slightly battered, the pair returned home to comforting embraces. Despite the mishap, their adventurous spirits remained undimmed, and they continued exploring with delight.>

```

#### **Tactic 2:** Instruct the model to work out its own solution before rushing to a conclusion

`Example prompt:`

```text
Determine if the student's solution is correct or not.

Question:
I'm building a solar power installation and I need help working out the financials. 
- Land costs $100 / square foot
- I can buy solar panels for $250 / square foot
- I negotiated a contract for maintenance that will cost me a flat $100k per year, and an additional $10 / square foot

What is the total cost for the first year of operations 
as a function of the number of square feet.

Student's Solution:
Let x be the size of the installation in square feet.
Costs:
1. Land cost: 100x
2. Solar panel cost: 250x
3. Maintenance cost: 100,000 + 100x
Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000
```

#### Note that the student's solution is actually not correct

#### We can fix this by instructing the model to work out its own solution first

`Example prompt:`

```text
Your task is to determine if the student's solution is correct or not.
To solve the problem do the following:
- First, work out your own solution to the problem. 
- Then compare your solution to the student's solution and evaluate if the student's solution is correct or not. 
Don't decide if the student's solution is correct until 
you have done the problem yourself.

Use the following format:
Question:
---
question here
---
Student's solution:
---
student's solution here
---
Actual solution:
---
steps to work out the solution and your solution here
---
Is the student's solution the same as actual solution just calculated:
---
yes or no
---
Student grade:
---
correct or incorrect
---

Question:
---
I'm building a solar power installation and I need help working out the financials. 
- Land costs $100 / square foot
- I can buy solar panels for $250 / square foot
- I negotiated a contract for maintenance that will cost me a flat $100k per year, and an additional $10 / square foot

What is the total cost for the first year of operations as a function of the number of square feet.
--- 
Student's solution:
---
Let x be the size of the installation in square feet.
Costs:
1. Land cost: 100x
2. Solar panel cost: 250x
3. Maintenance cost: 100,000 + 100x
Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000
---
Actual solution:
```

## Model Limitations: Hallucinations

- Boie is a real company, the product name is not real.

`Example prompt:`

```text
Tell me about AeroGlide UltraSlim Smart Toothbrush by Boie
```
