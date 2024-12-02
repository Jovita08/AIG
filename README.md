# AIG
## 1. Write a pygame program to create a window with size 400, 300 and set window title as “Basic Window”
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up the screen
screen = pygame.display.set_mode((400, 300))
pygame.display.set_caption("Basic Window")

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Set window color as white
    screen.fill((255, 255, 255))
    
    pygame.display.flip()

pygame.quit()
```

## 2.	Write a pygame program to create a rectangle, circle and line
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up the screen
screen = pygame.display.set_mode((400, 300))
pygame.display.set_caption("Draw Basic Shapes")

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Set background color to white
    screen.fill((255, 255, 255))

    # Draw shapes
    pygame.draw.rect(screen, (0, 0, 255), (50, 50, 100, 50))  # Blue rectangle
    pygame.draw.circle(screen, (255, 0, 0), (200, 150), 40)   # Red circle
    pygame.draw.line(screen, (0, 255, 0), (300, 50), (300, 250), 5)  # Green line

    # Update the display
    pygame.display.flip()

# Quit Pygame
pygame.quit()
```
## 3.	Write a pygame program to animate a ball that bounces off the edges of the screen, reversing direction when it hits the borders.
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up the screen
screen = pygame.display.set_mode((400, 300))

# Initial position and velocity of the circle
x, y = 200, 150
dx, dy = 3, 3

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Update the position of the circle
    x += dx
    y += dy

    # Bounce the circle on the edges
    if x <= 0 or x >= 400:
        dx = -dx
    if y <= 0 or y >= 300:
        dy = -dy

    # Clear the screen with white color
    screen.fill((255, 255, 255))

    # Draw the circle
    pygame.draw.circle(screen, (255, 0, 0), (x, y), 20)

    # Update the display
    pygame.display.flip()

    # Add a small delay for smooth animation
    pygame.time.delay(10)

# Quit Pygame
pygame.quit()
```

## 4.	Write a pygame to change shape color with keyboard input [ r- red , g- green, b- blue] import pygame
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up display
screen = pygame.display.set_mode((400, 300))
pygame.display.set_caption("Color Changing Rectangle")

# Initial color (blue) for the rectangle
color = (0, 0, 255)

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.KEYDOWN:
            # Change color based on key pressed
            if event.key == pygame.K_r:
                color = (255, 0, 0)  # Red
            elif event.key == pygame.K_g:
                color = (0, 255, 0)  # Green
            elif event.key == pygame.K_b:
                color = (0, 0, 255)  # Blue

    # Fill background with white
    screen.fill((255, 255, 255))

    # Draw the rectangle with the current color
    pygame.draw.rect(screen, color, (150, 100, 100, 100))

    # Update the display
    pygame.display.flip()

# Quit Pygame
pygame.quit()
```
## 5.	Write a pygame program to perform a random color change on Click.
```py
import pygame
import random

# Initialize Pygame
pygame.init()

# Set up the display
screen = pygame.display.set_mode((400, 300))

# Function to generate a random color
def random_color():
    return (random.randint(0, 255), random.randint(0, 255), random.randint(0, 255))

# Initial random color
color = random_color()

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.MOUSEBUTTONDOWN:
            # Change color on mouse click
            color = random_color()

    # Fill the screen with the current color
    screen.fill(color)

    # Update the display
    pygame.display.flip()

# Quit Pygame
pygame.quit()
```

## 6.	Write a pygame to display image with white background
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up the display window
screen = pygame.display.set_mode((400, 300))  # Set window size (width, height)
pygame.display.set_caption("Display Image")  # Set window title

# Load an image (make sure the image is in the same directory or provide the correct path)
image = pygame.image.load('image.png')  



# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:  # If the user closes the window
            running = False

    # Fill the background with white (optional)
    screen.fill((255, 255, 255))

    # Draw the image on the screen at coordinates (0, 0)
    screen.blit(image, (0, 0))

    # Update the display
    pygame.display.flip()

# Quit Pygame
pygame.quit()
```
## 7.	Write a python program to find Euclidean distance between two points (200,300) and (400,400)
```py
import math

# Coordinates of the points
x1, y1 = 200, 300
x2, y2 = 400, 400

# Calculate the Euclidean distance using the formula
distance = math.hypot(x2 - x1, y2 - y1)

# Output the result
print(f"The Euclidean distance between ({x1}, {y1}) and ({x2}, {y2}) is: {distance}")
```
## 8.	In a 2D game, a player’s character is moving with a velocity vector v⃗=(6,8) units per second. Write a python program to determine the magnitude (or length) of the velocity vector to understand the character's speed.
```py
import math

# Given velocity vector (6, 8)
vx, vy = 6, 8

# Calculate the magnitude of the velocity vector using math.hypot
magnitude = math.hypot(vx, vy)

# Output the result
print(f"The magnitude (speed) of the velocity vector is: {magnitude} units per second.")
```
## 9.	Consider an agent is located at the position (100, 100) in a 2D plane.A target is located at the position (200, 150). The agent has a maximum speed of 5 units per time step. write a python program to find the seek force
```py
import math

