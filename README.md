# 2024_03_02_PythonAntiAfk
Just a python script to avoid afk on your computer that have an "sleep mode"


Note that in addition, it is better to open a youtube page in full screen mode or a game (or else).

``` py

import pyautogui
import random
import time

# Function to simulate pressing the space key
def press_space():
    pyautogui.keyDown('a')
    time.sleep(0.1)  # Adjust this duration as needed
    pyautogui.keyUp('a') 
    pyautogui.keyDown('space')
    time.sleep(0.1)  # Adjust this duration as needed
    pyautogui.keyUp('space') 
# Function to move the mouse randomly on the screen
def move_mouse_randomly():
    screen_width, screen_height = pyautogui.size()
    new_x = random.randint(0, screen_width)
    new_y = random.randint(0, screen_height)
    pyautogui.moveTo(new_x, new_y, duration=0.5)

# Function to click at the center of the screen
def click_center():
    screen_width, screen_height = pyautogui.size()
    center_x = screen_width // 2
    center_y = screen_height // 2
    pyautogui.click(center_x, center_y)

# Main function to execute the actions
def main():
    try:
        while True:
            press_space()
            move_mouse_randomly()
            time.sleep(5)  # Wait for a second
            move_mouse_randomly()
            time.sleep(5)  # Wait for a second
            move_mouse_randomly()
            time.sleep(5)  # Wait for a second
            click_center()
            time.sleep(10)  # Wait for 60 seconds before repeating
            print (".")
    except KeyboardInterrupt:
        print("\nProgram stopped by user.")

if __name__ == "__main__":
    main()
```
