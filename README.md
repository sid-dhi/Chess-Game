# Chess-Game

🎮 Core Features:

**1. Complete Chess Rules Implementation**
✅ All piece movements with proper validation
✅ Check and checkmate detection
✅ Castling (both king-side and queen-side)
✅ En passant captures
✅ Pawn promotion (promotes to queen automatically)
✅ Legal move validation (prevents moves that leave king in check)

**2. Game Interface**
-Visual Chessboard with alternating dark/light squares
-Piece display using Unicode chess symbols
-Move highlighting:
Selected piece highlight
Valid move indicators (green circles)
Capture move indicators (red circles)
-Turn indicator showing whose turn it is
-Coordinates (a-h, 1-8) on board edges

3. Game Management
-Move history with notation (e.g., "e4", "Nf3")
-Undo move functionality
-New game reset button
-Captured pieces display for both sides
-Game status messages (check, checkmate, stalemate)

🛠️ Technical Implementation
Game State Management

javascript
// Key data structures
let gameState = {
    board: [],              // 8x8 array representing the board
    currentPlayer: 'white', // Whose turn it is
    selectedSquare: null,   // Currently selected piece
    validMoves: [],         // Valid moves for selected piece
    gameOver: false,        // Game status
    check: false,           // Is king in check?
    moveHistory: [],        // Record of all moves
    capturedPieces: {       // Captured pieces by color
        white: [],
        black: []
    },
    kingPositions: {        // Track king positions
        white: null,
        black: null
    },
    enPassantTarget: null,  // En passant target square
    castlingRights: {       // Castling availability
        white: { kingSide: true, queenSide: true },
        black: { kingSide: true, queenSide: true }
    }
};

**Move Validation System**
-Piece-specific movement rules for each piece type
-Boundary checking (stays within 8x8 board)
-Collision detection (can't move through pieces)
-Special moves:
Pawn double-move on first move
En passant captur
Castling with rook movement
Pawn promotion on reaching last rank

Check/Checkmate Detection
-Real-time check detection after each move
-Move filtering that prevents moves leaving king in check
-Checkmate detection when no legal moves remain
-Stalemate detection for draw conditions

🔧 Key Algorithms
**1. Move Calculation**
javascript:
function calculateValidMoves(rank, file) {
    // Returns array of {rank, file} positions the piece can move to
    // Includes filtering for moves that would leave king in check
}
**2. Check Detection**
javascript:
function isKingInCheck(board, color, kingRank, kingFile) {
    // Checks if king is threatened by any enemy piece
    // Examines all directions for attacking pieces
}
