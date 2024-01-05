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


## 2. Motivation
The existing UED algorithms seek to generate an infinite number of environments and open-endedly train the student based on the regret notion we will introduce regret in detail in Section 2. For example, to help the student generalize to a variety of mazes, the state-of-the-art algorithm (Parker-Holder et al. 2022) creates hundreds of thousands of training mazes, but such a massive amount of training is usually low- efficient and the student cannot learn anything in most of the mazes. Consequently, such infinite training is less applicable to real-world tasks where training efficiency is critical. On top of achieving well-generalizing agents, we also want to maximize the agent training efficiency with as few environments or tasks as possible in real-world tasks. For example, to train a robot to climb stairs, we cannot afford to create tens of thousands of real stairs with various heights and slopes in the laboratory. Instead, it is desirable for the robot to gen- eralize well to a variety of stairs with just a few training environments. Besides, to teach non-expert humans cooking skills, we want to make sure the cooking tasks in the training curriculum are optimally arranged regarding both training efficiency and training outcome. Both example training tasks require efficient finite horizon training, which cannot be addressed by the UED framework.


## 3. Method
We employed the Quality Diversity approach to select diverse vali- dation environments and subsequently encode salient information about the student policy into the state space of the teacher agent. This allows the teacher to track the learning progress and overall ability of the student during training. To make the teacher more applicable to real-world tasks, we further enhance its transferability to new students by utilizing the context-based meta-RL method. In our experiments, we validated that the proposed meta-teacher can not only create efficient and effective finite horizon training sequences but is also capable of rapidly transferring to new students with varying learning properties.

An illustration of using the QD method to select a set of environments that will elicit diverse agent behaviors. 
![image](figures/QD_method.png#pic_center)


An overview of the proposed algorithm is provided in the below figure. 
![image](figures/algo_overview.png#pic_center)


## Acknowledgement
This research/project is supported by the National Research Foundation Singapore and DSO National Laboratories under the AI Singapore Programme (AISG Award No: AISG2-RP- 2020-017).
