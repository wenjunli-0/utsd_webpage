# Unsupervised Training Sequence Design: Efficient and Generalizable Agent Training, AAAI-2024

<p align="center">
  <h3 align="center">Wenjun Li, Pradeep Varakantham</h3>
  <p align="center">
    Singapore Management University
    <br>
    <a href="https://www.ijcai.org/proceedings/2023/0601.pdf">[Paper]</a>
  </p>
</p>


## 1. Introduction
Agent decision-making using Reinforcement Learning (RL) heavily relies on either a model or simulator of the environment (e.g., moving in an 8x8 maze with three rooms, or playing Chess on an 8x8 board). Due to this dependence, small changes in the environment (e.g., positions of obstacles in the maze, size of the board) can severely affect the effectiveness of the policy learned by the agent. To that end, existing work has proposed the Unsupervised Environment Design (UED) framework to train RL agents on an adaptive curriculum of environments (generated automatically) to improve performance on out-of-distribution (OOD) test scenarios. Specifically, existing research in UED has employed the potential for the agent to learn in an environment (captured using *regret*) as the key factor in selecting the next environment(s) to train the agent. However, such a mechanism can select similar environments (with a high potential to learn) thereby making agent training redundant in all but one of those environments. To that end, we provide a principled approach to adaptively identify diverse environments based on a novel distance measure relevant to environment design. We empirically demonstrate the versatility and effectiveness of our method in comparison to multiple leading approaches for unsupervised environment design on three distinct benchmark problems used in literature.

