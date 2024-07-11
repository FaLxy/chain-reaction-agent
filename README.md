# Chain Reaction Learning Agent

This project implements a Deep Q-Network (DQN) agent that learns to play the Chain Reaction game using reinforcement learning techniques. The agent uses deep learning to evaluate board positions and make strategic moves in this explosive grid-based game.

## Game Overview

Chain Reaction is a strategic board game played on a 4x4 grid where players take turns placing orbs. When a cell reaches its critical mass (determined by the number of adjacent cells), it explodes and distributes orbs to neighboring cells, potentially creating chain reactions. The goal is to eliminate all opponent orbs from the board.

## Features

- **Deep Q-Network (DQN) Implementation**: Neural network-based agent that learns optimal strategies
- **Experience Replay**: Stores and replays past experiences for better learning
- **Epsilon-Greedy Strategy**: Balances exploration vs exploitation during training
- **Visual Interface**: Pygame-based GUI for watching the agent play
- **Configurable Parameters**: Easy-to-modify hyperparameters for experimentation
- **Model Persistence**: Save and load trained weights

## Project Structure

```
├── agent.py          # Main training loop and game execution
├── game.py           # Chain Reaction game implementation and GUI
├── dnq.py            # DQN neural network architecture
├── config.py         # Hyperparameters and configuration settings
├── weights.pth       # Pre-trained model weights
└── Readme.md         # Project documentation
```

## Architecture

The DQN agent consists of:
- **Input Layer**: 16 neurons (4x4 board state)
- **Hidden Layers**: 3 fully connected layers with 256 neurons each
- **Output Layer**: 16 neurons (Q-values for each board position)
- **Activation**: ReLU for hidden layers
- **Loss Function**: Mean Squared Error (MSE)
- **Optimizer**: Adam with configurable learning rate

## Installation

### Prerequisites
- Python 3.6+
- pip package manager

### Dependencies

Install the required packages:

```bash
pip install torch numpy pygame pandas
```

## Usage

### Training the Agent

To train a new agent from scratch:

```bash
python agent.py
```

### Configuration

Modify hyperparameters in `config.py`:

```python
params = {
    'episodes': 1000,           # Number of training episodes
    'learning_rate': 0.001,     # Learning rate for optimizer
    'memory_size': 2000,        # Experience replay buffer size
    'batch_size': 32,           # Training batch size
    'epsilon_decay_linear': 1/1000,  # Exploration decay rate
    'load_weights': True,       # Load pre-trained weights
    'display': False,           # Show game visualization
    'train': True              # Enable training mode
}
```

### Playing Against the Agent

Set `'play': True` in `config.py` to play against the trained agent interactively.

## Model Performance

The agent learns through self-play, gradually improving its strategy by:
- Recognizing winning and losing positions
- Learning to create chain reactions
- Developing defensive strategies
- Optimizing move sequences

## Key Components

### DQN Agent (`dnq.py`)
- Neural network architecture
- Experience replay mechanism
- Epsilon-greedy action selection
- State representation and preprocessing

### Game Engine (`game.py`)
- Chain Reaction game logic
- Board state management
- Move validation and execution
- Explosion mechanics and chain reactions
- Pygame visualization

### Training Loop (`agent.py`)
- Episode management
- Experience collection
- Network training
- Performance tracking

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Future Enhancements

- [ ] Implement different board sizes
- [ ] Add tournament mode with multiple agents
- [ ] Implement Monte Carlo Tree Search (MCTS)
- [ ] Add performance metrics and visualization
- [ ] Create web-based interface

## License

This project is open source and available under the MIT License.
