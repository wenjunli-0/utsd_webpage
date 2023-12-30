# Unsupervised Training Sequence Design: Efficient and Generalizable Agent Training, AAAI-2024

<p align="center">
  <h3 align="center">Wenjun Li, Pradeep Varakantham</h3>
  <p align="center">
    Singapore Management University
    <br>
    <a href="https://aaai.org/aaai-conference/">[Paper]</a>
  </p>
</p>

![image](figures/UTSD.png#pic_center)


## 1. Introduction
To train generalizable Reinforcement Learning (RL) agents, researchers recently proposed the Unsupervised Environment Design (UED) framework, in which a teacher agent creates a very large number of training environments and a student agent trains on the experiences in these environments to be robust against unseen testing scenarios. For example, to train a student to master the “stepping over stumps” task, the teacher will create numerous training environments with varying stump heights and shapes. In this paper, we argue that UED neglects training efficiency and its need for very large number of environments (henceforth referred to as infinite horizon training) makes it less suitable to training robots and non-expert humans. In real-world applications where either creating new training scenarios is expensive or training efficiency is of critical importance, we want to maximize both the learning efficiency and learning outcome of the student. To achieve efficient finite horizon training, we propose a novel Markov Decision Process (MDP) formulation for the teacher agent, referred to as Unsupervised Training Sequence Design (UTSD). Specifically, we encode salient information from the student policy (e.g., behaviors and learning progress) into the teacher’s state space, enabling the teacher to closely track the student’s learning progress and consequently discover the optimal training sequences with finite lengths. Additionally, we explore the teacher’s efficient adaptation to unseen students at test time by employing the context-based meta-learning approach, which leverages the teacher’s past experiences with various students. Finally, we empirically demonstrate our teacher’s capability to design efficient and effective training sequences for students with varying capabilities.


## 2. Background
To train generali


## 3. Method
To train generali



## Acknowledgement
This research/project is supported by the National Research Foundation Singapore and DSO National Laboratories under the AI Singapore Programme (AISG Award No: AISG2-RP- 2020-017).
