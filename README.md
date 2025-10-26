# Symbolic-Knowledge-Base-Rule-based-System
# Symbolic KB & Model Checking — Propositional Logic  
**符号知识库与模型检测 — 命题逻辑**

---

## 🧠 Project Overview | 项目概述
This project implements a **rule-based symbolic knowledge base** using **propositional logic** principles.  
The system performs **logical inference** to generate recommendations (movie suggestions) based on predefined facts and rules.  

本项目实现了一个基于**命题逻辑的符号知识库系统**，通过**符号推理 (Symbolic Inference)** 根据用户的偏好（事实）匹配逻辑规则，从而生成电影推荐结果。

---

## ⚙️ Features | 功能特点
- Uses **rule-based reasoning** to infer outcomes from symbolic facts  
- Demonstrates **knowledge representation** using propositional logic  
- Shows how **model checking** can simulate logical validation  
- Outputs movie recommendations based on user preferences  

功能包括：  
- 通过**规则推理**（Rule-based reasoning）从事实中推导结论  
- 展示如何使用**命题逻辑**表示知识  
- 模拟**模型检测 (Model Checking)** 的逻辑验证过程  
- 根据用户兴趣输出电影推荐  

---

## 🧩 Example Code | 示例代码

```python
# Define the rules
rules = [
    # Rule 1: If the user likes action and thriller, recommend Inception
    ({"action": lambda x: x == "thriller"}, ["Inception"]),

    # Rule 2: If the user likes romance and drama, recommend The Notebook
    ({"romance": lambda x: x == "drama"}, ["The Notebook"]),

    # Rule 3: If the user likes sci-fi and adventure, recommend Interstellar
    ({"sci-fi": lambda x: x == True, "adventure": lambda x: x == True}, ["Interstellar"]),

    # Rule 4: If the user likes comedy, recommend The Hangover
    ({"comedy": lambda x: x == True}, ["The Hangover"]),

    # Rule 5: If the user likes animation, recommend Coco
    ({"animation": lambda x: x == True}, ["Coco"]),

    # Rule 6: If the user likes action and adventure, recommend Mad Max: Fury Road
    ({"action": lambda x: x == "action", "adventure": lambda x: x == True}, ["Mad Max: Fury Road"]),

    # Rule 7: If the user likes drama and biography, recommend The Theory of Everything
    ({"drama": lambda x: x == "drama", "biography": lambda x: x == "biography"}, ["The Theory of Everything"]),
]

# Define the initial facts
facts = {
    "action": "thriller",
    "romance": "romance",
    "drama": "drama",
    "sci-fi": False,
    "adventure": True,
    "comedy": False,
    "animation": False,
    "biography": False
}

# Apply the rules to the facts
recommendations = []
for rule, action in rules:
    if all([rule[k](v) for k, v in facts.items() if k in rule]):
        recommendations += action

# Print the recommended movies
if recommendations:
    print("We recommend the following movies based on your preferences: ")
    for movie in recommendations:
        print("- " + movie)
else:
    print("We could not find any suitable movie recommendations based on your preferences.")
🧾 Example Output | 示例输出
bash
Copy code
We recommend the following movies based on your preferences:
- Inception
(Explanation: because the user likes action and thriller, the system logically infers that Inception is a good match.)
（说明：因为用户喜欢动作和惊悚类型，所以系统通过规则推理推荐了《盗梦空间》。）

🧮 Concept Summary | 理论总结
Symbolic Knowledge Base (符号知识库): stores facts and logical rules

Inference Engine (推理引擎): applies rules to derive new conclusions

Model Checking (模型检测): verifies logical consistency of the rules

Propositional Logic (命题逻辑): uses simple true/false statements for reasoning
