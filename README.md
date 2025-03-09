# DSA210-Term-Project-LoL-Analysis
## Project Overview
This project investigates the effects of various player actions such as  vision score, total minion kills, and objective scores, on the win rate and rank in League of Legends. Additionally, the project compares the relation of having AFK players and early surrenders on teams in different ranks (high vs low). 

Simply by analyzing my own games and other low elo players, I want to emphazise what low elo players can improve and what are the major differences between low elo and high elo games.

---

## Objectives
1. **Understand Skills of Players**
   Determine the relationship between paramters such as vision score, total minion killed, AFK number, Surrender rate, Baron kills and Win/Lose rate.
2. **Identify Significant Parameters**
   Emphazise which parameters have the biggest impact to improve League rank and win rate.
3. **Use Data to Improve Myself**
   Utilize insights from data analysis to identify areas of improvement in my own League of Legends games and enhance my overall performance.
4. **Write a Conclusion**
   Leverage the skills learned in DSA210 and data analysis to offer real solutions and insights that players can apply to improve their gameplay and rank.

---

## Motivation
I have been playing this game since 2012 and achieved the greatest rank which is Challeger. Strategy and skills are important in League, and winning the game is related to players' stats. It will be a fun way of practing my data skills. Also, I will come up with significant results since I have experience in that game. I hope to:
- Realize my mistakes, so that I can improve my gameplay and be a better player.
- Use the data skills that I learnt in the class on something that I have passion.
- Create an original and unusual work.

---

## Dataset and Tool
Riot games provide developer tool api for players. I can access match and player information api, including my own account and matches, in JSON format. I will be using Riot Games developer portal for my project. Here are some parameters I will consider:
- **Player Rank:** Players have ranks from iron to challenger, which shows their ability to play. Iron is the worst, challenger is the best.
- **Win:** A player lose or win a certain match. It is significant to show win/rate ratio.
- **Minion Number:** Each game players farm minions to earn gold in a match. High number of minion means a player is strong in a match.
- **Vision Score:** Vision scores indicates a player is aware of the situation on the map.
- **Game Duration:** It shows the time games end.
- **Baron Takedowns:** Baron is an essential objective and strategy to win the game.
- **Gold Earned:** Players spend gold on items that strengthen themselves.
- **Total Damage Dealt:** It shows the damage a player dealt to enemy team.
- **KDA**: Kill/death/assist ratio shows a players performance in a game.
- **hadAfkTeammate**: If a player is Away From Keyboard, it is really hard to win for their teammates.
- **gameEndedInSurrender:** It shows that a team surrender before game is actually ends by destroying the nexus.
