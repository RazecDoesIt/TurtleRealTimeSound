import sounddevice as sd
import turtle
import random
import numpy as np


def print_sound(indata, outdata, frames, time, status):
    volume_norm = np.linalg.norm(indata) * 10
    colors = ['blue', 'orange', 'green', 'purple', 'black', 'yellow', 'pink']
    turtle.screensize(500, 500)
    if int(volume_norm) < 10:
        turtle.pencolor(random.choice(colors))
    if int(volume_norm) > 30:
        angle = random.randint(0, 360)
        turtle.setheading(angle)
    if int(volume_norm) > 50:
        speed = random.randint(0, 50)
        turtle.speed(speed)
    turtle.forward(random.randrange(1, 30))

    if turtle.pos()[0] > 240:
        angle = turtle.heading()
        turtle.setheading(-angle)
        turtle.setposition(240, turtle.pos()[1])
        turtle.forward(30)
    if turtle.pos()[1] > 240:
        angle = turtle.heading()
        turtle.setheading(-angle)
        turtle.setposition(turtle.pos()[0], 240)
    if turtle.pos()[0] < -240:
        angle = turtle.heading()
        turtle.setheading(-angle)
        turtle.setposition(-240, turtle.pos()[1])
    if turtle.pos()[1] < -240:
        angle = turtle.heading()
        turtle.setheading(-angle)
        turtle.setposition(turtle.pos()[0], -240)
    print("|" * int(volume_norm))


with sd.Stream(callback=print_sound):
    sd.sleep(99999999)
