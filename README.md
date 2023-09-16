# FrozenLake-Problem
Reinforcement Learning Algorithm

# FrozenLake Problem:

The "deterministic" FrozenLake toy problem is a grid-world environment in reinforcement learning, where the agent must navigate a grid of frozen lake tiles to reach a goal tile while avoiding holes in the ice. It is called "deterministic" because the agent's actions always result in the intended state transitions. That is, if the agent takes an action to move left, it will always end up in the tile to the left of its current position, assuming there are no holes or walls blocking the way. The goal is to find an optimal policy that maximizes the expected reward, which is a function of the agent's actions and the resulting states. The FrozenLake environment has different variations, including deterministic, stochastic, and slippery, each with different levels of difficulty and randomness in state transitions.

# Here is my basic code structure:

I have defined a class GameState that represents the current state of the game. The class has the following methods:

__init__(self, position=starting_state): Initializes the game state with a starting position.
get_score(self, position): Returns the score for a given position.
is_game_over(self): Checks if the game is over (i.e., if the current position is either the goal state or one of the hole states).
get_nxt_pos(self, action): Determines the next position of the agent based on the action taken.
The __init__ method takes an optional position parameter that represents the starting position of the agent. The get_score method takes a position parameter and returns the score for that position. If the position is the ending state, the method returns a score of 10. If the position is one of the hole positions, the method returns a score of -5. Otherwise, the method returns a score of -1.
The is_game_over method checks if the game is over by checking if the current position is either the goal state or one of the hole states. If the current position is either the goal state or one of the hole states, the method returns True. Otherwise, the method returns False.

The get_nxt_pos method takes an action parameter and determines the next position of the agent based on the action taken. If the action is 0, the method subtracts 1 from the current row position. If the action is 1, the method adds 1 to the current row position. If the action is 2, the method subtracts 1 from the current column position. If the action is 3, the method adds 1 to the current column position. The method then checks if the next position is within the bounds of the game board (i.e., a 5x5 grid). If the next position is within the bounds of the game board, the method returns the next position. Otherwise, the method returns the current position.

Then we have used a reinforcement learning agent using Q-learning to solve the FrozenLake toy problem.

The agent is defined in the Agent class. It initializes the agent's parameters including the learning rate (alpha), discount factor (gamma), and exploration vs exploitation trade-off (epsilon). It also initializes a Q table, which is a dictionary containing the estimated value of each possible action from each possible state.

The get_max_action_value method takes a position and finds the action with the highest action value estimate for that state using the Q table.

The Q_Learn method performs off-policy Q-learning for the agent. It takes the number of episodes as input and updates the Q table using the temporal difference (TD) update rule. The method chooses an action using an epsilon-greedy policy based on the Q table and updates the Q table based on the observed reward and the maximum action value estimate for the next state.

The print_values method prints the action value estimates in a formatted way.

Overall, this code implements an agent that uses Q-learning to solve the FrozenLake toy problem, and allows for tuning of the learning rate, discount factor, and exploration vs exploitation trade-off.
![image](https://github.com/Deyanira18/FrozenLake-Problem/assets/79983539/94ddb09b-19c3-446c-b8f5-67593ed81f1f)
