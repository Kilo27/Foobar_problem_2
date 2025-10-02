# ✨Foobar — Problem 2: Currency Conquest

## Quick overview
Convert one of several buy-ins from its original currency into USD using a sequence of currency exchanges that yields the largest final USD value. Your program must report the chosen buy-in, the original amount and currency, the final USD value, the profit, and the conversion path.

---

## 🤖 Files in this repo / setup
- Clone the repository:
```powershell
git clone https://github.com/BenBastianelli/Foobar_problem_2.git
```
- Important data files used by the grader:
  - `Buy-ins.csv`
  - `test_exchange_rates.csv`
- When submitting locally with the provided GUI/executable, make sure your solution file and the executable are in the same directory.

---

## ✉️ How to submit
1. Name your file using: `TeamName_Solution.py` (example: `TeamFoo_Solution.py`).  
2. Put your solution file in the same directory as `Grade_code.exe`.  
3. Run `Grade_code.exe`, choose your team, and click **Grade Selected** to upload/grade on the leaderboard.

> Note: You can also test locally by running:
```powershell
python TeamName_Solution.py test_exchange_rates.csv Buy-ins.csv
```
The grader will run your script with the command-line arguments in that order.

---

## 📁 Input file formats

- `Buy-ins.csv` (header included)
  - Columns: `name,amount,currency`
  - Example row: `Alice,150.0,EUR`

- `test_exchange_rates.csv` (header included)
  - Columns: `from,to,rate`
  - Meaning: `1 unit of "from"` converts to `rate` units of `to`.
  - Example row: `EUR,USD,1.10`

---

## Required invocation
Your program must accept two command-line arguments:
1. path to the exchange rates CSV (e.g., `test_exchange_rates.csv`)
2. path to the buy-ins CSV (e.g., `Buy-ins.csv`)

If your program doesn't accept these command line arguments ensure that the paths specified in your solution are to the correct CSV files or else the grader will not work!

Example:
```powershell
python TeamName_Solution.py test_exchange_rates.csv Buy-ins.csv
```

---

## 👌 Required output (strict labels and formatting)
To ensure automatic grading, your program must print exactly five labeled lines (labels and punctuation shown below). Values should be numeric (floating point acceptable) and currency codes uppercase 3-letter ISO codes.

Exact labels (case-sensitive label words are shown; the grader accepts small case differences in some places but follow this exactly to be safe):

Buy-in Index: <integer index in CSV, 0-based or 1-based — use the same index you list in your CSV>  
Original Amount: <numeric> <CUR>  
Final USD Amount: <numeric>  
Total Profit: <numeric>  
Conversion Path: <CUR1> -> <CUR2> -> ... -> USD

Example:
```
Buy-in Index: 1
Original Amount: 150.0 EUR
Final USD Amount: 165.00
Total Profit: 15.00
Conversion Path: EUR -> GBP -> USD
```

- Conversion Path should use arrows `->` (the grader also accepts `→`) and list currencies in order.
- The currency in the Original Amount must be a three-letter uppercase code (e.g., `EUR`, `JPY`).
- Keep any extra debugging or logging off stdout (or ensure the required five lines appear exactly as specified).

---

## ✅ Acceptance criteria and scoring (summary)
Total: 150 points (rubric used by the grader)
- Load data using pandas in a single method: 15 pts  
- Build a directed graph representing exchanges: 37 pts  
- Implement a path traversal algorithm that finds the most profitable path: 75 pts  
- Produce the required textual output (format + values): 23 pts

---

## 🔢 Correctness & numeric tolerances
- Floating-point answers are accepted within absolute error ≤ 1e-3.
- Execution should complete in a reasonable time (aim for <10s on a typical modern laptop). The grader may not enforce timeouts now, but long-running or infinite loops will block grading.

---

## 🛑 Allowed / disallowed
- Allowed: Python standard library, `pandas`, `numpy`, `networkx` (if you plan to use it).
- Disallowed: Calling external web APIs, reading files outside the provided inputs, or attempting to programmatically modify other teams’ files.

---

## 🧪 Small sample 
Buy-ins (`Buy-ins.csv`):
```
name,amount,currency
A,100,EUR
B,200,JPY
```
Exchange rates (`test_exchange_rates.csv`):
```
from,to,rate
EUR,USD,1.1
JPY,USD,0.007
JPY,EUR,0.008
```
One valid output (if buy-in A is best):
```
Buy-in Index: 0
Original Amount: 100.0 EUR
Final USD Amount: 110.0
Total Profit: 10.0
Conversion Path: EUR -> USD
```

---

## ⚠️ Notes for fairness and grading
- The autograder looks for:
  - use of `pandas.read_csv` (single load method)
  - explicit graph-building constructs (dict/defaultdict, NetworkX, or adjacency structures)
  - path traversal algorithmic patterns (use of priority queue/heap, BFS/DFS/relaxation, etc.)
- If you plan to use matrix/NumPy-only methods, they may not be recognized by the structural checks — prefer clear graph structures to get full structural credit.

---

