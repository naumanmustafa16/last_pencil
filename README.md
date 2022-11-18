# last_pencil
import random
print("How many pencils would you like to use:")
while True:
    pencils = input()
    if pencils.isdigit():
        if int(pencils) > 0:
            break
        else:
            print("The number of pencils should be positive")
    else:
        print("The number of pencils should be numeric")

print("Who will be the first (John,Jack):")

while True:
    name = input()
    if name == 'John':
        print("|" * int(pencils))
        print("John's turn!")
        break
    elif name == 'Jack':
        print("|" * int(pencils))
        print(f"{name}'s turn:")
        break
    else:
        print("Choose between 'John' and 'Jack'")

rem_pencils = int(pencils)
while True:
    if name == 'John':
        pencils_in_turn = input()
        if pencils_in_turn not in ['1', '2', '3']:
            print("Possible values: '1', '2' or '3'")
        elif int(pencils_in_turn) >= 1 and int(pencils_in_turn) <= 3:
                if int(pencils_in_turn) > rem_pencils:
                    print("Too many pencils were taken")
                else:
                    rem_pencils = rem_pencils - int(pencils_in_turn)
                    if rem_pencils == 0:
                        print("Jack won!")
                        break
                    print(rem_pencils * "|")
                    name = "Jack"
                    print(f"{name}'s Turn:")
    if name == 'Jack':
        if rem_pencils % 4 == 1:
            bot_choice = 1
            # print(bot_choice)
            pencils_in_turn = bot_choice
        elif rem_pencils % 4 == 0 and rem_pencils >= 4:
            bot_choice = 3
            # print(bot_choice)
            pencils_in_turn = bot_choice
        # elif rem_pencils % 2 == 0 and rem_pencils % 4 != 0:
        #     bot_choice = 1
        #     # print(bot_choice)
        #     pencils_in_turn = bot_choice
        else:
            bot_choice = (rem_pencils % 4 - 1)
            pencils_in_turn = bot_choice
            if int(pencils_in_turn) > rem_pencils:
                print("Too many pencils were taken")
                continue
        print(bot_choice)
        rem_pencils = rem_pencils - pencils_in_turn
        if rem_pencils == 0:
            print("John won!")
            break
        else:
            print(rem_pencils * "|")
            name = "John"
            print(f"{name}'s Turn!")



