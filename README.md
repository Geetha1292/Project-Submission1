# Project-Submission1
Tic-tac-toe Game using python

oard=['-' for i in range(9)]

def PlayBoard():
    print("|", board[0],"|", board[1],"|",board[2],"|")
    print("|", board[3],"|", board[4],"|",board[5],"|")
    print("|", board[6],"|", board[7],"|",board[8],"|")

Contestant1 = "X"
Contestant2 = "O"
 
def check_conditions(Contestant):
    conditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8], [0, 3, 6],
        [1, 4, 7], [2, 5, 8], [0, 4, 8], [2, 4, 6],

        ]
    for check in conditions:
        if board[check[0]]== Contestant and board[check[1]]==Contestant and board[check[2]]== Contestant:
            return 1
    else:
        return 0
     
 
def StartGame():
    PlayBoard()
    while True:
        while True:
            Contestant1_option=input(f"{player1},enter your position:")
            
            if Contestant1_option not in[str(i) for i in range(1,10)]:
                print ("please enter[1-9]")
                continue
            
            if board[int(Contestant1_option)-1] == "-":
                board[int(Contestant1_option)-1]= Contestant1
                PlayBoard()
                if check_conditions(Contestant1):
                    return f'{Contestant1} Winner.'
                break
            else:
                print("this place is not empty!")
                
        if len([ i for i in board if i == '-']) == 0:
            return '...'
                 
                
        while True:
            Contestant2_option = input(f"{Contestant2},enter your position:")

            if Contestant2_option not in[str(i) for i in range(1,10)]:
                print ("please enter[1-9]")
                continue
            
            if board[int(Contestant2_option)-1] == "-":
                board[int(Contestant2_option)-1]= Contestant2
                PlayBoard()
                if check_conditions(Contestant2):
                    return f'winner : {Contestant2}'
                break
            else:
                print("this place is not empty!")
                
print(StartGame())

while  True:
    play_again=input(" Do you want to play again[y/n]:")
    if play_again in "yY":
        board=['-' for i in range(9)]
        print(StartGame())
    else:
        exit()
    
output:
| - | - | - |
| - | - | - |
| - | - | - |
X,enter your position:1
| X | - | - |
| - | - | - |
| - | - | - |
O,enter your position:5
| X | - | - |
| - | O | - |
| - | - | - |
X,enter your position:2
| X | X | - |
| - | O | - |
| - | - | - |
O,enter your position:3
| X | X | O |
| - | O | - |
| - | - | - |
X,enter your position:4
| X | X | O |
| X | O | - |
| - | - | - |
O,enter your position:7
| X | X | O |
| X | O | - |
| O | - | - |
winner : O
 Do you want to play again[y/n]:n

C:\Users\Geetha\Desktop\game>
Tictactoe.py
