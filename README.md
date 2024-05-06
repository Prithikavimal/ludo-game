# ludo-game

import random

# Function to roll the dice
def roll_dice():
    return random.randint(1, 6)

# Function to move a player's piece
def move_piece(player, piece, steps):
    if player in game_board:
        position = (game_board[player] + piece + steps) % 52
        game_board[player] = position
        print(f"{player} moves piece {piece} {steps} steps. New position: {position}")

# Function to print the game board
def print_board():
    for player, position in game_board.items():
        print(f"{player}: {position}")

# Initialize players and game board
players = ["Red", "Green", "Blue", "Yellow"]
game_board = {player: 0 for player in players}

# Main game loop
while True:
    print("\n----- Ludo Game -----")
    for player in players:
        input(f"{player}, press Enter to roll the dice...")
        steps = roll_dice()
        print(f"{player} rolled: {steps}")
        move_piece(player, 1, steps)
    print_board()
