# HangMan_Agent

# Hangman Hybrid Agent — HMM + Reinforcement Learning

This project implements a **hybrid AI agent** that learns to play the game of **Hangman** using a combination of:
- **Hidden Markov Model (HMM)** for letter sequence probability estimation.
- **Policy Gradient Reinforcement Learning** for adaptive letter guessing.

The system blends probabilistic modeling and reinforcement learning to progressively improve its accuracy and efficiency.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Project Overview

The goal is to teach a machine to play Hangman intelligently — guessing letters of a hidden word using learned patterns instead of random choices.

The agent:
1. Learns letter transitions from a word corpus using an HMM.
2. Uses reinforcement learning to optimize its guessing strategy.
3. Achieves a higher success rate over thousands of training episodes.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Notebook

**File:** [`ML_Hackathon.ipynb`](./ML_Hackathon.ipynb)

This notebook performs the entire workflow:
1. Mounts Google Drive and loads the dataset (`corpus.txt`, `test.txt`).
2. Trains or loads the **HMM model**.
3. Trains the **Policy Gradient Reinforcement Learning agent**.
4. Evaluates model accuracy on test data.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Folder Structure (Google Drive)
MyDrive/

└── ML_Hackathon/

├── Data/

│ ├── corpus.txt # Training corpus for HMM

│ ├── test.txt # Test dataset

│ └── hangman_hmm.pkl # Saved trained HMM model

└── Hangman_Hybrid_Agent.ipynb

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## How to Run (Google Colab)

1. Upload the following to your Google Drive:

/MyDrive/ML_Hackathon/Data/

├── corpus.txt

└── test.txt


2. Open the notebook in **Google Colab**.
3. Run all cells sequentially.

The notebook will automatically:
- Mount your Drive  
- Load or train the HMM model  
- Train the hybrid RL policy  
- Evaluate results on the test set  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Example Output

HMM trained on corpus.
Training tuned policy...
Ep 5000 | R=220.4 | Base=180.1 | Word=reactor
Ep 25000 | R=480.9 | Base=440.6 | Word=machine
Evaluating...
Results: Success=50.4% | Wrong=12040 | Repeats=210 | Score=2350.1


---

##  Key Components

|      Component       |                          Description                              |
|----------------------|-------------------------------------------------------------------|
| **LetterHMM**        | Trains letter-to-letter transition probabilities from the corpus. |
| **SmartWordMatcher** | Filters candidate words matching the Hangman pattern.             |
| **HybridPolicy**     | Learns to combine HMM and dictionary probabilities using RL.      |
| **HangmanEnv**       | Simulates Hangman gameplay with tuned reward functions.           |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

##  Evaluation Metrics

|     Metric       |              Description            |   Goal   |
|------------------|-------------------------------------|----------|
| **Success Rate** | % of correctly guessed words        | ↑ Higher |
| **Wrong**        | Total wrong guesses                 | ↓ Lower  |
| **Repeats**      | Repeated guesses                    | ↓ Lower  |
| **Final Score**  | Weighted overall performance metric | ↑ Higher |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

##  Learning Dynamics

- **R (Reward):** Cumulative reward per episode — should increase as the model learns.  
- **Base (Baseline):** Smoothed average reward — tracks general performance trend.  
- Ideally, both values **rise steadily** as training progresses.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

##  Authors
- Anirudha Rao
- Adarsh R Menon
- Aman Kumar Mishra
- Akshay Kumar K
