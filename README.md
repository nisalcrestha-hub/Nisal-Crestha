import random
play = "yes"
while play == "yes":
    my_words = ["apple", "tiger", "planet", "school", "python"]
    answer = random.choice(my_words)
    word_show = ["_"] * len(answer)
    life = 3
    used = []
    print("\nHangman")
    print("You have 3 chances")
    while life > 0:
        print("\nWord:", " ".join(word_show))
        print("Life left:", life)
        letter = input("Type a letter: ").lower()
        if letter in used:
            print("Already used")
            continue
        used.append(letter)
        if letter in answer:
            for i in range(len(answer)):
                if answer[i] == letter:
                    word_show[i] = letter
            print("Nice!")
        else:
            life -= 1
            print("Not correct")
        if "_" not in word_show:
            print("You won")
            print("Word:", answer)
            break
    if "_" in word_show:
        print("You lost")
        print("Word was:", answer)
    play = input("\nPlay again? yes/no: ").lower()







    
