# 📘 CSL7110 – Assignment 2  
## Min-Hashing and Locality Sensitive Hashing (LSH)

This repository contains the implementation and experimental analysis for Assignment 2 of CSL7110 (Big Data Analytics).  
The assignment focuses on k-grams, Jaccard similarity, Min-Hashing, and Locality Sensitive Hashing (LSH), including applications on the MovieLens 100k dataset.

---

## 📂 Repository Structure

```
ML_with_BigData2/
│
├── question1.ipynb        # k-grams and exact Jaccard similarity
├── question2.ipynb        # Min-Hashing implementation and analysis
├── question3.ipynb        # LSH implementation and S-curve analysis
├── question4.ipynb        # Min-Hashing on MovieLens 100k dataset
├── question5.ipynb        # LSH on MovieLens dataset
│
├── minhash/               # D1.txt, D2.txt, D3.txt, D4.txt
├── ml-100k/               # MovieLens 100k dataset
└── README.md
```

---

# 🔹 Assignment Overview

This assignment covers:

- k-gram construction  
- Exact Jaccard similarity computation  
- Min-Hash signature estimation  
- Locality Sensitive Hashing (LSH)  
- Experimental evaluation on MovieLens 100k dataset  

All implementations were written from scratch as required.

---

# 🔹 Question 1: k-Grams & Exact Jaccard Similarity

Implemented:

- 2-grams (character-based)
- 3-grams (character-based)
- 2-grams (word-based)

For each type:

- Constructed unique k-gram sets (duplicates ignored)
- Computed Jaccard similarity between all document pairs
- Reported 18 similarity values (3 k-gram types × 6 document pairs)

---

# 🔹 Question 2: Min-Hashing

Hash function family used:

h(x) = (a x + b) mod m

Where m > 10,000 to reduce collision probability.

Experiments conducted with:

- t = 20
- t = 60
- t = 150
- t = 300
- t = 600

For each value of t:

- Constructed MinHash signatures
- Estimated Jaccard similarity between D1 and D2
- Compared approximation with exact similarity
- Observed accuracy vs runtime trade-off

---

# 🔹 Question 3: Locality Sensitive Hashing (LSH)

Configuration:

- t = 160 hash functions
- Threshold τ = 0.7

S-curve formula used:

f(s) = 1 − (1 − s^b)^r

Tasks completed:

- Selected suitable (r, b) values for good separation at τ
- Estimated candidate probabilities for all document pairs
- Reported probabilities for 6 document pairs

---

# 🔹 Question 4: Min-Hashing on MovieLens 100k Dataset

Dataset:

- 943 users
- 1682 movies
- Only movie sets considered (ratings ignored)

Steps:

1. Computed exact Jaccard similarity for all user pairs  
2. Reported pairs with similarity ≥ 0.5  
3. Computed MinHash signatures using:
   - 50 hash functions
   - 100 hash functions
   - 200 hash functions  
4. For each configuration:
   - Reported candidate pairs (similarity ≥ 0.5)
   - Computed false positives
   - Computed false negatives
   - Reported averages over 5 runs

---

# 🔹 Question 5: LSH on MovieLens Dataset

Goal:

Find candidate user pairs with similarity:

- ≥ 0.6
- ≥ 0.8

Configurations tested:

| Hash Functions | r  | b  |
|---------------|----|----|
| 50            | 5  | 10 |
| 100           | 5  | 20 |
| 200           | 5  | 40 |
| 200           | 10 | 20 |

For each configuration:

- Implemented banding technique
- Reported false positives
- Reported false negatives
- Averaged results over 5 runs
- Compared performance for different thresholds

---

# 🛠 Implementation Details

Language: Python  

Libraries Used:

- collections
- itertools  
- random  
- time

---

# ▶ How to Run

1. Clone the repository:

```
git clone https://github.com/arjunbaidya/ML_with_BigData2.git
```

2. Navigate into the directory:

```
cd ML_with_BigData2
```

3. Open Jupyter Notebook:

```
jupyter notebook
```

4. Run notebooks in order:

- question1.ipynb  
- question2.ipynb  
- question3.ipynb  
- question4.ipynb  
- question5.ipynb  

---

# 📌 Notes

- All experimental results and observations are included in the submitted PDF report.
- Code is original and written specifically for this assignment.
- Multiple experimental runs were performed wherever required.

---

# 👤 Author

Arjun Baidya  
CSL7110 – ML with Bigdata
