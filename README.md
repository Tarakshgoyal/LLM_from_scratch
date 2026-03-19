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

---

*More sections (like Installation, Usage, and Architecture) will be added as the project progresses.*
