# Quixo

components:
  - LearningGame: the re-definition of the Game class for training, considering symmetries when generating possible moves.
  - MyPlayer: a player that makes random moves but can identify and play winning moves.

agents:
  - Initially, I attempted to create a Q-Learning agent. When it encounters a state that is symmetric to another state already in the Q-table, it uses the existing entry instead of creating a new one. However, this alone was not sufficient to reduce the size of the Q-table to a reasonable dimension. Consequently, I opted to design a new, more effective agent that does not rely on a table.
  - In the Minimax Agent (Applied Alpha-Beta Pruning), I can determine the depth of its evaluation of future states. The evaluation of states is conducted as follows:
    - If the winner is 1, return -inf
    - If the winner is 0, return inf.
    - Assign higher points to the player with more tiles in the same column/row/diagonal.
    - Give greater importance to columns and rows that are on the perimeter, as completing a line in these positions is simpler compared to the central ones.
