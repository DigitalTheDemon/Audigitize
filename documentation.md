# Basics
> to import mods you have to do is have a python mod file (.py) custom for Audigitize, bring it into the *./mods* folder. Thats all for importing it into the game.
> when the program is updated 1 of 2 things happen:
> - the module you imported will launch with sucess code.
> -  the module will fail to load.

# Building a module
> To build a module compatible with Audigitize you ***must*** create a python file and initialize the mod. 
> Do do this you call the `__INIT_AUDIGITIZE__` function inside the code.
```python
def __INIT_AUDIGITIZE__(self):
    print("function loaded!")
```
> - This function is only called once on load of the ui.


# Working with UI
> The project is built ontop of the PyQt5 library (pip install pyqt5) and uses it to generate UI. It has some basic built in functions for modifications.
> the easiest one to start with is the `EFFECT_UI` function, where once called takes in a few arguments.
> 1. Self argument
> 2. Type ('Slider-text', 'label', 'toggle')
> 3. Range ***ONLY APPLIES FOR SLIDER-TEXT | LEAVE BLANK OTHERWISE***
> 4. Text *all ui elements have a label*
> 5. Connection (*Function OR Variable depending on type*)
>> *This calls a function when the toggle button was toggled, with the inputs of True or False*
>> *When variable is inputted instead it will adjust the variable to the range, or what the user selected*

> *Here is an example usage of this function being called*
```python
def exampleCall(self):
    print('Custom function called!')

self.AUDIO_EFFECT_UI('Slider-text', (0, 100), 'Example slider with input textbox', self.exampleCall): # First argument (self) is placed at the front.
```