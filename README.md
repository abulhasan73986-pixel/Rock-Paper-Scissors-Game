# Rock-Paper-Scissors-Game
import random

print("=== Rock ✊ Paper 📄 Scissors ✂ ===")
print("First to score 3 points wins the match!\n")

player_pts = 0
cpu_pts = 0
options = ["rock", "paper", "scissors"]

while player_pts < 3 and cpu_pts < 3:
    my_pick = input("Your turn (rock/paper/scissors): ").lower()
    if my_pick not in options:
        print("Oops! Type only rock, paper or scissors.\n")
        continue

    cpu_pick = random.choice(options)
    print(f"You → {my_pick} | Computer → {cpu_pick}")

    # Logic in one line
    if my_pick == cpu_pick:
        print("It's a tie!\n")
    elif (my_pick, cpu_pick) in [("rock", "scissors"), ("scissors", "paper"), ("paper", "rock")]:
        print("You score a point!\n")
        player_pts += 1
    else:
        print("Computer scores a point!\n")
        cpu_pts += 1

    print(f"Score: You {player_pts} - {cpu_pts} Computer\n")

# Final result
print("=== Match Over ===")
if player_pts > cpu_pts:
    print("🎉 You win the match!")
else:
    print("💻 Computer wins the match!")
