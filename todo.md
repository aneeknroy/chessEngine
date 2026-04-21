1. Board Representation
The absolute simplest is an 8x8 array (e.g., int board[8][8]). Use integers to represent pieces — positive for white, negative for black, zero for empty. That's it.

2. Move Generation
You need a function that, given a board state, produces a list of all legal moves for the current side. This is the hardest part of the MVP. At minimum it must handle:

Pawn moves (including initial 2-square advance)
Knight, bishop, rook, queen, king moves
Basic check detection (don't allow moves that leave your king in check)

You can skip for MVP: en passant, castling, promotion (just auto-queen).
3. Move Representation
A simple struct with fromSquare and toSquare (e.g., two pairs of x/y coordinates) is enough.

4. Search (the "engine" part)
The bare minimum is Minimax with a fixed depth (depth 2 or 3 is playable). No pruning required for MVP, though alpha-beta is a small addition that makes a huge difference.

5. Evaluation Function
A static evaluator that simply counts material (pawn=1, knight=3, bishop=3, rook=5, queen=9) is sufficient. Positive = good for white, negative = good for black.

6. Game Loop
A simple loop that:

Prints the board to the terminal
Accepts a move from the human (e.g., typed as e2e4)
Calls the engine to pick its move
Checks for checkmate/stalemate

The order to build it
Board → Move Generator → Evaluator → Minimax → Game Loop