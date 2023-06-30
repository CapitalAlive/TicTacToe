# write your code here
def print_table(table):
    print("---------")
    print("|", table[0], table[1], table[2], "|")
    print("|", table[3], table[4], table[5], "|")
    print("|", table[6], table[7], table[8], "|")
    print("---------")


def is_there_a_winner(table):
    possible_win_list = [
        table[0] + table[1] + table[2],
        table[3] + table[4] + table[5],
        table[6] + table[7] + table[8],
        table[0] + table[3] + table[6],
        table[1] + table[4] + table[7],
        table[2] + table[5] + table[8],
        table[0] + table[4] + table[8],
        table[2] + table[4] + table[6],
        ]
    xos_in_table = {"_": 0, "O": 0, "X": 0}

    for item in table:
        xos_in_table[item] += 1
    print_table(table)

    if "XXX" in possible_win_list:
        game_finished = True
        print("X wins")
    elif "OOO" in possible_win_list:
        game_finished = True
        print("O wins")
    elif xos_in_table["_"] > 0:
        pass
        game_finished = False
    else:
        print("Draw")
        game_finished = True
    return game_finished

table_coordinates_dict = {
    "11":0,"12":1,"13":2,
    "21":3,"22":4,"23":5,
    "31":6,"32":7,"33":8
}

table = list("_________".upper())
current_player = "X"

while is_there_a_winner(table) is False:
    valid_move = False
    while valid_move is False:
        next_move = input().split(" ")
        try:
            next_move = [int(item) for item in next_move]
            if (len(next_move) != 2) or (next_move[0] not in range(1, 4)) or (next_move[1] not in range(1, 4)):
                print("Print Coordinates should be from 1 to 3!")
            elif table[table_coordinates_dict[str(next_move[0]) + str(next_move[1])]] in ["X", "O"]:
                print("This cell is occupied! Choose another one!")
            else:
                valid_move = True
        except ValueError:
            print("You should enter numbers!")
    if current_player == "X":
        table[table_coordinates_dict[str(next_move[0]) + str(next_move[1])]] = "X"
        current_player = "0"
    else:
        table[table_coordinates_dict[str(next_move[0]) + str(next_move[1])]] = "O"
        current_player = "X"
