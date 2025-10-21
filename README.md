# Tic-Tac-Toe

This project is a simple 3×3 Tic-Tac-Toe game implemented using the provided game engine framework for CMPM 123.  
The code allows two players to take turns placing X’s and O’s until one wins or the board fills up in a draw.

## Overview

The base project included all core engine files (`Bit`, `BitHolder`, `Game`, `Player`, etc.) and a skeleton `TicTacToe.cpp` with TODOs.  
My task was to complete the logic inside that file to make the game playable.

The game:
- Draws a 3×3 grid of clickable squares.  
- Alternates turns between Player 1 (X) and Player 2 (O).  
- Checks all winning combinations each turn.  
- Detects draws when the board is full.  
- Locks the board once the game ends (no more moves allowed).  

---

## Code I Implemented

I filled in or modified these methods inside `TicTacToe.cpp`:

- `setUpBoard()` – creates the 3×3 grid, loads `"square.png"`, and starts the game.  
- `actionForEmptyHolder()`– handles clicks on empty squares, places the current player’s piece, and prevents moves after a win or draw.  
- `stopGame()` – clears the board by destroying all pieces.  
- `ownerAt()` – returns the owner of a square for winner checking.  
- `checkForWinner()` – checks the 8 possible winning line combinations.  
- `checkForDraw()` – detects a draw when all squares are filled.  
- `stateString()` / `setStateString()` – save and load the current board state using a 9-character string (`"0"` = empty, `"1"` = X, `"2"` = O).

I also added a small condition in `actionForEmptyHolder()`:
if (checkForWinner() != nullptr || checkForDraw())
    return false;
so that when the game ends you cannot continue placing pieces.