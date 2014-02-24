# WP Laboratory Work #1

## Title

Window. Window handling. Basic window’s form elements

## Contents
  - Win32 API
  - GIT
  - Programming Style Guidelines
  - Window
  - Button
  - Text Input
  - Text

## Objectives:
  - Understanding and using CLI (basic level)
  - Administration of a remote linux machine using SSH
  - Ability to work remotely (remote code editing)
  - Ability to work with VCS

## Executed Tasks:
  - **Mandatory Tasks:**
    - Create a Windows application
    - Choose a _Programming Style Guideline_ that you'll follow
    - Add 2 buttons to window: one with default styles, one with custom styles (size, background, text color, font family, font size)
    - Add 2 text inputs to window: one with default styles, one with custom styles (size, background, text color, font family, font size)
    - Add 2 text elements to window: one with default styles, one with custom styles (size, background, text color, font family, font size)
  - **Tasks With Points:**
    - Make elements to fit window on resize **(1 pt)**
    _(hint: you can limit minimal window width and height)_
    - Make elements to interact or change other elements (1 pt for 2 different interactions) **(0-2 pt)** _(ex. on button click, change text element color or position)_
    - Change behavior of different window actions (at least 3). For ex.: on clicking close button, move window to a random location on display's working space **(1 pt)**
    - Write your own PSG (you can take existent one and modify it) and argue why it is better (for you) **(1 pt)**
  - **Additional Tasks:**
    - Additional taks done for fun

## Theoretical Work:

First of all I had to choose on a programming language and PSG. As a programming language I'll use C++ as it is more powerful and easy. As a PSG I'll use [Geotechnical Software Services C++ Programming Style Guidelines](http://geosoft.no/development/cppstyle.html).

There are few concepts that are new to me, and some that broke my code execution flow perceptions. It was a bit strange at first to work with code that is not linearly executed but can emit message at any time (almost). Also there are some parts of the application that are called much more often than others. Some of them are called only once during the whole application lifetime. This made me think more about what code should be inside of callback function and what code should be moved outside.

With the help of Petzold book and MSDN thing become clear and simple.

## Practical Work:

### Create a Windows application

I just took provided bootstrap and everything worked.

### Choose a _Programming Style Guideline_ that you'll follow

[Geotechnical Software Services C++ Programming Style Guidelines](http://geosoft.no/development/cppstyle.html)

### Add 2 buttons to window: one with default styles, one with custom styles (size, background, text color, font family, font size)

As I wanted to add a default font to a button first of all I had to create that style using following code:
```
buttonFont = CreateFont(20,0,0,0,FW_DONTCARE,TRUE,
  FALSE,FALSE,DEFAULT_CHARSET,
  OUT_OUTLINE_PRECIS,
  CLIP_DEFAULT_PRECIS,
  CLEARTYPE_QUALITY,
  VARIABLE_PITCH,
  TEXT("Cambria"));
```

Then I send a *WM_SETFONT* message and only after that I created the button using `CreateWindowEx`. It is strange that it is not mandatory to provide font handler to created button but instead font is set for the whole window application.

### Add 2 text inputs to window: one with default styles, one with custom styles (size, background, text color, font family, font size)

_todo_

### Add 2 text elements to window: one with default styles, one with custom styles (size, background, text color, font family, font size)

_todo_

### Make elements to fit window on resize **(1 pt)**

_todo_

### Make elements to interact or change other elements (1 pt for 2 different interactions) **(0-2 pt)** _(ex. on button click, change text element color or position)_

_todo_

### Change behavior of different window actions (at least 3). For ex.: on clicking close button, move window to a random location on display's working space **(1 pt)**

_todo_

### Write your own PSG (you can take existent one and modify it) and argue why it is better (for you) **(1 pt)**

_todo_

### Additional taks done for fun

I used .rc file to set my window icon and menu to control some functions.

## Conclusions:

This laboratory work was a groundbreaking for me. It is first time when I encountered a non-linear control flow based on events. It was also strange to discover that some window properties are set for the whole window and not per specific entities (like buttons custom font). It was interesting to find out that actually windows have a life-cycle.

It was interesting to find out that even if C++ is considered OOP it doesn't use objects but structures (yes, it is because up to Windows 8 it is written in C). That broke my mindset that everything should be a class instance and that very often instead of badly used class instance it may be easier just to use a structure.

Another interesting thing was to make the window responsive. In browsers it seems to be so easy but when you write everything by yourself it starts to be less intuitive and simple. Also for long time I was wondering why browsers do not provide an eary method to customize buttons and very often each browser has its own different style for buttons. But now after trying to change default styles of a button I can see that it is not that easy as it seems and most probably developers just used default buttons to save some time and skip some pain.
