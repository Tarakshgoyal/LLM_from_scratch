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

## 🌌 The "Large" in LLM: Parameters & Pre-Training

What puts the "large" in Large Language Models is that they contain hundreds of billions of **parameters**. 

No human ever deliberately sets these parameters. Instead, they begin entirely at random, meaning a brand-new model just outputs gibberish. However, these parameters are repeatedly refined based on trillions of example pieces of text. 

During training, the model is fed a text example with the last word hidden. It makes a prediction, and that prediction is compared to the true last word. An algorithm called **backpropagation** is then used to tweak all the parameters so the model is slightly more likely to choose the correct word next time, and less likely to choose the others. 

When you repeat this across trillions of examples, the model doesn't just memorize the training data—it actually starts to make highly reasonable predictions on text it has never seen before.

## 🤯 The Mind-Boggling Scale of Computation

Given the huge number of parameters and the enormous amount of training data, the scale of computation involved is difficult to fathom. 

To illustrate: imagine you could perform **one billion** additions and multiplications every single second. How long do you think it would take you to do all the operations required to train the largest language models? A year? Maybe 10,000 years? 

The answer is actually well over **100 million years**. 

This staggering amount of computation is only made possible by using special computer chips optimized for running many operations in parallel, known as **GPUs** (Graphics Processing Units).

## 🎓 Beyond Autocomplete: RLHF

The massive process described above is called **pre-training**. However, the goal of simply auto-completing random internet text is very different from the goal of being a helpful, safe AI assistant. 

To bridge this gap, chatbots undergo a second, equally important phase of training called **Reinforcement Learning with Human Feedback (RLHF)**. Human workers review the model's responses and flag unhelpful or problematic predictions. Their corrections further adjust the model's parameters, teaching it to generate the types of helpful, conversational answers that users actually prefer.

## ⚡ The Transformer Revolution

Not all language models can be easily parallelized on GPUs. Prior to 2017, most models had to process text sequentially—one word at a time. Then, a team of researchers introduced a breakthrough architecture known as the **Transformer**. 

Instead of reading text from start to finish, Transformers soak it all in at once, in parallel. 

### How Transformers Process Language:
1. **Embeddings (Lists of Numbers):** The first step in a Transformer is to associate each word with a long list of numbers. Because mathematical models only work with continuous values, language must be encoded numerically. These lists of numbers capture and encode the actual *meaning* of the word.
2. **The "Attention" Mechanism:** What makes Transformers truly unique is an operation called **attention**. This allows all the individual lists of numbers to "talk" to one another and refine their meanings based on the surrounding context. For example, the numbers encoding the word *bank* will shift depending on the context to specifically represent a *riverbank* rather than a *financial bank*.
3. **Feed-Forward Neural Networks:** The data then passes through a feed-forward network, which gives the model extra capacity to store the complex patterns of language it learned during training.

## 🪄 Emergent Behavior

Data repeatedly flows through many iterations of these fundamental operations. By the end, the final vector in the sequence has been influenced by all the surrounding context and everything the model learned during training. One final mathematical function is performed to produce the ultimate prediction—a probability distribution for every possible next word.

Although researchers designed the architecture for how these steps work, the specific behavior of the model is an **emergent phenomenon** born from how hundreds of billions of parameters are tuned. This makes it incredibly challenging to look inside the model and determine exactly *why* it makes a specific prediction. 

What we do know is the end result: when you use an LLM to autocomplete a prompt, the words it generates are uncannily fluent, fascinating, and incredibly useful.

## 🧩 Decoding GPT: Generative Pretrained Transformer

You’ve likely heard the acronym **GPT**, but what does it actually mean?

* **Generative:** These are models designed to generate new text.
* **Pretrained:** The model went through a massive initial learning process over huge swaths of internet data. (The prefix implies there is room to "fine-tune" it later for specific tasks).
* **Transformer:** This is the core invention underlying the current AI boom. It is a specific, highly efficient type of neural network architecture introduced by Google in 2017. 

Transformers can be built for many things—turning audio into transcripts, text into images (like DALL-E), or, in our case, text into next-word predictions.

### Predict, Sample, Repeat
At first glance, predicting a single next word feels very different from generating a full, coherent essay. But generation is just a loop:
1.  **Predict:** The model looks at the initial text and generates a probability distribution for the next word.
2.  **Sample:** A word is selected from that distribution.
3.  **Repeat:** That new word is appended to the text, and the whole sequence is fed back into the model to predict the *next* word.

This loop—combined with the massive scale of the model—is what transforms a simple autocomplete tool into a fluent chatbot.

---

## 🔍 Inside the Transformer: The Data Flow

When a model generates a word, a highly structured sequence of mathematical operations occurs under the hood. Deep learning relies on transforming data into arrays of real numbers (tensors) and processing them through massive matrices of weights.

### 1. Tokens and Word Embeddings
First, the input text is chopped into smaller pieces called **tokens** (words, parts of words, or characters). The model cannot process text directly, so each token is mapped to a high-dimensional vector—a long list of numbers—using an **Embedding Matrix**. 

* **The Geometry of Meaning:** You can think of these vectors as coordinates in a high-dimensional space (e.g., 12,288 dimensions in GPT-3). As the model trains, it organizes this space so that directions carry semantic meaning. 
* **Example:** If you take the vector for *King*, subtract the vector for *Man*, and add the vector for *Woman*, the resulting coordinates will land surprisingly close to the vector for *Queen*. The model mathematically learns relationships like gender, plurality, and geography.

### 2. The Attention Block (Context)
A single word's meaning changes based on context (e.g., a "fashion *model*" vs. a "machine learning *model*"). The vectors pass through an **Attention Block**, which allows them to "talk" to each other. Information is passed back and forth so each vector can update its values to reflect the surrounding context. 

* **Context Window:** The model can only look at a fixed number of tokens at a time (e.g., 2,048 tokens). This is why chatbots can sometimes "lose the thread" of very long conversations.

### 3. The Feed-Forward Layer (Multi-Layer Perceptron)
After sharing context, the vectors pass through a feed-forward layer. Here, they no longer talk to each other; they are processed in parallel. You can think of this step as the model asking a long list of complex questions about each vector and updating them based on the answers.

This entire process (Attention → Feed-Forward) repeats across many layers until the essential meaning of the entire passage is baked into the very last vector in the sequence.

---

## 🎯 The Final Prediction: Unembedding and Softmax

Once the final vector is fully enriched with context, it's time to make a prediction. 

### Unembedding
The model uses an **Unembedding Matrix** to map that final, context-rich vector back into a list of numbers—one for every single possible token in its vocabulary (e.g., 50,000 tokens). These raw, unnormalized scores are called **logits**.

### Softmax & Temperature
Because logits can be negative or wildly large, they aren't useful as probabilities. They are passed through a function called **Softmax**, which normalizes them into a valid probability distribution (all values are between 0 and 1, and they all add up to 1). 

To make the AI's output more dynamic, developers add a variable into the Softmax math called **Temperature**:
* **Low Temperature (e.g., 0.0):** The model always picks the most likely word. The output is highly predictable, safe, but often generic or repetitive.
* **High Temperature (e.g., 0.8+):** The distribution is flattened slightly, giving less likely words a fighting chance. The output becomes more creative and original, but if set *too* high, it can quickly degenerate into nonsense.
