# LLM From Scratch 🧠

Welcome to **LLM From Scratch**! This project explores the foundational mechanics of Large Language Models (LLMs) by building them from the ground up.

## 📖 The Core Concept: The "Magical Machine"

Suppose we have a powerful, magical machine that can take any text and provide a highly sensible prediction of what word comes next. 

If you were writing a script, you could finish it by feeding what you have so far into this machine. You would look at what it predicts to start the AI's answer, add that word to your script, and then feed the *new*, slightly longer script back into the machine. By repeating this process over and over with a growing body of text, the machine effectively completes the dialogue. 

When you interact with a modern AI chatbot, this is exactly what is happening behind the scenes.

## ⚙️ How It Actually Works

Beneath the "magic," an LLM is actually a highly sophisticated mathematical model. Its primary function is to predict the next word for any given sequence of text.

### Example: Next-Word Prediction
If you give the model the following prompt:

> *"The Taj Mahal is in which state _____"*

The model evaluates its vast mathematical network and assigns a **probability** to all possible words that could logically follow. 

* **Rajasthan:** 20.5%
* **Agra:** 53.2%
* **punjab:** 22.1%
* *...and so on.*

The word with the maximum probability is selected and replied back to you by the LLM. 

## 🤖 Building a Chatbot: The Prompting Trick

To turn a next-word predictor into a conversational chatbot, you lay out a text prompt that describes an interaction between a user and a hypothetical AI. For example:

> **System:** What follows is a conversation between a user and a helpful, very knowledgeable AI assistant.
> **User:** Give me some ideas for what to do when visiting Dehradun.
> **AI Assistant:** _____

You add whatever the user types in as the first part of the interaction. Then, you have the model repeatedly predict the next words that such an "AI Assistant" would logically say in response. That generated dialogue is what is ultimately presented back to the user.

## 🎲 Randomness and Natural Output

While it might seem logical to always pick the word with the highest probability, the output actually tends to sound a lot more natural if you allow the machine to occasionally select less likely words at random. 

Because of this introduced randomness, even though the mathematical model itself is deterministic, a specific prompt will typically give a slightly different answer each time it is run.

## 📚 Training and the Scale of Data

Models learn how to make these predictions by processing an enormous amount of text, typically pulled from the internet. 

To put the scale of this data into perspective: if a standard human were to read the exact amount of text used to train GPT-3, reading non-stop 24 hours a day, 7 days a week, it would take them over **2,600 years**. Larger models built since then train on much, much more.

## 🎛️ Parameters and Weights: Tuning the Machine

We can think of training a language model a little bit like tuning the dials on a massive machine. 

The way an LLM behaves is entirely determined by these many different continuous numerical values, usually called **parameters** or **weights**. Changing those parameters fundamentally changes the probabilities that the model assigns to the next word for any given input.
---

*More sections (like Installation, Usage, and Architecture) will be added as the project progresses.*
