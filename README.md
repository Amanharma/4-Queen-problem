# 4-Queen-problem
[1/10, 9:13 AM] Meta AI: 4-Queen Problem SudoCode

The 4-Queen problem is a classic backtracking problem that involves placing 4 queens on a 4x4 chessboard such that no queen attacks another.

SudoCode
```
Procedure Solve Queens():
  Initialize board as a 4x4 matrix
  Call Place Queens(0, board)

Procedure Place Queens(row, board):
  If row == 4 Then
    // Solution found, print the board
    Print Board(board)
  Else
    For col = 0 to 3 Do
      If Is Safe(row, col, board) Then
        // Place queen at (row, col)
        board[row][col] = 1
        // Recur for the next row
        Place Queens(row + 1, board)
        // Backtrack, remove queen from (row, col)
        board[row][col] = 0
      End If
    End For
  End If

Function Is Safe(row, col, board):
  // Check if the queen at (row, col) is safe
  For i = 0 to row - 1 Do
    If board[i][col] == 1 Then
      Return False // Queen attacks another queen in the same column
    End If
    If col - (row - i) >= 0 And board[i][col - (row - i)] == 1 Then
      Return
```
[1/10, 9:13 AM] Meta AI: 4-Queen Problem SudoCode

The 4-Queen problem is a classic backtracking problem that involves placing 4 queens on a 4x4 chessboard such that no queen attacks another.

SudoCode
```
Procedure Solve Queens():
  Initialize board as a 4x4 matrix
  Call Place Queens(0, board)

Procedure Place Queens(row, board):
  If row == 4 Then
    // Solution found, print the board
    Print Board(board)
  Else
    For col = 0 to 3 Do
      If Is Safe(row, col, board) Then
        // Place queen at (row, col)
        board[row][col] = 1
        // Recur for the next row
        Place Queens(row + 1, board)
        // Backtrack, remove queen from (row, col)
        board[row][col] = 0
      End If
    End For
  End If

Function Is Safe(row, col, board):
  // Check if the queen at (row, col) is safe
  For i = 0 to row - 1 Do
    If board[i][col] == 1 Then
      Return False // Queen attacks another queen in the same column
    End If
    If col - (row - i) >= 0 And board[i][col - (row - i)] == 1 Then
      Return False // Queen attacks another queen in the upper-left diagonal
    End If
    If col + (row - i) < 4 And board[i][col + (row - i)] == 1 Then
      Return False // Queen attacks another queen in the upper-right diagonal
    End If
  End For
  Return True // Queen is safe
```

Explanation
1. The `Solve Queens` procedure initializes the board and calls the `Place Queens` procedure to start the backtracking process.
2. The `Place Queens` procedure attempts to place a queen in each column of the current row. If a safe position is found, it recursively calls itself to place queens in the next row.
3. The `Is Safe` function checks if a queen can be placed at a given position without being attacked by another queen.

Note: This sudoCode uses a 0-based indexing system for the board.
