# DSA210-Term-Project-LoL-Analysis
## Project Overview
This project investigates the effects of various player actions and skills such as vision score, and total minion kill, on the rank in League of Legends. Additionally, the project compares the relation of elo and surrender rate.

Simply by comparing high elo games and low games, I want to emphazise what low elo players can improve and what are the major differences between low elo and high elo players.
I will test these two hypotheses:

- **Null Hypothesis(H0):** There is no significant difference between High Elo and Low Elo players in terms of minion score, damage dealt, vision score, and surrender behavior in League of Legends.
- **Alternative Hypothesis(H1):** There is a significant difference between High Elo and Low Elo players in terms of minion score, damage dealt, vision score, and surrender behavior in League of legends.

---

## Objectives
1. **Understand Skills of Players**
   Determine the relationship between parameters such as vision score, total minion killed, damage dealt dealt, and Surrender rate.
2. **Identify Significant Parameters**
   Emphazise which parameters have the biggest impact to improve League rank.
3. **Use Data to Improve Myself**
   Utilize insights from data analysis to identify areas of improvement in my own League of Legends games and enhance my overall performance.
4. **Write a Conclusion**
   Leverage the skills learned in DSA210 and data analysis to offer real solutions and insights that players can apply to improve their gameplay and rank.

---

## Motivation
I have been playing this game since 2012 and achieved the greatest rank which is Challenger. Strategy and skills are important in League, and winning the game is related to players' skills. It will be a fun way of practing my data skills. Also, I will come up with significant results since I have experience in that game. I hope to:
- Realize my mistakes, so that I can improve my gameplay and be a better player.
- Use the data skills that I learnt in the class on something that I have passion.
- Create an original and unusual work.

---

## Dataset and Tool
Riot games provide developer tool api for players. I can access match and player information api, including my own account and matches, in JSON format. I will be using Riot Games developer portal for my project. Also, I will use op.gg to take low elo player data. Here are some parameters I will consider:
- **Player Rank:** Players have ranks from iron to challenger, which shows their ability to play. Iron is the worst, challenger is the best.
- **Win/Loss:** A player lose or win a certain match. It is significant to show win/rate ratio.
- **Minion Number:** Each game players farm minions to earn gold in a match. High number of minion means a player is strong in a match.
- **Vision Score:** Vision scores indicates a player is aware of the situation on the map.
- **Game Duration:** It shows the time games end.
- **Baron Takedowns:** Baron is an essential objective and strategy to win the game.
- **Gold Earned:** Players spend gold on items that strengthen themselves.
- **Total Damage Dealt:** It shows the damage a player dealt to enemy team.
- **KDA**: Kill/death/assist ratio shows a players performance in a game.
- **hadAfkTeammate**: If a player is Away From Keyboard, it is really hard to win for their teammates.
- **gameEndedInSurrender:** It shows that a team surrender before game is actually ends by destroying the nexus.
I processed the parameters as per-minute ratios to prevent long games from causing misinterpretation.
Here is an example table of my data:

| **Match ID**    | **Player Rank** | **Win** | **Vision Score** | **Total Minions Killed** | **Baron Kills** | **Gold Earned** | **KDA** | **Total Damage Dealt** | **Game Duration (mins)** | **Minion Kills per Minute** | **AFK Teammates** | **Surrender** |
|-----------------|-----------------|---------|------------------|--------------------------|-----------------|-----------------|---------|------------------------|--------------------------|-----------------------------|-------------------|---------------|
| TR1_1597270354  | Challenger      | True    | 11               | 210                      | 2               | 15312           | 16      | 21469                  | 22.03                    | 9.54                        | No                | No            |
| TR1_1597270234  | Emerald         | False   | 4                | 120                      | 0               | 11788           | 6.5     | 13421                  | 39.02                    | 3.25                        | Yes               | Yes           ||






## Future Work

This project offers numerous avenues for further exploration, with the potential to include a wide range of additional parameters that could provide valuable insights. Some key areas to focus on in future iterations include:

 **Incorporating Additional Metrics:**
   - Beyond the parameters analyzed in this project (such as minions per minute, damage dealt, and vision score), there are many other factors that can help better understand player performance and success in **League of Legends**. These include:
     - **Objective Points:** Data on securing objectives (like dragons, barons, and towers) can shed light on a player's strategic decision-making and teamwork.
     - **Damage to Structures (Turrets):** Understanding how players contribute to damaging turrets and objectives will provide a clearer picture of their role in securing victories.
     - **Roles and Champions Played:** Analyzing different player roles (such as ADC, Support, Jungler, etc.) and champion choices can help better contextualize the results, as different roles focus on different aspects of the game.
   
   By adding more parameters, we can create a more comprehensive analysis that captures the full complexity of **League of Legends** gameplay.

 **Role-Based Analysis:**
   - While efforts were made to balance roles in the dataset, a more **granular approach** could be beneficial. Player performance is often influenced by their role in the game, and examining the impact of **role classification** on various metrics is crucial. For instance:
     - **Support Role:** Support players typically have lower minion scores but higher vision scores due to their focus on map control, warding, and assisting their team. It's important to consider these differences when interpreting the data.
     - **Other Roles (Jungler, ADC, etc.):** Each role has a unique set of objectives and responsibilities within a game. For example, **Junglers** might have higher damage dealt but lower minion farm compared to **Top Laners**. Analyzing data within the context of specific roles will help avoid misinterpretation and offer a more nuanced understanding of player performance.

