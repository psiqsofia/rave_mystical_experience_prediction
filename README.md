# 🧠 Predicting Mystical Experiences at Raves using Neural Networks

This project explores how psychological, contextual, and emotional factors might influence the likelihood of having a **mystical experience** during a rave or electronic music event. A mystical experience is a subjective experience characterized by a sense of union with something greater than oneself, often described as a profound spiritual or religious encounter.
Here I combine simulated data, data visualization, and a neural network model built in Keras.

---

## 🌌 Context

Based on a fictional but psychologically grounded dataset of 200 individuals attending raves, each described by:

- Age
- Gender
- Emotional state before the event
- Substance use (yes/no)
- Music type (e.g., techno, trance, ambient)
- Spirituality level (self-reported measure)
- Visual and sensory intensity of the event
- Social connection during the experience

The target variable was whether the person had a **mystical experience** (`1 = yes`, `0 = no`).

---

## 🧪 Data Simulation

The dataset was synthetically created based on probabilities informed by real psychological insights (e.g., emotional state, social connection, spirituality).

Example:

| age | emotion   | spirituality | visuals | connection | mystical |
|-----|-----------|--------------|---------|------------|----------|
| 27  | euphoric  | high         | high    | high       | 1        |
| 31  | numb      | low          | low     | low        | 0        |

---

## 📊 Exploratory Data Analysis (EDA)
🟣 1. Mystical experience frequency

Out of 200 participants, approximately 70 reported having had a mystical experience. 
[Mystical Experience](images/mystical.png)

🟪 2. Emotional state vs Mystical experience

Participants who described their emotional state as euphoric were the most likely to report a mystical experience. In contrast, those feeling numb or sad had the lowest frequency of mystical experiences. This suggests a strong emotional activation may be a contributing factor in mystical states.
[Emotional state](images/emotion.png)

🟨 3. Spirituality level vs Mystical Experience

Participants with low or medium spirituality levels reported fewer mystical experiences. Interestingly, those with a high level of spirituality had almost equal proportions of “Yes” and “No”, indicating that high spirituality may be related to, but not fully predictive of, mystical experiences.
[Spirituality Level](images/spirituality.png)

💛 4. Substance use vs Mystical Experience

Among participants who reported no substance use, very few experienced mystical states. On the other hand, those who did use substances were almost equally split between having and not having mystical experiences. This supports the hypothesis that substance use might increase the likelihood of a mystical experience, but is not a guarantee.
[Substance use](images/substance.png)
💜 5. Connection with Others vs Mystical Experience

Participants who felt more connected with others during their experience were more likely to report a mystical state. This variable appears as one of the strongest correlates with mysticism, hinting at the importance of interpersonal or collective experience in transcendence.

[Connection with Others](images/connection.png)

## 🧠 Neural Network Model

Built using Keras with the following structure:

```python
model = Sequential([
  Dense(16, activation='relu', input_shape=(n_features,)),
  Dense(8, activation='relu'),
  Dense(1, activation='sigmoid')
])
