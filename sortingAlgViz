"""
---------------------------------------------------------------------------------------------------------------------
Sorting algorithm visualizer
---------------------------------------------------------------------------------------------------------------------
"""

import turtle
import time
import random


"""
---------------------------------------------------------------------------------------------------------------------
array
---------------------------------------------------------------------------------------------------------------------
"""

class array_data:
    unsortedArray = []
    currentSorts = []

    def create_array(self, size):
        for i in range(size):
            array_data.unsortedArray.append(random.randint(1, 100))
            array_data.currentSorts.append('black')

    def reset_colors(self, array):
        for i in range(len(array)):
            array[i] = 'black'


"""
---------------------------------------------------------------------------------------------------------------------
visualization
---------------------------------------------------------------------------------------------------------------------
"""

class visualization:
    pen = turtle.Turtle()

    def update_screen(self, timePerFrame, array):
        window.tracer(0, 60)
        visualization.draw_array('draw', array)
        window.update()
        time.sleep(timePerFrame)
        visualization.pen.clear()

    def draw_array(self, heights):
        botLeft = 1
        for i in range(len(array_data.currentSorts)):
            visualization.draw_block('block', [botLeft, 0], [botLeft + 2, heights[i]], array_data.currentSorts[i])
            botLeft += 2

    def draw_block(self, botLeft, topRight, color):
        visualization.pen.hideturtle()
        visualization.pen.speed(0)
        visualization.pen.color(color)

        visualization.pen.begin_fill()
        visualization.pen.goto(botLeft)
        visualization.pen.goto(topRight[0], botLeft[1])
        visualization.pen.goto(topRight)
        visualization.pen.goto(botLeft[0], topRight[1])
        visualization.pen.goto(botLeft)
        visualization.pen.end_fill()


"""
---------------------------------------------------------------------------------------------------------------------
bubble sort
---------------------------------------------------------------------------------------------------------------------
"""

class bubble_sort:
    def runSort(self, integerArray, colorArray, isSorted):
        sortsLeft = len(integerArray) - 1

        while not isSorted:
            isSorted = True
            for i in range(sortsLeft):
                toSwitch = False
                colorArray[i] = 'green'

                if integerArray[i] > integerArray[i + 1]:
                    toSwitch = True
                    colorArray[i + 1] = 'red'
                    isSorted = False

                visualization.update_screen('screen update', 0.05, array_data.unsortedArray)

                array_data.reset_colors('reset', colorArray)

                if toSwitch:
                    integerArray[i], integerArray[i + 1] = integerArray[i + 1], integerArray[i]

            sortsLeft -= 1

            if isSorted == True:
                return False

"""
---------------------------------------------------------------------------------------------------------------------
execution
---------------------------------------------------------------------------------------------------------------------
"""

# setup
window = turtle.Screen()
window.setworldcoordinates(0, 0, 100, 100)
window.tracer(0)
array_data.create_array('array', 50)
time.sleep(3)

# run sort
bubble_sort.runSort('bubble', array_data.unsortedArray, array_data.currentSorts, False)
time.sleep(2)
