import random
import time
from pynput.mouse import Controller
from pynput import keyboard

mouse = Controller()
screen_width, screen_height = 1920, 1080
running = True

def move_mouse():
    global running
    while running:
        x = random.randint(0, screen_width)
        y = random.randint(0, screen_height)
        mouse.position = (x, y)
        print(f"Mouse moved to: ({x}, {y})")
        time.sleep(1)

def on_press(key):
    global running
    if key == keyboard.Key.esc:
        print("Kill switch activated. Stopping mouse movement.")
        running = False
        return False

listener = keyboard.Listener(on_press=on_press)
listener.start()
move_mouse()
listener.join()
