# FourBishops-AI  
### A Bishop-Heavy Chess Variant Engine | DSA Course Project  
**Members:** Taha Khan (22i-2335), Aawaiz (22i-0845)

FourBishops-AI is a Python-based chess engine built for a custom **Bishop-Heavy** chess variant.  
In this variant, each player begins with **four bishops**, one rook, one knight, one queen, one king, and eight pawns — shifting strategic complexity toward diagonal mobility, bishop coordination, and long-range tactics.

Developed as part of our **Data Structures and Algorithms (DSA)** course project, this engine implements **Minimax**, **Alpha-Beta pruning**, a specialized diagonal-focused heuristic, and full self-play analytics including accuracy measurement, node counts, and confusion matrices.

---

## ♟️ Variant Overview

In this bishop-centric variant:

- Each side has **4 bishops**
- Only **queenside castling** is allowed
- Bishop value and mobility are heavily emphasized
- The game prioritizes:
  - Diagonal control  
  - Bishop-pair synergy  
  - Long-range threats  
  - Open/semi-open rook files  
  - Central knight placements  
  - King safety under diagonal pressure  

The `python-chess` library is used with a custom FEN to enforce the variant.

---

## 🚀 Features

### 🔍 **Search Algorithm**
- Minimax search with **Alpha-Beta pruning**
- Depth-*d* prediction compared against deeper depth-*d+1* “ground truth”
- Node-counting & performance profiling

### 🎯 **Custom Evaluation Heuristic**
Weighted factors include:

- Material (custom bishop-heavy values)
- Mobility difference
- Center-square dominance
- Bishop-pair bonus
- Bishop attack-pressure weighting
- Penalties for blocked bishops
- Rook bonuses on open / semi-open files
- Knight central-outpost bonus
- King-safety penalties under attack

### 📊 **Analytics & Logging**
Generates:

- Move-prediction accuracy  
- Full confusion matrix  
- Per-move CSV logs (`selfplay_stats.csv`)  
- Win/Loss/Draw tracking  
- Average nodes/move and time/move  

### 🤖 **Self-Play Integration**
Runs N games where depth 3 predictions are validated by depth 4 search.

---

## 📈 Results Summary

From 20 self-play games:

- **Prediction Accuracy:** 73.8%  
- **Win/Loss/Draw:** 12–5–3  
- **Total Moves:** 874  
- **Avg. Nodes/Move:** ~10,200  
- **Avg. Time/Move:** ~0.14 seconds  

CSV Outputs:
- `selfplay_stats.csv`: per-move logs  
- `confusion_matrix.csv`: ground-truth vs. predicted move matrix  

---

## 🧪 Testing & Validation

Unit tests verify:

- Queenside-only castling  
- En passant correctness in custom positions  
- Evaluation consistency  
- Search-depth comparison stability  

---

## 🛠️ Implementation Details

### **Language & Libraries**
- Python 3.x  
- python-chess  
- csv, time, math  

### **Suggested Directory Structure**
/FourBishops-AI
├── engine/
│ ├── search.py
│ ├── evaluate.py
│ ├── utils.py
├── selfplay/
│ ├── run_games.py
│ ├── stats_logger.py
│ └── confusion_matrix.py
├── tests/
│ ├── test_castling.py
│ ├── test_enpassant.py
│ └── test_evaluation.py
├── data/
│ ├── selfplay_stats.csv
│ └── confusion_matrix.csv
└── README.md



---

## ▶️ Running the Engine

1. Clone the repository:
git clone https://github.com/your-username/FourBishops-AI.git
cd FourBishops-AI

2. Install Dependencies
pip install python-chess

3. Run Self-Play
python3 selfplay/run_games.py

4. View performance logs in the /data/ directory.


📌 Future Improvements

Variable or adaptive search depth

Pawn-structure evaluation

MCTS (Monte Carlo Tree Search) exploration

Opening book tailored for bishop-heavy play

Simple GUI for move visualization


📚 References

Russell, S., & Norvig, P. (2020). Artificial Intelligence: A Modern Approach (4th Ed.)

python-chess Library — https://python-chess.readthedocs.io

FIDE Laws of Chess (2018)


⭐ If this engine interests you, please star the repository!

co-contributor -> Taha Khan  
