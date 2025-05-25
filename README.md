# Chess Game in C++

A simple command-line chess game implementation written in C++. This game allows two players to play chess locally with basic move validation and a text-based interface.

## Features

- **Full Chess Board**: Standard 8x8 chessboard with proper piece placement
- **Move Validation**: Validates moves for all chess pieces according to standard rules
- **Two-Player Gameplay**: Alternating turns between white and black players
- **Clear Display**: Clean console interface with coordinate labels
- **Cross-Platform**: Works on both Windows and Unix-like systems

## Supported Pieces and Moves

### Pieces
- **Pawns (P/p)**: Forward movement, diagonal captures, double move from starting position
- **Rooks (R/r)**: Horizontal and vertical movement
- **Knights (N/n)**: L-shaped moves (2+1 or 1+2 squares)
- **Bishops (B/b)**: Diagonal movement
- **Queens (Q/q)**: Combination of rook and bishop moves
- **Kings (K/k)**: One square in any direction

### Notation
- **Uppercase letters**: White pieces (P, R, N, B, Q, K)
- **Lowercase letters**: Black pieces (p, r, n, b, q, k)
- **Dash (-)**: Empty squares

## How to Play

### Compilation
```bash
g++ -o chess chess.cpp
```

### Running the Game
```bash
./chess
```

### Game Controls
- **Move Format**: Enter moves in the format `source destination` (e.g., `e2 e4`)
- **Coordinates**: Use standard chess notation (a1-h8)
  - Columns: a-h (left to right)
  - Rows: 1-8 (bottom to top)
- **Quit Game**: Type `quit` to exit

### Example Moves
```
e2 e4    # Move white pawn from e2 to e4
e7 e5    # Move black pawn from e7 to e5
g1 f3    # Move white knight from g1 to f3
b8 c6    # Move black knight from b8 to c6
```

## Board Layout

The game starts with the standard chess setup:

```
  a b c d e f g h
8 r n b q k b n r 8
7 p p p p p p p p 7
6 - - - - - - - - 6
5 - - - - - - - - 5
4 - - - - - - - - 4
3 - - - - - - - - 3
2 P P P P P P P P 2
1 R N B Q K B N R 1
  a b c d e f g h
```

## Game Rules Implemented

### Basic Movement
- All pieces move according to standard chess rules
- Path obstruction is checked (pieces cannot jump over others, except knights)
- Capture validation (can only capture opponent's pieces)

### Pawn Rules
- Move one square forward
- Move two squares forward from starting position
- Capture diagonally forward
- Cannot move backward

### Special Rules Not Implemented
- **Castling**: King and rook special move
- **En passant**: Special pawn capture
- **Pawn promotion**: Pawn reaching the end of the board
- **Check/Checkmate detection**: Game doesn't end automatically
- **Stalemate detection**: Game continues indefinitely

## Technical Details

### File Structure
- Single source file: `chess.cpp`
- No external dependencies (uses standard C++ libraries only)

### Key Functions
- `initializeBoard()`: Sets up the initial chess position
- `printBoard()`: Displays the current board state
- `parsePosition()`: Converts chess notation to array coordinates
- `isValidMove()`: Validates moves for each piece type
- `makeMove()`: Executes a valid move
- `playGame()`: Main game loop

### System Requirements
- C++ compiler (g++, clang++, or Visual Studio)
- Console/terminal environment
- Works on Windows, macOS, and Linux

## Limitations

This is a basic implementation and does not include:
- Advanced chess rules (castling, en passant, promotion)
- Check/checkmate detection
- Game state saving/loading
- AI opponent
- Move history
- Timer functionality
- Graphical user interface

## Contributing

Feel free to enhance this chess game by adding:
- Check/checkmate detection
- Special moves (castling, en passant, promotion)
- Save/load game functionality
- AI opponent
- Better user interface
- Move validation improvements

## License

This project is open source and available under standard programming practice terms.

---

**Note**: This is an educational chess implementation focused on basic gameplay and move validation. For competitive play, consider using a more feature-complete chess engine.
