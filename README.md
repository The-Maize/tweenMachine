# TweenMachine 3.0.3
PYTHON 3 VERSION : Maya 2022 ++ 

Thank you to all the users for the thousands of downloads through gumroad. Any issues with up comming maya releases please feel free to let me know so i can fix them as fast as possible. 
The goal for this tool is to keep it alive. The best free tweener is one that is uncomplicated and lightweight. 

A complete new version of this was pulled into zootools by Andrew Silke. Andrew is talented and simplyu a great human being. 
Give his newer more updated version a go if you wish to try his tool. There will be some more additions added to this tool. There has been some upgrades already, how ever they will have to wait for release. Likely to be when maya is updated to 2025. Due to some life circumstances i have not been able to integrate them completely yet. I hope you love this tool as much as i do. Justin has done an amazing job building its original. 

---------------------
### The easiest way to create breakdown poses in Maya

Say you’re creating poses for your character with stepped keys, and have created key poses on frames 1 and 10.
You want to make a breakdown pose on frame 7, but you want it to favor the first pose by 70%. The following comparison
shows how this would be accomplished both with and without tweenMachine.

|Manual Process                                  | Tween Machine                                        |
|------------------------------------------------|------------------------------------------------------|
|Select all controls on the character            | Select all controls on the character                 |
|Change interpolation on all key frames to linear | Left-click on frame 7 in the timeline                |
|Left-click on frame 3 in the timeline           | Adjust a slider in the tweenMachine interface to -70 |
|Middle-click on frame 7 in the timeline         |                                                      |
|Set a key                                       |                                                      |
|Change interpolation on all key frames to stepped|                                                      |

If you’re not happy with the results, you’ve got a lot of steps to repeat if you’re doing it the manual way. With 
tweenMachine, you simply adjust the slider and see the results immediately.  Better still, if you’ve created a custom
set that controls the entire character, you can skip the first step and save even more time.

Will tweenMachine create perfect breakdown poses? Not likely, but it will get you closer to your goal a lot faster than
other methods. You spend less time with busywork and more time making actual progress.

Tween Machine was originally developed by [Justin Barrett](http://www.justinsbarrett.com/) and used extensively throughout
the animation and visual effects industries for years.

Development was taken over by Alex Widener in February 2018.EDIT As of 2022-02-25- Alex's Git hub is no longer available i have done my best to contact in order for a mains pull. Now how ever the software is available here. all correct and up to date contribution attributions are in place. 

Development has been reassigned to [Wade Schneider](https://github.com/The-Maize) in 2022. Wade is a keen developer, and is working towards a great career in the vfx and animation industry. Currently working towards an animation degree, and is an owner partner in a small games development company [GameSage](gamesageproductions.com).

| Contribution                     | Author                                              |
|----------------------------------|-----------------------------------------------------|
|tweenMachine.mel/ tweenMachine.py | [Justin S. Barrett](http://www.justinsbarrett.com/) |
|xml_lib.mel                       | J. Adrian Herbez                                    |
|Maya Shelf Icon                   | [Keith Lango](http://keithlango.squarespace.com/)   |
|Python 3 Convert & Continued Dev                |[Wade Schneider](https://github.com/The-Maize)            |
|Zootools Integration                   | [Andrew Silke](https://create3dcharacters.com)   |


## Installation

### Windows:

Move the tweenMachine.py file to your default Maya scripts directory.

`C:/Users/username/Documents/maya/version_number/scripts`

Save the icon into the “prefs/icons” folder for the same Maya version.

`C:/Users/username/Documents/maya/version_number/prefs/icon`

Once everything is installed, open Maya. In the script editor, type the following in a Python tab:

```
import tweenMachine
tweenMachine.start()
```

Highlight the line, then select `File–>Save Selected to Shelf` to turn it into a shelf button. Use the Shelf Editor to
assign the icon to the shelf button.

### Mac OS:

Move the tweenMachine.py file to your default Maya scripts directory.

`/Users/username/Library/Preferences/Autodesk/maya/version_number/scripts`

Save the icon into the “prefs/icons” folder for the same Maya version.

`/Users/username/Library/Preferences/Autodesk/maya/version_number/prefs/icon`


Once everything is installed, open Maya. In the script editor, type the following in a Python tab:

```
import tweenMachine
tweenMachine.start()
```

Highlight the line, then select `File–>Save Selected to Shelf` to turn it into a shelf button. Use the Shelf Editor to
assign the icon to the shelf button.

### Linux
Do all the same stuff wherever your maya scripts folder is. You can find it by entering the following in a Maya Script Editor:

```
import sys
for s in sys.path:
    print(s)
```

And then find the `maya/version_number/scripts/` folder and follow the same steps as above. 

## Usage

When running tweenMachine for the first time, it will open with a bare-bones interface. There’s a single slider labeled
“Selected”, and a group of seven buttons below the slider. In this mode, tweenMachine operates only on selected objects.
Click between two keys on the timeline, and adjust the “Selected” slider to create a new breakdown key. The values set
for the new breakdown key will be biased toward the surrounding keys on the timeline based on how you set the slider.
In the slider’s default position, the new keys will be exactly halfway between the surrounding keys. Slider values to
the left will favor the new key toward the previous key, while values to the right will favor the next key. Clicking one
of the buttons will set the slider to a preset value. If you wish, you can highlight individual channels in Maya’s
channel box, and tweenMachine will only perform its work on those channels, leaving others untouched.

That covers the core operation of tweenMachine, but there are additional features available through various menu items. A full breakdown of all menu items is covered in the next section

### Menu

The functions for all (currently available) tweenMachine menu items are as follows…

`Options > Show`

Contains Menu Bar and Label visibility toggles, plus radio buttons that let you select if you want to see the slider,
the buttons, or both.

`Options > Mode… > Window`

Sets the interface to be a standard floating window.

`Options > Mode… > Toolbar`

Sets the interface to toolbar mode, allowing you to place it next to other Maya toolbars in the main window.

`Options > Overshoot`

Toggles “overshoot mode” for all sliders. By default, the range of all sliders is -100 to 100. When “overshoot mode” is
active, the range of all sliders changes to -150 to 150. Using this mode allows you to create overshoot poses on the
right end of the sliders in the 101-150 range, while using it in the -101 to -150 range on the left end effectively
creates anticipation poses.

`Options > Special Tick Color`

Toggles the tick color used for keys added using the tweenMachine. When off (default), the standard tick color is used.
When on, the “special” tick color is used.

### Buttons

The buttons below each set slider provide a quick way to set the slider to predictable values. By default they are set
to mimic the style of pose favoring familiar to 2D animators. The center button is an exact halfway point between the
two poses, and spreading out from the center on either side, the remaining buttons represent pose favoring by 1/3, 1/5,
and 1/8 in their respective directions.By holding the mouse over any button, an annotation popup will appear showing the
numerical value assigned to that button.

While the button values and colors are locked in this version (unless you manually tweak them), the Python version will
eventually allow them to be easily customized.
