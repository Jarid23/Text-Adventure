
def start ():

    global keys
    keys = 0
    print (" Welcome to the game, type 'start' to begin. ")
    print()
    prompt_sta ()

def prompt_sta ():

    prompt_0 = input("Type a command : ")
    try :
        if prompt_0 == 'Start' :
            outhouse()
        if prompt_0 == 'start' :
            outhouse()
        elif prompt_0 != 'Start:':
            print("Type 'Start' ")
            prompt_sta()
    except ValueError:
        print("Type 'Start' not that other BS.")
        print()
        prompt_sta()

def outhouse ():

    print("You are now outside.")
    prompt_outside()

def prompt_outside ():

    prompt_1 = input("You may do the following : Enter House, Look, Trash Flowers, or Exit : ")
    try:
        if prompt_1 == "Enter House":
            hallway()

        elif prompt_1 == "Look":
            print("There is a big house you can enter, flowers you can trash and an exit that appears locked.")
            print()
            prompt_outside()
        elif prompt_1 == "Exit":
            print("It is locked")
            print()
            prompt_outside()
        elif prompt_1 == 'Trash Flowers':
            print("You trashed the flowers.")
            print()
            prompt_outside()
        else:
            print("Look, Exit, Enter House or Trash Flowers")
            prompt_outside()
    except ValueError:
        print("...")
        print()
        prompt_outside()

def hallway():

    print("You are in a hallway")
    print()
    prompt_hallway ()

def prompt_hallway ():

    prompt_2 = input("In the Hallway you can : E (lounge), N (bedroom) or W (kitchen):")
    try:
        if prompt_2 == 'E':
            lounge()
        elif prompt_2 == 'W':
            kitchen()
        elif prompt_2 == 'N':
            bedroom()
        else:
            print("...")
            print()
            prompt_hallway()
    except ValueError:
        print("...")
        print()
        prompt_hallway()

def bedroom():

    print("You are in a bedroom, you can 'S' to hallway or 'Read Note'")
    print()
    prompt_bedroom()

def prompt_bedroom ():

    prompt_5 = input("What would you like to do ('S' to hallway or 'Read Note' ? : ")
    try:
        if prompt_5 == 'S':
            hallway()
        if prompt_5 == 'Read Note':
            print("The way to win this game is to enter the Kitchen to the West of the Hallway and Pick up Key and then return to the lounge to the East of the Hallway. ")
            prompt_bedroom()
        else:
            print("Enter either 'S or 'Read Note")
            print()
            prompt_bedroom()
    except ValueError :
            print("Enter either 'S or 'Read Note")
            print()
            prompt_bedroom()


def lounge ():

    global keys
    try:
        if keys == 1:
            print("You unlocked door with key! You are victorious! ")
            print()
            prompt_victory ()
        else :
            print("You need a key to unlock the lounge")
            print()
            hallway()
    except ValueError:
        print("You need a key to unlock the lounge")
        print()
        hallway()

def prompt_victory():

    print("YOU WON!!! You made it to the lounge with all the drinks.")

def prompt_lounge():

    prompt_3 = input("Type a command: ")
    try:
        if prompt_3 == 'W':
            hallway()
        elif prompt_3 == 'N' or prompt_3 == 'E' or prompt_3 == 'S':
            print("You can't go that way")
            prompt_lounge()
        else:
            print("...")
            print()
            lounge()
    except ValueError:
        print("You need a key")
        print()
        hallway()

def kitchen ():

    print("You are in a kitchen. You notice a key and a mysterious looking door to the west.")
    print()
    prompt_kitchen ()

def prompt_kitchen():

    global keys
    prompt_4 = input("In the Kitchen you can: 'E' (hallway) , 'W' (mystery) or, 'Pick up Key' : ")
    try:
        if prompt_4 == 'E':
            hallway()
        elif prompt_4 == 'W':
            print("You can't go that way")
            print()
            prompt_kitchen()
        elif prompt_4 == ("Pick up Key"):
            print("You have picked up a key")
            print()
            keys = 1
            print()
            prompt_kitchen()
        else:
            print("...")
            print()
            prompt_kitchen()
    except ValueError:
        print("...")
        print()
        prompt_kitchen()

start()


