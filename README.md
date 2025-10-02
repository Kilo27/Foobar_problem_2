<div align ="center">
  
# Foobar_problem_2 <br>

</div>

<div align="center">

## 💻 User guide for setting up 💻

</div>

  1. Congrats on navigating to this repository as that is our first step!<br>
  2. As you can see this repository has a few files and an executable that is necessary to submit answers for this question,<br>
  The way you can easily move these to your own local directory is with the following command <br>
  ``` 
    git clone https://github.com/BenBastianelli/Foobar_problem_2.git 
  ```
<br>
Once this repository is cloned you should have access to all of the files and the problem is now ready to be attempted!!

<br> <br> 

<div align="center">
  
## ✅ Submitting a solution ✅ <br>

</div>

**submitting a solution** is a relatively straight forward process and has everything to do with the executable you pulled when you cloned this repository ` Grade_code.exe ` <br>
to submit a solution you **must** run this executable and complete the following<br>
1. Ensure your file name for submission follows the following format : ` TeamName_Solution.py ` <br> <br>
2. Click your team name when it pops up on the executable screen <br>**(NOTE THE EXECUTABLE AND SOLUTION FILE MUST BE LOCATED IN THE SAME DIRECTORY)** <br> <br>
3. Click the *"Grade Selected"* button option <br> <br>
4. Your script will be automatically graded and your score on the leader board will be updated <br> <br>

<br>
after this click the "grade code" button at the bottom of the executable and (after almost crashing) the executable will return your grade and update it on the live leaderboard

<div align ="center">
  
# Foobar_problem_description <br>

</div>

# 💱 Foobar 2025 Q2: Currency Conquest

## 🌍 Background
*Global finance is a maze—and you're the strategist who sees the way through.*

## 🎯 Your Mission
You're tasked with navigating a web of international currency exchanges. Each buy-in represents an investment in a foreign currency. Your goal? Convert it to USD through the most profitable path—without retracing your steps.

## 🗂️ Dataset Overview
You’ll be working with two input files:

- **buyins.csv:** Initial investments in various currencies and amounts.
- **exchange_rates.csv:** Directed graph of currency conversions in the format `TO,FROM,RATE`.

*Note: All datasets are in CSV format. You must use Python to write your solution however.*

## 🔍 Conversion Rules
- Each currency can be visited **only once** per path.
- No cycles, no arbitrage loops.
- Maximize the final USD amount.

## 🧠 Objective
For each buy-in:

- Determine the most profitable conversion path to USD.
- Ensure each currency is visited at most once.
- Return the buy-in that yields the highest USD profit.

## 📥 Input Format
- **buyins.csv:** List of buy-ins with currency and amount.
- **exchange_rates.csv:** Conversion rates in the format `TO,FROM,RATE`.

## 🏁 Goal
> “Find the most optimal path a buy-in can take from its original currency to USD. Once completed for all buy-ins, return the one which makes the most profit.”

## 🧮 Scoring Breakdown (150 pts total)
- 📥 Load data using pandas in a single method: **15 pts**
- 🧭 Build a traversable data structure: **37 pts**
- 🛣️ Implement path traversal algorithm: **75 pts**
- ✅ Return correct output in expected format: **23 pts**

## 📌 Output Format
To earn full marks, your output must follow this structure:
```
Buy-in index : (index in the CSV of the buy-in)
Original Amount : value + currency 
Final USD amount : value 
Total Profit : value 
Conversion Path : USD -> EUR -> GBP -> ...
```
## ❗ Tips
- Use pandas for data loading (in one method only).
- Avoid cycles in your pathfinding logic.
- Format your output exactly as shown.