# Positions of the agent and target
agent_x, agent_y = 100, 100
target_x, target_y = 200, 150

# Agent's maximum speed
max_speed = 5

# Step 1: Calculate the direction vector (from agent to target)
dx = target_x - agent_x
dy = target_y - agent_y

# Step 2: Calculate the magnitude (length) of the direction vector
magnitude = math.hypot(dx, dy)

# Step 3: Normalize the direction vector
norm_dx = dx / magnitude
norm_dy = dy / magnitude

# Step 4: Calculate the seek force (normalize the direction and scale by max speed)
seek_force_x = norm_dx * max_speed
seek_force_y = norm_dy * max_speed

# Output the seek force
print(f"The seek force vector is: ({seek_force_x}, {seek_force_y})")
```
## 10.	Consider an agent is located at the position (100, 100) in a 2D plane. A target is located at the position (200, 150). The agent has a maximum speed of 5 units per time step. write a python program to find the flee force 
```py
import math

# Positions of the agent and target
agent_x, agent_y = 100, 100
target_x, target_y = 200, 150

# Agent's maximum speed
max_speed = 5

# Step 1: Calculate the direction vector (from agent to target)
dx = target_x - agent_x
dy = target_y - agent_y

# Step 2: Calculate the magnitude (length) of the direction vector
magnitude = math.hypot(dx, dy)

# Step 3: Normalize the direction vector
norm_dx = dx / magnitude
norm_dy = dy / magnitude

# Step 4: Calculate the flee force (reverse the direction and scale by max speed)
flee_force_x = -norm_dx * max_speed
flee_force_y = -norm_dy * max_speed

# Output the flee force
print(f"The flee force vector is: ({flee_force_x}, {flee_force_y})")
```
## 11.	Write a python program to find the decision taken by weekend
```py
import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn import tree
from sklearn.preprocessing import LabelEncoder

# Initialize LabelEncoder
Le = LabelEncoder()

# Load the data
df1 = pd.read_excel("d:\\workshop\\play\\Decision_weekend.xlsx")

# Drop the 'weekend' column
df1 = df1.drop(['weekend'], axis=1)

# Encode categorical features
df1['Weather '] = Le.fit_transform(df1['Weather '])
df1['Money'] = Le.fit_transform(df1['Money'])
df1['Parents '] = Le.fit_transform(df1['Parents '])
df1['Decision'] = Le.fit_transform(df1['Decision'])


# Split the dataset into features and target variable
x = df1.drop(['Decision'], axis=1)
y = df1['Decision']

# Create and fit the Decision Tree model
clf = tree.DecisionTreeClassifier(criterion='gini')
clf = clf.fit(x, y)

# Plot the decision tree
tree.plot_tree(clf)
```
![image](https://github.com/user-attachments/assets/271845da-681f-4f77-8f9e-67553aeba759)

# From record
## 1.	To write a python program to simulate the process of passing an item among players and eliminating players based on the given rules until a single winner is determined(Hot Potato game).
```py
import random
import time

def hot_potato(names, num):
    while len(names) > 1:
        for _ in range(num):
            names.append(names.pop(0))  # Pass the potato around
        eliminated = names.pop(0)  # Eliminate the player holding the potato
        print(f"{eliminated} is eliminated!")
    return names[0]  # Return the last remaining player

def main():
    players = ["Alice", "Bob", "Divakar", "David", "Eve"]
    num_passes = 1  # Number of passes before elimination
    print("Hot Potato Game Start!")
    time.sleep(1)
    winner = hot_potato(players, num_passes)
    print(f"\nThe winner is: {winner}")

if __name__ == "__main__":  # Corrected the condition
    main()
```
## 2.	Write a python program to simulate Stack plate game
```py
class PlateStack:
    def __init__(self):
        self.stack = []

    def is_empty(self):
        return len(self.stack) == 0

    def push(self, plate):
        self.stack.append(plate)
        print(f"Plate '{plate}' added to the stack.")

    def pop(self):
        if self.is_empty():
            print("The stack is empty. No plates to remove.")
        else:
            removed_plate = self.stack.pop()
            print(f"Plate '{removed_plate}' removed from the stack.")

    def view_stack(self):
        if self.is_empty():
            print("The stack is empty.")
        else:
            print("Current stack of plates:")
            for plate in reversed(self.stack):
                print(plate)

