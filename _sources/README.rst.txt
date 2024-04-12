Basics
======

The Tkinter module is the standard Python interface to Tk GUI toolkit
from Scripts,both of Tk and Tkinter are available on most Unix
platforms,as well as Windows and Macintosh systems. Starting with the
8.0 release,Tk offers native look and feel on all platforms.

Tk interface module is located in a binary module named \_tkinter
present in earlier versions. Two most important python GUI modules are:-
1. Tkinter module 2. Tkconstants to get started you need to import the
modules using by typing “import Tkinter” or by typing ” from Tkinter
import \* ” to initialize Tkinter we have to create the root widget,only
one root widget should be created for each program, and it must be
created before any other widget.

.. code:: python

   python root =Tk()
   w = Label(root,text='Hello world!)
   w.pack()

A Label widget can display either text or an icon or other image. In
this case, we use the text option to specify which text to display.
Next, we call the pack method on this widget, which tells it to size
itself to fit the given text, and make itself visible. But before this
happens, we have to enter the Tkinter event loop:

.. code:: python

   python root.mainloop()

The program will stay in the event loop until we close the window. The
event loop doesn’t only handle events from the user (such as mouse
clicks and key presses) or the windowing system (such as redraw events
and window configuration messages), it also handle operations queued by
Tkinter itself. Among these operations are geometry management (queued
by the pack method) and display updates. This also means that the
application window will not appear before you enter the main loop.

Basic tkinter program:
^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

   from tkinter import Tk, Frame, Button

   class App:
       def __init__(self, master):
           frame = Frame(master)
           frame.pack()
           self.button = Button(frame, text='QUIT', fg="green", command=frame.quit)
           self.button.pack(side='left')
           self.hi_there = Button(frame, text="Hello", command=self.say_hi)
           self.hi_there.pack(side=LEFT)

       def say_hi(self):
           print("hi there!")

   root = Tk()
   app = App(root)
   root.mainloop()

**Class Creation:** We start by defining a class called App.The
constructor (**init** method) takes a parent widget (the master) as an
argument. Inside the constructor, we create a Frame widget to serve as a
container for other widgets.\ ** Adding Buttons:** Within the frame, we
create two Button widgets. The first button is labeled “QUIT” and
appears in red.The second button is labeled “Hello”. **Functionality:**
The “QUIT” button is associated with the frame.quit function, which
quits the application. The “Hello” button triggers a custom method
called say_hi.

+-----------------------------------------------------------------------+
| When working with Tkinter, you can name widgets using the following   |
| approach: **Automatic Naming:**\                                      |
+-----------------------------------------------------------------------+
| In Tkinter, each widget is an object (an instance of a class)         |
| representing buttons, frames, and other GUI elements. When you create |
| a widget, you need to pass its parent as a parameter to the widget    |
| creation function. Tkinter automatically assigns a unique name to     |
| each new widget. For example, if you create a button within a frame,  |
| Tkinter assigns names like “.:1428748” for the frame and              |
| “.:1428748.1432920” for the button.                                   |
+-----------------------------------------------------------------------+
| **Accessing Widget Names:**\  To access a widget’s name within an     |
| event or function, use event.widget[“text”]. For example, if you want |
| to get the name of a widget during an event, use event.widget[“text”] |
| inside a function. You can then print the widget’s name using         |
| print(event.widget[“text”]).                                          |
+-----------------------------------------------------------------------+
| Remember, widget names in Tkinter are automatically managed, making   |
| it easier to work with GUI elements                                   |
+-----------------------------------------------------------------------+

Geometry Mixins
~~~~~~~~~~~~~~~

The Grid, Pack, and Place classes are used as mixins by the widget
classes. They provide access to various geometry managers via
delegation.

.. _geometry-mixins-1:

Geometry Mixins
^^^^^^^^^^^^^^^

+---------------------------+-------------------------------------------+
| Manager                   | Description                               |
+===========================+===========================================+
| Grid                      | The grid geometry manager allows you to   |
|                           | create table-like layouts by organizing   |
|                           | widgets in a 2-dimensional grid. To use   |
|                           | this manager, employ the ``grid`` method. |
+---------------------------+-------------------------------------------+
| Pack                      | The pack geometry manager lets you create |
|                           | layouts by “packing” widgets into a       |
|                           | parent widget, treating them as           |
|                           | rectangular blocks placed in a frame. To  |
|                           | use this manager, call the ``pack``       |
|                           | method on the widget.                     |
+---------------------------+-------------------------------------------+
| Place                     | The place geometry manager enables        |
|                           | explicit placement of widgets at specific |
|                           | positions. Use the ``place`` method to    |
|                           | achieve this fine-grained control.        |
+---------------------------+-------------------------------------------+

Additional Details
^^^^^^^^^^^^^^^^^^

Here’s how these managers can be practically applied:

-  **Grid**: Ideal for creating complex user interfaces with multiple
   widgets arranged in rows and columns.
-  **Pack**: Best suited for simpler layouts where widgets need to be
   placed either vertically or horizontally.
-  **Place**: Offers precise control over widget positioning; however,
   manual management is required for responsiveness.

Widget classes in Tkinter
~~~~~~~~~~~~~~~~~~~~~~~~~

+-----------------------------------+-----------------------------------+
| Widget                            | Description                       |
+===================================+===================================+
| Button                            | A simple button, used to execute  |
|                                   | a command or other operation.     |
+-----------------------------------+-----------------------------------+
| Canvas                            | Structured graphics. This widget  |
|                                   | can be used to draw graphs and    |
|                                   | plots, create graphics editors,   |
|                                   | and to implement custom widgets.  |
+-----------------------------------+-----------------------------------+
| Checkbutton                       | Represents a variable that can    |
|                                   | have two distinct values.         |
|                                   | Clicking the button toggles       |
|                                   | between the values.               |
+-----------------------------------+-----------------------------------+
| Entry                             | A text entry field.               |
+-----------------------------------+-----------------------------------+
| Frame                             | A container widget. The frame can |
|                                   | have a border and a background,   |
|                                   | and is used to group other        |
|                                   | widgets when creating an          |
|                                   | application or dialog layout.     |
+-----------------------------------+-----------------------------------+
| Label                             | Displays a text or an image.      |
+-----------------------------------+-----------------------------------+
| Listbox                           | Displays a list of alternatives.  |
|                                   | The listbox can be configured to  |
|                                   | get radiobutton or checklist      |
|                                   | behavior.                         |
+-----------------------------------+-----------------------------------+
| Menu                              | A menu pane. Used to implement    |
|                                   | pulldown and popup menus.         |
+-----------------------------------+-----------------------------------+
| Menubutton                        | A menubutton. Used to implement   |
|                                   | pulldown menus.                   |
+-----------------------------------+-----------------------------------+
| Message                           | Display a text. Similar to the    |
|                                   | label widget, but can             |
|                                   | automatically wrap text to a      |
|                                   | given width or aspect ratio.      |
+-----------------------------------+-----------------------------------+
| Radiobutton                       | Represents one value of a         |
|                                   | variable that can have one of     |
|                                   | many values. Clicking the button  |
|                                   | sets the variable to that value,  |
|                                   | and clears all other radiobuttons |
|                                   | associated with the same          |
|                                   | variable.                         |
+-----------------------------------+-----------------------------------+
| Scale                             | Allows you to set a numerical     |
|                                   | value by dragging a “slider”.     |
+-----------------------------------+-----------------------------------+
| Scrollbar                         | Standard scrollbars for use with  |
|                                   | canvas, entry, listbox, and text  |
|                                   | widgets.                          |
+-----------------------------------+-----------------------------------+
| Text                              | Formatted text display. Allows    |
|                                   | you to display and edit text with |
|                                   | various styles and attributes.    |
|                                   | Also supports embedded images and |
|                                   | windows.                          |
+-----------------------------------+-----------------------------------+

`You can make some projects
now <https://www.javatpoint.com/eight-amazing-ideas-of-python-tkinter-projects>`__

.. figure::
   https://github.com/shreshth45967/shreshth45967-An-introduction-to-tkinter/assets/96594936/5955164e-4450-473b-9e60-5af1e4d1c0fe
   :alt: 1_wEAtpMCNxjcW_9VZyGafdg

   1_wEAtpMCNxjcW_9VZyGafdg
