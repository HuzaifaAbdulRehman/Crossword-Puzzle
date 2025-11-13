# Crossword Puzzle Game - x86 Assembly

A console-based crossword puzzle game developed in x86 Assembly Language using the Irvine32 library. This project demonstrates low-level programming concepts including string manipulation, file I/O operations, and menu-driven interface design.

## Description

This crossword puzzle game challenges players to find hidden words in a grid across three difficulty levels. Players have limited lives and must guess words correctly to advance through the levels. The game features a complete menu system with settings, instructions, and high score tracking.

## Features

- **Three Progressive Levels**: Increasing difficulty with different word sets
  - Level 1: Basic words (FAST, APPLE, SPOT, TOUCH, SHOUT)
  - Level 2: Intermediate words (VALUE, EMPLOYEE, SUCCESS, LAW, VIRUS)
  - Level 3: Advanced words (FINANCE, MONEY, REWARD, WALLET, WARE)
- **Lives System**: Start with 3 lives, lose one for each incorrect guess
- **Score Tracking**: Earn points for finding words correctly
- **High Score System**: Saves and displays best scores
- **Color Customization**: 8 different color themes (Blue, White, Green, Red, Magenta, Yellow, Cyan, Brown)
- **File I/O**: Reads puzzle grids and saves high scores to text files
- **Interactive Menu**: Easy-to-navigate interface with multiple options

## Installation Steps

### Prerequisites

1. **MASM (Microsoft Macro Assembler)** - Required to assemble the code
2. **Irvine32 Library** - Must be installed and configured
   - Download from [Kip Irvine's website](http://asmirvine.com/)
   - Extract and configure include paths
3. **Visual Studio** (recommended) or **MASM615** for compilation
4. **Windows OS** - Required for Irvine32 library compatibility

### Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/HuzaifaAbdulRehman/Crossword-Puzzle.git
   cd Crossword-Puzzle
   ```

2. Ensure Irvine32 library files are in your MASM include directory:
   - `Irvine32.inc`
   - `Irvine32.lib`
   - `macros.inc`

3. Verify the following files are in the project directory:
   - `Coal_Project_Code.txt` (main assembly code)
   - `level1.txt`, `level2.txt`, `level3.txt` (puzzle grids)
   - `instruction.txt` (game instructions)

4. Rename the main code file for assembly:
   ```bash
   copy Coal_Project_Code.txt main.asm
   ```

5. Assemble and link the program:
   ```bash
   ml /c /Zi /coff main.asm
   link /SUBSYSTEM:CONSOLE main.obj Irvine32.lib kernel32.lib
   ```

6. Run the executable:
   ```bash
   main.exe
   ```

## Usage Instructions

### Main Menu Options

1. **Quick Play**: Start the game from Level 1 and progress through all three levels
2. **Instructions**: Display game rules and how to play
3. **Settings**: Customize game appearance (change console colors)
4. **High Score**: View the highest score achieved
5. **Quit**: Exit the game

### Gameplay

1. Run the program and select "Quick Play" from the main menu
2. The puzzle grid will be displayed showing the letter layout
3. Enter words you can find in the grid when prompted
4. Words can be horizontal, vertical, or diagonal
5. Correct words increase your score
6. Incorrect guesses decrease your lives
7. Complete all words in a level to advance
8. Game ends when lives reach 0 or all levels are completed

### Example Puzzle Grid

```
F A S T X S
Z S P O T H
C X Y U P O
A X X C A U
M Y C H L T
A P P L E F
```

Find words: FAST, APPLE, SPOT, TOUCH, SHOUT

## Technologies Used

- **Language**: x86 Assembly (MASM syntax)
- **Library**: Irvine32.inc - Provides simplified I/O procedures
- **Macro Support**: macros.inc for code simplification
- **File Operations**: Windows API calls for file reading/writing
- **String Operations**:
  - `cmpsb` (Compare String Bytes)
  - `repe` (Repeat While Equal)
  - String manipulation using ESI/EDI registers

### Key Assembly Concepts Demonstrated

- Procedures and function calls
- Conditional jumps and branching
- String comparison algorithms
- File I/O operations
- Memory addressing modes
- Register manipulation (EAX, EBX, ECX, EDX, ESI, EDI)
- Stack operations
- Macro usage

## Folder Structure

```
COAL_Project/
│
├── Coal_Project_Code.txt          # Main assembly source code
├── Creative_Menu_Assembly_Code.txt # Alternative menu implementation
├── Formatted_Menu_Assembly_Cod_II.txt # Formatted menu code
│
├── level1.txt                     # Level 1 puzzle grid
├── level2.txt                     # Level 2 puzzle grid
├── level3.txt                     # Level 3 puzzle grid
├── instruction.txt                # Game instructions (if exists)
├── high_score.txt                 # Saved high score (generated at runtime)
│
├── Coal_Project_Summary.pdf       # Project documentation
├── Code_Explanation_Coal_Project.pdf # Detailed code explanation
├── Formatted_Assembly_Code_Project.pdf # Formatted code reference
│
├── Explanation_img/               # Screenshots and diagrams
│   ├── img1.jpg
│   └── desktop.ini
│
└── README.md                      # This file
```

## Notes

### Important Considerations

- The game is case-sensitive for word matching
- All words must be entered in **UPPERCASE** letters
- Level progression requires finding all words in the current level
- High score is saved to `high_score.txt` in the same directory
- Color settings persist only for the current session

### Known Limitations

- Windows-only compatibility (due to Irvine32 library)
- Requires specific MASM environment setup
- Fixed word lists (not dynamically loaded)
- No diagonal word search in current implementation
- Limited to 3 difficulty levels

### Troubleshooting

- **Error: "Cannot open file"** - Ensure level text files are in the same directory as the executable
- **Linker errors** - Verify Irvine32.lib is properly linked
- **Assembly errors** - Check that Irvine32.inc and macros.inc are in your include path
- **Colors not changing** - Try running as administrator

## Credits

**Developer**: Huzaifa Abdul Rehman
**Course**: Computer Organization and Assembly Language (COAL)
**Institution**: FAST-NUCES
**Year**: 2024

### Libraries & Resources

- **Irvine32 Library** by Kip R. Irvine - Simplified assembly programming procedures
- **MASM (Microsoft Macro Assembler)** - Assembly and linking tools

### Acknowledgments

Special thanks to:
- Kip Irvine for the excellent Irvine32 library and learning resources
- COAL instructors for project guidance
- The assembly programming community for documentation and support

## License

This project is created for educational purposes as part of a Computer Organization and Assembly Language course.

---

**For questions, issues, or contributions**, please contact the repository owner or open an issue on GitHub.
