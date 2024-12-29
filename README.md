<p align="center">
  <img src="https://github.com/user-attachments/assets/00155445-09a3-4f7c-8e8f-68d876f6cbf0" alt="logo">
</p>

# XODIA Reinforcement Learning Competition

This repository contains the code and implementation details for the **XODIA Reinforcement Learning Competition (April 2024)**, where I secured **3rd prize** among over 30 participants. The competition focused on creating an AI bot capable of playing the game *Pocket Tanks* by developing an optimized reward function.

## Overview

The primary task was to design and implement a reward function that enables the AI bot to make strategic decisions and maximize its score in *Pocket Tanks*. The competition evaluated the bot's performance in various scenarios against other AI agents.

## Python Packages Used

- `Xodia24`: A package developed for the competition.
- `stable_baselines3`: A popular library for reinforcement learning.
- `PyTorch`: Used for training the reinforcement learning model.

## Reward Function Implementation

The reward function uses complex mathematical equations to determine the reward based on the bullet type and distance (`x`) to the opponent:

- **Standard Shell (bullet_type == 0)**: Reward based on `y = -0.04 * x² + 160` for `x <= 25`. Otherwise, -60.
- **Triple Threat (bullet_type == 1)**: Reward based on `y = -0.0005 * x² + 90` for `x <= 240`. Otherwise, -50.
- **Long Shot (bullet_type == 2)**: Reward `y = -0.5 * x + 100` for `x <= 200`. Otherwise, -20.
- **Heavy Impact (bullet_type == 3)**: Reward `y = -0.002 * x² + 200` for `x <= 250`. Otherwise, -100.
- **Blast Radius (bullet_type == 4)**: Reward based on `y = -0.003 * x² + 100` for `x <= 80`. For `80 < x <= 100`, reward 60; for `100 < x < 110`, -20; else, -30.
- **Healing Halo (bullet_type == 5)**: Reward `y = -0.04 * x² + 130` for `x <= 25`. For `25 < x <= 28`, reward 40; else, -80.
- **Boomerang Blast (bullet_type == 6)**: Reward `y = 1200 / (x + 10) + 100` for `x <= 200`. Otherwise, -70.

This approach leverages complex mathematical equations to guide the AI's decisions based on different bullet types and distances.


## Results

- The bot achieved **consistent high scores** across test matches.
- Secured **3rd place** in the competition with a well-balanced reward function.
- Watch **AI Wars** : [click here](https://youtu.be/fUzpJypN_Hg?si=EIBE7uiDjvoIliQ_)


## Acknowledgments

- The XODIA organizing team for hosting the competition.
- Fellow participants for inspiring innovative solutions.
