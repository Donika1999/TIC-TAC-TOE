# Tic-Tac-Toe Game using Field Programmable Gate Arrays
Tic-Tac-Toe is a very popular paper-and-pencil game in a 3x3 grid for two players. In this project, a
player plays the Tic Tac Toe game with a computer.

The machine is playing a defensive game and hence, the human player will always move first. Each
time the player moves, the machine waits for two seconds before making its move.

Input is be a 3 X 3 array, a reset button, and a switch SW1. If SW1 is off, the computer always wins
if possible, or draw (nobody wins) if winning is not possible. If SW1 is on, part of the machine’s logic
gets bypassed so that the player can win occasionally. Output will be a 3 X 3 array of LEDs with a
red and a green LED in each square. Two LEDs are used to indicate player wins or computer wins.
If the game is a draw, both LEDs light.

![TTT grid](/ttt.png)

The input 2-D array is initialized with 0. Hence, 0 is stored into a position when neither the player
or computer played in that position. Similarly, 1 (X) is the value to be stored when the player played
in the position and 2 (O) is the value to be saved when the computer played in the position.

It is assumed that the player will not make any illegal move and he is aware of empty sqares.

The player/ computer wins the game when successfully placing three similar (1-Xs) or (2-Os) values
in the following row pairs: (1,2,3); (4,5,6);(7,8,9); (1,4,7); (2,5,8);(3,6,9); (1,5,9);(3,5,7). The winner
detecting circuit is designed to find the winner when the above winning rule is matched.

### Algorithm

* The player makes the first move.
* If player starts in center (2,2) , machine plays corner [ (1,1), (1,3), (3,1), (3,3) ]; otherwise,
machine plays center (2,2).
* After each subsequent move by the player, the machine checks the following in sequence:
    * Two O’s in a row: machine plays in the third square and wins.
    * Two X’s in a row: machine plays in the third square to block player.
    * If it is the machine’s second move, a special move may be required: If player’s first two
moves are opposite corners, the machine’s second move must be side. If player’s first move
is center, the machine’s second move should be corner if rule (b) does not apply.
    * Two intersecting rows each contain only one X: Machine plays in the square at the intersection of the two rows (this blocks the player from forcing a win).
    * If there is no better move, play anywhere.
  
### SM Chart
 
 ![smchart](/smc.png)
    
### Further Explorations
 
 * Illegal moves can be detected and avoided.
 * Calculate the number of spaces left after each move.
 * A completely different approach would be to have no rules at all, but instead to write a program.
The program might recognize an immediate win and the threat of an immediate loss, but otherwise it would move randomly and record the results. If the computer loses a game, it would
remember the last unforced choice it made in that game, and keep a record to try something
else in the same situation next time. The result, after many games, would be a complete list of
all possible sequences

### References

1. DIGITAL DESIGN: PRINCIPLES AND PRACTICES by John F. Wakerly
2. https://people.eecs.berkeley.edu/~bh/pdf/v1ch06.pdf

**This project has been performed under the guidance of Prof. Biswajit Mishra.**
