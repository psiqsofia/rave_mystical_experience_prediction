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

## 📊 Exploratory Analysis

Some key insights:

- Higher spirituality and euphoric states correlate with mystical experiences.
- People who reported substance use were more likely to have had a mystical experience, compared to those who did not. However, not all substance users experienced mysticism, indicating other contributing factors such as emotional state or spirituality.
  
_Visuals here:_


<p align="center">
  <img src="images/emotion_vs_mystical.png" width="400"/>
  <img src="images/spirituality_vs_mystical.png" width="400"/>
</p>

---

## 🧠 Neural Network Model

Built using Keras with the following structure:

```python
model = Sequential([
  Dense(16, activation='relu', input_shape=(n_features,)),
  Dense(8, activation='relu'),
  Dense(1, activation='sigmoid')
])
