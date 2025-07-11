# Vivian386-association-mini-

# Project Title : Association Rule Mining on Simulated Clothing Transactions

This mini-project demonstrates how to apply **Association Rule Mining** using the **Apriori algorithm** on simulated clothing transaction data.

We go step-by-step through generating data, transforming it, mining frequent itemsets, and finally generating and interpreting association rules.



##  Instructions Followed

###  1. Simulate Transaction Data 

> **Instruction**: Create at least 10 fake transactions in Python.  
> Each transaction should have 2–5 items selected from a pool of at least 8 unique items.

✔️ We created 10 transactions.  
✔️ Each transaction contains 2 to 5 randomly selected items.  
✔️ Items are chosen from a list of **8 clothing items**:
- T-Shirt
- Jeans
- Sneakers
- Jacket
- Cap
- Socks
- Sweater
- Scarf

**Example Output:**
Transaction 1: ['Socks', 'Jeans', 'Cap']
Transaction 2: ['Sneakers', 'Sweater', 'T-Shirt']
Transaction 3: ['Jacket', 'Scarf', 'Sneakers', 'Cap']




###  2. Analyze with Apriori 

> **Instruction**:  
> Convert the data into a one-hot encoded format using pandas.  
> Use the Apriori algorithm (mlxtend) to find frequent itemsets.  
> Set minimum support to 0.3 (30%).

**Step-by-Step:**

####  One-Hot Encoding:

- We use `TransactionEncoder` to convert transaction lists into a binary matrix.
- Each row represents a transaction.
- Each column shows whether an item was present (`True`) or not (`False`).

**Example:**

| T-Shirt | Jeans | Sneakers | ... |
|--------|-------|----------|------|
| True   | True  | False    | ... |
| False  | False | True     | ... |

####  Apriori Algorithm:

- We apply the Apriori algorithm from `mlxtend.frequent_patterns`.
- Minimum support is set to `0.3`, meaning we keep only itemsets that appear in at least 3 out of 10 transactions.

**Example Output:**

support itemsets
0 0.3 (Jeans)
1 0.4 (Sneakers)
2 0.3 (Sneakers, Cap)




### 3. Generate Rules 

> **Instruction**:  
> Generate association rules with:
> - Metric: confidence  
> - Minimum threshold: 0.7  
> Show at least 2 rules and briefly explain what one rule means in everyday language.

#### Rule Generation

- We use `association_rules()` from `mlxtend`.
- We set:
  - `metric='confidence'`
  - `min_threshold=0.7`

**What is Confidence?**  
Confidence is the probability that if someone buys item A, they will also buy item B.

#### 🔹 Example Output:

(Sneakers) (Cap) 0.3 0.75 1.2
(Jeans, T-Shirt) (Sneakers) 0.3 0.75 1.3



### Explanation of a Sample Rule

> **Rule:**  
> If a customer buys **Jeans** and **T-Shirt**, they are also likely to buy **Sneakers**.  
> **Confidence:** 0.75

**What it means in real life:**

> Among customers who buy Jeans and a T-Shirt, **75% also buy Sneakers**.  
> A clothing retailer might use this insight to:
> - Suggest Sneakers when someone adds Jeans and T-Shirts to their cart
> - Place these items closer together in a physical store
> - Create combo discounts to increase basket size



##  How to Run the Project

###  Requirements

Install the required Python libraries:

bash
pip install pandas mlxtend


## Conclusion
This project successfully demonstrates how association rule mining can uncover meaningful patterns in consumer behavior — even with a small, simulated dataset.

Using the Apriori algorithm, we:

Discovered frequent item combinations in clothing purchases.

Generated strong rules with high confidence (≥ 70%) to understand which items are commonly bought together.

Interpreted a sample rule to show how businesses can use such insights to improve marketing strategies, product placement, and cross-selling.

Although the data was randomly generated, the workflow mirrors real-world applications in retail analytics, e-commerce recommendation systems, and inventory planning.

This mini-project shows that even simple data mining techniques can deliver actionable business intelligence when applied correctly.



