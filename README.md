from IPython.display import clear_output

board = [" " for _ in range(0, 10)]
def printboard(board):
            clear_output()
            print(f"{board[1]} | {board[2]} | {board[3]}")
            print("----------")
            print(f"{board[4]} | {board[5]} | {board[6]}")

            print("----------")
            print(f"{board[7]} | {board[8]} | {board[9]}")

def position(num, player):
    if(board[num] == " "):
        board[num] = player
    else:
        print("The place is taken, give another value!")

print("Do you want to be X or O?")
user = input()
if user == 'X':
    print("Player 1 will go first.")
    first = 'X'
    second = 'O'
elif user == "O":
    print("Player 2 will go first.")
    first = 'O'
    second = 'X'
else:
    print("Invalid input.")
    exit()

while True:
    print("Are you ready to play? Yes or No")
    user1 = input()
    if(user1 == "No"):
        print("Game is done!")
        break
    elif(user1 != "Yes"):
        print("Please enter Yes or No!")
        continue
    
    printboard(board)
    
    print("Choose number between 1-9")
    user2 = input()
    if(user2.isdigit()):


        user3 = int(user2)
        if 0 < user3 and user3 < 10:
            position(user3, first)
        else:
            print("Number is out of range!")
    else:
        print("Please enter a valid number!")

    printboard(board)
    
