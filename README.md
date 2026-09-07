# Лабораторная работа №1
лаба1 змейка через streamlit
import turtle

def perform_switch_case(state, t, turn):
    x = round(t.position()[0] / 10)
    y = round(t.position()[1] / 10)
    if state == "INIT":
        state = "LEFT1"
        t.setheading(180)
        return state, turn
    if state == "LEFT1":
        t.forward(10)
        if x <= -8:
            state = "UP1"
            t.setheading(90)
            return state, turn
        return state, turn
    if state == "UP1":
        t.forward(10)
        if y >= 3:
            state = "RIGHT1"
            t.setheading(0)
            return state, turn
        return state, turn
    if state == "RIGHT1":
        t.forward(10)
        if x >= 0:
            state = "UP2"
            t.setheading(90)
            return state, turn
        return state, turn
    if state == "UP2":
        t.forward(10)
        if y >= 6:
            state = "LEFT2"
            t.setheading(180)
            return state, turn
        return state, turn
    if state == "LEFT2":
        t.forward(10)
        if x <= -8:
            state = "UP3"
            t.setheading(90)
            return state, turn
        return state, turn
    if state == "UP3":
        t.forward(10)
        if y >= 9:
            state = "RIGHT2"
            t.setheading(0)
            return state, turn
        return state, turn
    if state == "RIGHT2":
        t.forward(10)
        if x >= 0:
            state = "UP4"
            t.setheading(90)
            return state, turn
        return state, turn
    if state == "UP4":
        t.forward(10)
        if y >= 12:
            state = "LEFT3"
            t.setheading(180)
            return state, turn
        return state, turn
    if state == "LEFT3":
        t.forward(10)
        if x <= -8:
            state = "STOP"
            return state, turn
        return state, turn
    return state, turn

def draw():
    curr_state = "INIT"
    t = turtle.Turtle()
    t.speed(0)
    t.penup()
    t.goto(10, 10)
    t.pendown()
    turn = 1
    while curr_state != "STOP":
        curr_state, turn = perform_switch_case(curr_state, t, turn)
    turtle.done()

if __name__ == "__main__":
    draw()
