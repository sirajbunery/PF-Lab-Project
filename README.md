# PF-Lab-Project
**Tic-Tac-Toe-with-MiniMax-algorithm**
Allows for tracking of scores, repeated play, alternating turns and planned to have 2 AIs, with one done using minimax algorithm

**Objectives: **
 
Our project name is Tic-Tac-Toe game. This game is very popular and is fairly simple by itself. It is actually a two player game. In this game, there is a board with n x n squares. In our game, it is 3 x 3 squares. The goal of Tic-Tac-Toe is to be one of the players to get three same symbols in a row - horizontally, vertically or diagonally - on a 3 x 3 grid. 
 
**1.	Overview: **
 
This game can be played in a 3x3 grid.The game can be played by two players. There are two options for players: 
 
  	 (a) Human       (b) Computer(AI)  
 

**Theory of Game: **

A player can choose between two symbols with his opponent, usual games use “X” and “O”. If first player choose “X” then the second player have to play with “O” and vice versa.  
A player marks any of the 3x3 squares with his symbol (may be “X” or “O”) and his aim is to create a straight line horizontally or vertically or diagonally with two intensions: 

a)	Create a straight line before his opponent to win the game. 

b)	Restrict his opponent from creating a straight line first. 

In case logically no one can create a straight line with his own symbol, the game results a tie. 

Hence there are only three possible results – a player wins, his opponent (human or computer) wins or it’s a tie. 

**Strategy:**

The game of Tic Tac Toe has limited winning conditions.

Meaning there’s only a few ways for a winning condition. The first move and second move dictate often how the game will go. The rest depends upon either of the player making mistakes in-order for the other to win.

The first player to make a move to ensure the best winning odds must start with any corner. If the opposing player makes a move in any spot other than the center, the game is won for the first player, given he does not blunder. He simply must make the next following moves that ensure he has two winning moves possible, and it is impossible for the opposing player to stop him.

If he places a move in a square, then the best move for the opposing player will be to try for a tie.

At the end, given two experienced players, both making no mistakes, the game should always end in a tie.

**The Foundation of the Code:**

The program is divided into multiple functions given that a lot of the code we will be writing will have to be repeated multiple times throughout the code. Some parts of the code will be used for two different modules of the game (i.e. printing the game board is a function that will be used for both human vs human mode and the human vs AI mode).

The program has a few values that are global and to be accessed throughout the code. The board is a list of 9, each having a default value of 0 representing emptiness. The print board divides it into three separate lines with the proper formatting.
The main program uses the newest method in recent Python 3.10 version called match, which is commonly referred to switch function in other languages. It is enveloped by a while statement which continues forever unless we input 0, at which point the program ends.
The reason we use a while case is we want the game to run forever until the user explicitly inputs the quit command. The benefit of this is we can keep track of score of two Players, and the score of the AI separately. With wins, losses, and ties recorded separately.
The winning moves in Tic Tac Toe are predefined, with 3 being the horizontal lines, 3 vertical lines and 2 diagonals. All we have to check to see if a player won, is to check every one of them and see if they have the same value (each having 1 represents O being marked in every one of them, and vice versa) and then break the loop, and return a value.

**MiniMax Algorithm:**

The focus of the project was to have an AI that was not beatable, and would play the most optimal move every time. This is very difficult with if conditions, and hard to ensure the AI will account for every possibility with just if conditions. Thus, we use a very popular algorithm for game theory, called MiniMax.

MiniMax is an algorithm that considers the current state of the game, then plays every possible move by both players, and evaluates the score. It is a recursive algorithm, that returns the value of each game state, and then we save the position that will lead to the best outcome.

In this code, we have assigned a value of 1 to every game state where the AI wins, and the value of -1 to every game state where the AI loses. Additionally, to ensure the most optimal value possible, we reward an additional +1 or -1 every time the AI wins or loses with spots empty on the game board.
The algorithm works using a maximizer and a minimizer, to assume the opponent plays the most optimal move also, we use a minimizer when it is the opponent’s turn to play, to select the best move that the opponent can play.

When it is the AI turn’s to play, the maximizer is used to select scores that are the highest, representing the most optimal move that ensures a win for the AI.
In the function SMART_AIMOVE we will be saving the best move that had the best winning odds calculated by the MiniMax algorithm.

There is also a reverse MiniMax function for when the plays first/second, as the AI needs to know beforehand if they are going to be playing O’s or X’s, with the choice being in player’s hand.






