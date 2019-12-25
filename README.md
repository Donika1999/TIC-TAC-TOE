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
