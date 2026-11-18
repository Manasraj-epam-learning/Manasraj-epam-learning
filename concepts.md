# AI Foundations: Concept Notes

## 1. What is Artificial Intelligence?

Artificial Intelligence (AI) is the field of building systems that perform tasks which normally need human intelligence, such as understanding language, recognising images, making decisions or solving problems.

Everything in use today is **narrow AI**: a system built for one task or a small set of tasks. **Artificial General Intelligence (AGI)**, a system with human-level ability across any task, does not exist today.

## 2. AI, ML, Deep Learning and Generative AI

```
+-------------------------------------------------------+
| Artificial Intelligence (any technique that acts      |
| "intelligently": rules, search, planning, learning)   |
|   +-----------------------------------------------+   |
|   | Machine Learning (learns patterns from data)  |   |
|   |   +---------------------------------------+   |   |
|   |   | Deep Learning (multi-layer neural     |   |   |
|   |   | networks)                             |   |   |
|   |   |   +-------------------------------+   |   |   |
|   |   |   | Generative AI (creates new    |   |   |   |
|   |   |   | text, images, audio, code)    |   |   |   |
|   |   |   +-------------------------------+   |   |   |
|   |   +---------------------------------------+   |   |
|   +-----------------------------------------------+   |
+-------------------------------------------------------+
```

| Term | Meaning | Example |
|------|---------|---------|
| AI | Umbrella term for machines performing intelligent tasks | Chess engine, voice assistant |
| Machine Learning | Systems improve at a task by learning from data instead of explicit rules | Spam filter, price prediction |
| Deep Learning | ML using neural networks with many layers; strong on images, audio, text | Face recognition, speech-to-text |
| Generative AI | Models that generate new content resembling their training data | Large language models, image generators |

Two clarifications worth remembering:

- **Not all AI is ML.** A hand-written rule system or a classic search algorithm is AI but does not learn from data.
- **Generative AI is placed inside deep learning** because today's leading generative models (transformers, diffusion models) are deep neural networks. Simple generative models without neural networks also exist (for example Markov-chain text generators), so the nesting is a practical simplification rather than a strict rule.

## 3. Traditional programming vs. machine learning

| | Traditional programming | Machine learning |
|---|---|---|
| Input | Data + hand-written rules | Data + known answers (labels) |
| Output | Answers | Rules (a trained model) |
| Strength | Predictable, easy to explain | Handles patterns too complex to write as rules |
| Weakness | Rules break on unforeseen cases | Needs good data; can be wrong in subtle ways |

`code/spam_classifier.py` shows both approaches side by side.

## 4. Types of machine learning

- **Supervised learning**: learn from labelled examples (input and correct output).
  - *Classification*: predict a category (spam / not spam).
  - *Regression*: predict a number (exam score, house price).
- **Unsupervised learning**: find structure in unlabelled data (customer clustering, dimensionality reduction).
- **Reinforcement learning**: an agent learns by trial and error, receiving rewards or penalties (game playing, robotics).
- **Self-supervised learning**: the model creates its own labels from the data, for example predicting the next word in a sentence. This is how large language models are pre-trained.

## 5. The machine learning workflow

1. **Define the problem**: what should be predicted, and how will success be measured?
2. **Collect data**: relevant, representative and legally usable.
3. **Prepare data**: clean missing or wrong values, encode text/categories, scale features.
4. **Split data**: training set (learn), validation set (tune), test set (final honest check).
5. **Choose and train a model**: adjust parameters to minimise a loss function.
6. **Evaluate**: use suitable metrics on data the model has never seen.
7. **Improve**: better data, features, model or hyperparameters. Repeat.
8. **Deploy and monitor**: real-world data drifts, so performance must be tracked.

`code/linear_regression_demo.py` and `code/spam_classifier.py` follow steps 3 to 6.

## 6. Core concepts

**Features and labels.** Features are the inputs the model sees (hours studied, words in a message). The label is the answer to predict (exam score, spam/ham).

**Model, parameters, hyperparameters.** Parameters are learned during training (slope and intercept in linear regression, weights in a neural network). Hyperparameters are chosen by the developer before training (learning rate, k in k-NN, number of epochs).

**Loss function and training.** The loss measures how wrong predictions are (for example mean squared error). Training searches for parameters that make the loss small. **Gradient descent** does this by repeatedly moving parameters a small step in the direction that reduces the loss. The step size is the **learning rate**.

**Overfitting and underfitting.**
- *Overfitting*: the model memorises noise in the training data. Training score is high, test score is noticeably lower. See `practice/ex04_overfitting_demo.py`.
- *Underfitting*: the model is too simple to capture the pattern. Both scores are low.
- Remedies include more data, simpler models, regularisation and early stopping.

**Why the test set must stay untouched.** If the test data influences any training decision, the reported score becomes optimistic and no longer reflects real-world performance.

**Evaluation metrics (classification).** Given the confusion matrix (TP, FP, FN, TN):
- Accuracy = (TP + TN) / total
- Precision = TP / (TP + FP): of the items flagged positive, how many truly were
- Recall = TP / (TP + FN): of the true positives, how many were found
- F1 = harmonic mean of precision and recall

Accuracy is misleading on imbalanced data (`practice/ex06_accuracy_paradox.py`).

**Neural networks (briefly).** A neural network is layers of simple units. Each unit computes a weighted sum of its inputs and passes it through a non-linear activation function. Training adjusts the weights with gradient descent (using backpropagation to compute the gradients). "Deep" means many layers.

## 7. Generative AI and large language models

- A **Large Language Model (LLM)** is a very large neural network (usually a **transformer**) trained on huge amounts of text to predict the next token.
- A **token** is a chunk of text (a word or part of a word); models read and write tokens.
- A **prompt** is the input given to the model; **prompt engineering** is writing prompts to get better outputs.
- The **context window** is the maximum amount of text the model can consider at once.
- **Hallucination**: the model produces fluent but false or unsupported statements, because it generates plausible text rather than looking up verified facts.
- Common ways to reduce hallucination: clear prompts, supplying source documents (retrieval-augmented generation), and human verification.

## 8. Limitations and responsible AI

- **Data bias**: a model trained on unrepresentative data produces unfair or inaccurate results for under-represented groups.
- **Explainability**: deep models are often hard to interpret, which matters in areas like healthcare and finance.
- **Privacy and security**: training data may contain personal information; models can be attacked or misused.
- **Over-reliance**: outputs should be verified, especially for important decisions.
- **Accountability**: humans and organisations remain responsible for how AI systems are used.

## 9. Summary

- AI is the broad goal; machine learning is learning from data; deep learning uses multi-layer neural networks; generative AI creates new content.
- A good ML result comes from good data, an honest evaluation and awareness of limitations, not just from a clever algorithm.
- A trained model and a rule-based program can both look "smart", but only the first one learns from data.
