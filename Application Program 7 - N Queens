/**Given an N×N chessboard, the task is to place N queens on the board
so that no two queens can attack each other. The objective of this
case study is to implement the N-Queens algorithm in C Language to
find all possible arrangements of the queens on the chessboard.**/

#include <stdio.h>
#include <stdbool.h>

#define N 8 // Change this to your desired board size

bool isSafe(int board[N][N], int row, int col) {
    // Check if a queen can be placed at board[row][col] without conflict

    // Check the left side of the current row
    for (int i = 0; i < col; i++) {
        if (board[row][i])
            return false;
    }

    // Check upper diagonal on the left side
    for (int i = row, j = col; i >= 0 && j >= 0; i--, j--) {
        if (board[i][j])
            return false;
    }

    // Check lower diagonal on the left side
    for (int i = row, j = col; i < N && j >= 0; i++, j--) {
        if (board[i][j])
            return false;
    }

    return true;
}

bool solveNQueens(int board[N][N], int col) {
    // Base case: If all queens are placed, return true
    if (col >= N)
        return true;

    // Try to place a queen in each row of the current column
    for (int i = 0; i < N; i++) {
        if (isSafe(board, i, col)) {
            // Place the queen at board[i][col]
            board[i][col] = 1;

            // Recur to place queens in the next columns
            if (solveNQueens(board, col + 1))
                return true;

            // If placing the queen in board[i][col] doesn't lead to a solution,
            // then backtrack by removing the queen from board[i][col]
            board[i][col] = 0;
        }
    }

    // If no row allows a queen to be placed in the current column, return false
    return false;
}

void printBoard(int board[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", board[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int board[N][N] = {0};

    if (solveNQueens(board, 0)) {
        printf("Solution exists:\n");
        printBoard(board);
    } else {
        printf("Solution does not exist.\n");
    }

    return 0;
}
