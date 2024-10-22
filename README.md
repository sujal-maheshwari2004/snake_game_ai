# Snake Game AI

This project is an AI-powered version of the classic Snake game. The AI agent learns how to play the game using reinforcement learning, specifically Deep Q-Learning (DQN). The game is built using `Pygame`, and the AI's objective is to maximize the score by eating food and avoiding collisions with walls or itself.

## Table of Contents

- [Installation](#installation)
- [Project Structure](#project-structure)
- [Game Rules](#game-rules)
- [AI Details](#ai-details)
- [Usage](#usage)
- [Acknowledgements](#acknowledgements)

## Installation

Ensure you have Python installed. You can install the necessary dependencies by running:

```bash
pip install -r requirements.txt
```

Required dependencies:
- `pygame`
- `numpy`
- `torch`
- `matplotlib` (optional, for visualizing training progress)

## Project Structure

The main files in the project are:

```plaintext
.
├── agent.py            # DQN agent that controls the snake
├── arial.ttf           # Font file for game
├── helper.py           # Utility functions for reward shaping and visualizations
├── model.py            # Neural network model for Q-learning
├── game.py             # Pygame implementation of the Snake game
├── requirements.txt    # Python dependencies
├── README.md           # Project documentation
```

### File Descriptions:

- **game.py**: Implements the Snake game using Pygame. The AI controls the snake automatically by interacting with the environment.
- **agent.py**: Defines the Deep Q-Learning (DQN) agent used to train the snake AI.
- **model.py**: Contains the neural network model architecture used by the agent for learning Q-values.
- **helper.py**: Includes helper functions for visualizing training progress and shaping rewards.

## Game Rules

1. The AI controls the snake, which moves around the screen in a grid of 20x20 pixel blocks.
2. The snake grows when it eats food, and the objective is to eat as much food as possible without colliding with the walls or its own body.
3. The game ends if the snake crashes into the boundaries of the game window or into itself.
4. The score increases by 1 each time the snake eats food.

## AI Details

The AI is trained using the Deep Q-Learning algorithm, which learns to make optimal moves by interacting with the game environment. The AI's goal is to maximize the score by making decisions based on the current game state.

- **State Representation**: The state is represented by the snake's current direction, the location of the food, and the snake's position relative to itself and the walls.
- **Action Space**: The possible actions are:
  - `Straight`
  - `Right`
  - `Left`
- **Reward System**:
  - +10 for eating food
  - -10 for colliding with the walls or itself
  - Small penalty for each frame to encourage faster completion of the task.

## Usage

### Train the AI

To train the AI to play the Snake game, run the following command:

```bash
python agent.py
```

The training loop will start, and the AI will begin learning how to play the game. The performance will improve as the training progresses.

### Visualize Training Progress

If you'd like to visualize the AI's training performance, use:

```bash
python helper.py
```

This will generate graphs showing the agent's score over time and its progress.

## Acknowledgements

- This project is built using Pygame for the Snake game environment.
- The AI is powered by Deep Q-Learning, a reinforcement learning algorithm for training agents to play games.