---
## Findings from Exploratory Data Analysis and Testing.

Based on the visualizations, it's evident that high elo players demonstrate greater skill across the key metrics.

![Metrics Comparison](https://github.com/umutolcer/DSA210-Term-Project/blob/main/data/metrics_comparison.png?raw=tru)

**Hypothesis Testing Results:**
1. Damage Dealt per Minute: Significant difference **found** (p-value = 0.001).
2. Minions Per Minute: Significant difference **found** (p-value = 0.004).
3. Vision Score: **No** significant difference (p-value = 0.057).
4. Surrender Rate: Significant difference **found** (p-value = 0.004).


*Please head to the main.ipynb file for detailed EDA and findings.*

---

## Machine Learning 🤖

After conducting hypothesis testing, I applied **Machine Learning** methods to classify players into **Low Elo** or **High Elo** categories based on in-game performance metrics such as KDA, vision score, and damage output. These models help explore how well in-game behavior can predict a player's skill tier.

I trained and evaluated three models:
- **Logistic Regression** (baseline linear classifier)
- **Random Forest Classifier** (nonlinear ensemble model)
- **XGBoost Classifier** (gradient boosting ensemble model)

*See full implementation in the `main.ipynb` notebook.*

---

### 1. Logistic Regression

**Logistic Regression** served as a baseline model. It is a simple linear classifier often used for binary classification problems. **0** indicates **Low Elo** while **1** indicates **High Elo**.

**Accuracy**: `0.76`

**Classification Report**:

| Class        | Precision | Recall | F1-Score | Support |
| ------------ | --------- | ------ | -------- | ------- |
| **0**        | 0.77      | 0.76   | 0.77     | 63      |
| **1**        | 0.74      | 0.75   | 0.75     | 57      |
| **Accuracy** |           |        | **0.76** | **120** |
| Macro Avg    | 0.76      | 0.76   | 0.76     | 120     |
| Weighted Avg | 0.76      | 0.76   | 0.76     | 120     |

**Confusion Matrix**:

|              | Predicted 0 | Predicted 1 |
| ------------ | ----------- | ----------- |
| **Actual 0** | 48          | 15          |
| **Actual 1** | 14          | 43          |

---

### 2. Random Forest Classifier

**Random Forest** is an ensemble model that builds multiple decision trees to capture complex feature interactions. **0** indicates **Low Elo** while **1** indicates **High Elo**.

**Accuracy**: `0.82`

**Classification Report**:

| Class        | Precision | Recall | F1-Score | Support |
| ------------ | --------- | ------ | -------- | ------- |
| **0**        | 0.82      | 0.84   | 0.83     | 63      |
| **1**        | 0.82      | 0.79   | 0.80     | 57      |
| **Accuracy** |           |        | **0.82** | **120** |
| Macro Avg    | 0.82      | 0.82   | 0.82     | 120     |
| Weighted Avg | 0.82      | 0.82   | 0.82     | 120     |

**Confusion Matrix**:

|              | Predicted 0 | Predicted 1 |
| ------------ | ----------- | ----------- |
| **Actual 0** | 53          | 10          |
| **Actual 1** | 12          | 45          |

---

### 3. XGBoost Classifier

**XGBoost** is a gradient boosting model known for its efficiency and high performance on structured data. **0** indicates **Low Elo** while **1** indicates **High Elo**.

**Accuracy**: `0.80`

**Classification Report**:

| Class        | Precision | Recall | F1-Score | Support |
| ------------ | --------- | ------ | -------- | ------- |
| **0**        | 0.81      | 0.81   | 0.81     | 63      |
| **1**        | 0.79      | 0.79   | 0.79     | 57      |
| **Accuracy** |           |        | **0.80** | **120** |
| Macro Avg    | 0.80      | 0.80   | 0.80     | 120     |
| Weighted Avg | 0.80      | 0.80   | 0.80     | 120     |

**Confusion Matrix**:

|              | Predicted 0 | Predicted 1 |
| ------------ | ----------- | ----------- |
| **Actual 0** | 51          | 12          |
| **Actual 1** | 12          | 45          |

---

### 🔍 ROC Curve & AUC Comparison

To further evaluate model performance, I analyzed **ROC curves** and calculated **AUC (Area Under the Curve)** scores.
![image](https://github.com/user-attachments/assets/4cecd134-3289-4cfd-bf11-5fbdb38d76cd)

| Model              | AUC Score |
|--------------------|-----------|
| Logistic Regression| 0.7566    |
| Random Forest      | 0.8882    |
| XGBoost            | 0.8583    |

- **Random Forest** achieved the highest AUC, confirming its superior ability to distinguish between Low and High Elo players.
- **XGBoost** followed closely, while **Logistic Regression** was notably less effective.

---

### 🎯 Summary

- Ensemble models (**Random Forest**, **XGBoost**) significantly outperform the linear **Logistic Regression**.
- These results highlight that **in-game performance metrics** can reliably indicate a player's skill tier.
- **Random Forest** stands out as the most robust and accurate model for this classification task.



