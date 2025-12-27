# ♟️ Dynamic Learning Chess AI with Adaptive Behavior

This project implements a self-learning Chess Engine that doesn't just play moves, but **adapts its personality** based on game outcomes. By combining classical search algorithms with modern optimization techniques, the AI learns to balance aggression and defense dynamically through a specialized meta-parameter framework.

---

## 🚀 The Core Concept

Most chess engines use static evaluation weights. This project introduces a **Meta-Parameter ()** that acts as an "aggression slider". The AI evaluates positions numerically through feature extraction and uses **Conjugate Gradient Descent** to learn optimal weights for different board characteristics.

### 🧠 How It Thinks

The engine evaluates a board position  using a learned function:




* **Weight Vector ():** Represents learned values for five key features: Material Balance, Mobility, Center Control, King Safety, and Pawn Structure.


* **Meta-Parameter ():** Allows dynamic adjustment of playstyle. When , the AI becomes more aggressive (allowing material sacrifices for activity); when , it prioritizes defensive, positional play.


* **Optimization:** The AI minimizes a loss function using **Conjugate Gradient** for weights and **Golden Section Search** to fine-tune the aggression parameter based on win rates.



---

## 📊 Performance Comparison

In simulations against a "Tough Opponent" (a positional heuristic engine), the Adaptive AI significantly outperformed static strategies:

| Metric | Player Simulator (Static) | Dynamic AI (Adaptive) |
| --- | --- | --- |
| **Win Rate** | 41% | 57% |
| **Draw Rate** | 59% | 43% |
| **Avg. Moves (Wins)** | 65.49 | 41.42 |

**Key Insight:** The Dynamic AI achieved **16% more victories** and won with **~37% fewer moves**, indicating more efficient and decisive decision-making.

---

## 🛠️ Technical Stack

* **Search:** Minimax with Alpha-Beta Pruning to eliminate unnecessary branches.


* **Optimization:** Conjugate Gradient optimization to iteratively update feature weights and avoid the slow convergence of basic Gradient Descent.


* **Adaptive Tuning:** Golden Section Search to find the lowest point of the loss curve for meta-parameter tuning.


* **Framework:** Built with Python, leveraging `python-chess` for game logic and `multiprocessing` for parallelized top-level move evaluation.

---

## 📂 Project Structure

* `main code.ipynb`: Core architecture including the `ParallelMinimaxSearcher`, `ChessFeatureExtractor`, and the `DynamicChessEvaluator`.
* `presentation.pptx`: Technical presentation detailing the mathematical framework, gradients, and loss functions.
* `final stats.ipynb`: Scripts for processing CSV results and generating performance metrics.
* `AiVsOpponent.csv`: Data generated from 100 simulated games of the AI against the tough opponent.

---

## 🔮 Future Possibilities

While the current engine demonstrates strong adaptive capabilities, several areas remain open for expansion:

* **Deep Feature Extraction:** Moving beyond handcrafted features to a neural network-based feature extractor (CNNs) for more nuanced position understanding.
* **Reinforcement Learning (RL):** Implementing a full Temporal Difference (TD) learning approach, similar to AlphaZero, to allow the AI to learn solely from self-play without external datasets.
* **Opening Book Integration:** Currently, the AI evaluates from scratch; adding a grandmaster opening database would improve its early-game efficiency.
* **Time Management Heuristics:** Dynamically adjusting search depth based on the complexity of the position and remaining clock time.

---

## 📜 License

This project is publicly available under the **MIT License**. You are free to use, modify, and distribute the code, provided that the original copyright and license notice are included.

---
