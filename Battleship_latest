import os
from random import randint

class bcolors:
    HEADER = '\033[95m'
    OKBLUE = '\033[94m'
    OKGREEN = '\033[92m'
    WARNING = '\033[93m'
    FAIL = '\033[91m'
    ENDC = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'

board = []

for x in range(10):
    board.append(["O"] * 10)

def print_board(board):
    for row in board:
        xxx = " ".join(row)
        print (xxx)

print ("Let's play Battleship!")
print_board(board)

def random_row(board):
    return randint(0, len(board) - 1)

def random_col(board):
    return randint(0, len(board[0]) - 1)

points = 0
ship_row = random_row(board)
ship_col = random_col(board)

ship_row2 = random_row(board)
ship_col2 = random_row(board)

ship_row3 = random_row(board)
ship_col3 = random_row(board)
os.system('clear')
print str(ship_row)  + ', ' + str(ship_col)
print str(ship_row2) + ', ' + str(ship_col2)
print str(ship_row3) + ', ' + str(ship_col3)

# Everything from here on should go in your for loop!
# Be sure to indent four spaces!
for turn in range(6):
    print ('Turn', turn + 1)
    print points
    guess_row = int(raw_input("Guess Row:"))
    guess_col = int(raw_input("Guess Col:"))

    if guess_row == ship_row and guess_col == ship_col \
        or guess_row == ship_row2 and guess_col == ship_col2 \
        or guess_row == ship_row3 and guess_col == ship_col3:
        os.system('clear')
        points += 1

        if points == 3:
            print_board(board)
            print ('You\'ve won, Congratulations ;)')
            break
        elif points in range(1,3):
            board[guess_row][guess_col] = bcolors.OKGREEN + "*" + bcolors.ENDC
            print_board(board)
            print ("Congratulations! You sunk my battleship!")
    else:
        if (guess_row < 0 or guess_row > 9) or (guess_col < 0 or guess_col > 9):
            print ("Oops, that's not even in the ocean.")
        elif(board[guess_row][guess_col] == bcolors.FAIL + "X" + bcolors.ENDC):
            print_board(board)
            print ("You guessed that one already.")
        else:
            os.system('clear')
            print ("You missed my battleship!")
            board[guess_row][guess_col] = bcolors.FAIL + "X" + bcolors.ENDC
            print_board(board)
    if turn == 5:
        os.system('clear')
        print ('Game Over')
        print_board(board)
        print 'Correct answers were: \nship 1: ' + str(ship_row) + ', ' + str(ship_col)
        print 'ship 2: ' + str(ship_row2) + ', ' + str(ship_col2)
        print 'ship 3: ' + str(ship_row3) + ', ' + str(ship_col3)