def plate_stack_game():
    plate_stack = PlateStack()
    print("Welcome to the Plate Stack Game!")
    while True:
        print("\nChoose an option:")
        print("1. Add a plate")
        print("2. Remove a plate")
        print("3. View stack")
        print("4. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            plate = input("Enter the name of the plate to add: ")
            plate_stack.push(plate)
        elif choice == '2':
            plate_stack.pop()
        elif choice == '3':
            plate_stack.view_stack()
        elif choice == '4':
            print("Exiting the game. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":  
    plate_stack_game()
```
## 3.	Write a python program to implement mini-max search algorithm to find the optimal value of MAX Player from graph.
```py
import math

def minimax(curDepth, nodeIndex, maxTurn, scores, targetDepth):
    # Base case: targetDepth reached
    if curDepth == targetDepth:
        return scores[nodeIndex]
    
    if maxTurn:
        # Maximizing player's turn
        return max(
            minimax(curDepth + 1, nodeIndex * 2, False, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, False, scores, targetDepth)
        )
    else:
        # Minimizing player's turn
        return min(
            minimax(curDepth + 1, nodeIndex * 2, True, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, True, scores, targetDepth)
        )

# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = math.log(len(scores), 2)  # Calculate depth of node (log base 2 of the number of scores)
treeDepth = int(treeDepth)  # Convert to an integer, as depth is a whole number

print("The optimal value is : ", end="")
print(minimax(0, 0, True, scores, treeDepth))
```
## 4.	Write a python program to implement negamax algorithm
```py
import math

def negamax(curDepth, nodeIndex, scores, targetDepth):
    # Base case: if we reach the target depth, return the score at that node
    if curDepth == targetDepth:
        return scores[nodeIndex]
    
    # Recursively evaluate both child nodes
    value1 = negamax(curDepth + 1, nodeIndex * 2, scores, targetDepth)
    value2 = negamax(curDepth + 1, nodeIndex * 2 + 1, scores, targetDepth)
    
    # Return the maximum value by flipping the sign for the other player's turn
    return max(-value1, -value2)

# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = 3
print("The optimal value is: ", end="")
print(negamax(0, 0, scores, treeDepth))
```
## 5.	Design a python program to create a decision tree for following data.
  a.	Healthy, In Cover, With Ammo  Attack
  b.	Hurt, In Cover, With Ammo  Attack 
  c.	Healthy, In Cover, Empty  Defend 
  d.	Hurt, In Cover, Empty  Defend 
  e.	Hurt, Exposed, With Ammo  Defend

```py
from sklearn.tree import DecisionTreeClassifier
from sklearn import tree
import pandas as pd
import matplotlib.pyplot as plt

# Data: [Health, Cover, Ammo, Exposed] 
# Health: 1 for Healthy, 0 for Hurt
# Cover: 1 for In Cover, 0 for Exposed
# Ammo: 1 for With Ammo, 0 for Empty 
# Exposed: 1 for Exposed, 0 for In Cover 
# Actions: 0 for Defend, 1 for Attack

# Define the training data and corresponding labels (actions)
data = [
    [1, 1, 1],  # Healthy, In Cover, With Ammo -> Attack
    [0, 1, 1],  # Hurt, In Cover, With Ammo -> Attack
    [1, 1, 0],  # Healthy, In Cover, Empty -> Defend
    [0, 1, 0],  # Hurt, In Cover, Empty -> Defend
    [0, 0, 1],  # Hurt, Exposed, With Ammo -> Defend
]

# Labels: 1 for Attack, 0 for Defend
labels = [1, 1, 0, 0, 0]

# Create a Decision Tree Classifier model
clf = DecisionTreeClassifier(criterion="entropy")

# Train the model
clf.fit(data, labels)

# Test data: example data points
test_data = [
    [1, 1, 1],  # Healthy, In Cover, With Ammo
    [0, 0, 1],  # Hurt, Exposed, With Ammo
    [1, 1, 0],  # Healthy, In Cover, Empty
]

# Predict actions for the test data
predictions = clf.predict(test_data)

# Output the predictions
for i, pred in enumerate(predictions):
    action = "Attack" if pred == 1 else "Defend"
    print(f"Test case {i+1}: Predicted action is {action}")

# Optional: Visualize the decision tree
plt.figure(figsize=(10, 6))
tree.plot_tree(clf, feature_names=['Health', 'Cover', 'Ammo', 'Exposed'], class_names=['Defend', 'Attack'], filled=True)
plt.show()
```
## 6.	Write a pygame to illustrate the seek behavior
```py
import pygame

# Initialize Pygame
pygame.init()

# Set up the display window
screen = pygame.display.set_mode((600, 400))
pygame.display.set_caption("Seek Behavior")

# Define colors and initial positions
WHITE, BLUE, RED = (255, 255, 255), (0, 0, 255), (255, 0, 0)
agent_pos, target_pos = pygame.Vector2(100, 100), pygame.Vector2(400, 300)
max_speed = 3

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.MOUSEBUTTONDOWN:
            target_pos = pygame.Vector2(pygame.mouse.get_pos())

    # Seek behavior
    direction = (target_pos - agent_pos).normalize() * max_speed if agent_pos != target_pos else pygame.Vector2(0, 0)
    agent_pos += direction

    # Fill background with white
    screen.fill(WHITE)
    
    # Draw the agent and target
    pygame.draw.circle(screen, BLUE, agent_pos, 10)
    pygame.draw.circle(screen, RED, target_pos, 5)

    # Update the display
    pygame.display.flip()
    
    # Control the frame rate
    pygame.time.Clock().tick(60)

# Quit Pygame
pygame.quit()
```
