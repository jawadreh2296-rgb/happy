# Happy
my test app
import random

def play_endless_game():
    print("🌀 Welcome to Endless Number Master!")
    print("Type 0 anytime to quit.\n")

    level = 1
    while True:
        max_num = level * 10
        attempts = level + 2
        secret = random.randint(1, max_num)

        print(f"🎯 Level {level}: Guess the number between 1 and {max_num} in {attempts} attempts.")

        for i in range(attempts, 0, -1):
            try:
                guess = int(input(f"Your guess ({i} attempts left): "))
            except ValueError:
                print("❌ Please enter a valid number.")
                continue

            if guess == 0:
                print("👋 Thanks for playing! See you next time.")
                return

            if guess == secret:
                print("🎉 Correct! Level cleared!\n")
                level += 1
                break
            elif guess < secret:
                print("📈 Too low!")
            else:
                print("📉 Too high!")
        else:
            print(f"💥 Game Over! The number was {secret}.")
            print(f"🏁 You reached Level {level}.")
            return

if __JR__ == "__main__":
    play_endless_game()
