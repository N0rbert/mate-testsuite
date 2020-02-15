# MATE Panel

MATE Panel is preinstalled on MATE DE. It is usually shown on the top and down parts of the screen. Its main executable is named `mate-panel`.

## Applets

MATE Panel has a lot of preinstalled applets.

### Testing applets

MATE Panel allows to test any applet by using special program named `mate-panel-test-applets`.

Steps to test:
1. Open MATE Terminal
1. Execute `mate-panel-test-applets`
1. In the *Test applet utility* select needed *Applet* and then click *Execute*
1. Ensure that applet is shown in separated window and it looks as expected
1. Close the *Test applet utility*

Expected results:

* the *Test applet utility* was opened, all applets look and operate as expected.

### Add and remove applets

MATE Panel allows user to add and remove applets.

#### Add custom application launched

Steps to test:
1. Move mouse cursor above top MATE Panel 
1. Do a right mouse click
1. Select *Add to Panel*
1. Choose *Custom Application Launcher* and click *Add*
1. Fill all needed fields with needed information (for example: *Type* : *Application*, *Name:* `MATE Calculator`, *Command*: `mate-calc`) and click *OK*
1. Test the applet by clicking on it

Expected results:

* user is able to add *Custom Application Launcher* applet to the Panel, the application from it can be launched normally.

#### Add application launcher

Steps to test:
1. Move mouse cursor above top MATE Panel 
1. Do a right mouse click
1. Select *Add to Panel*
1. Choose *Application Launcher* and click *Add*
1. Select needed application from the list (or use search) and click *Add*
1. Test the applet by clicking on it

Expected results:

* user is able to add *Application Launcher* applet to the Panel, the application from it can be launched normally and has correct icon for selected application.

#### Add applet

Steps to test:
1. Move mouse cursor above top MATE Panel 
1. Do a right mouse click
1. Select *Add to Panel*
1. Choose needed applet in the opened *Add to Panel* window and click *Add*
1. Close the *Add to Panel* by clicking *Close*
1. Test the just added applet

Expected results:

* user is able to add applet to the MATE Panel, applet looks and operates well.


#### Remove applet

Steps to test:
1. Move mouse cursor above the some applet of top MATE Panel
1. Do a right mouse click
1. Select applet to remove and click *Remove From Panel*

Expected results:

* user is able to remove applet from the MATE Panel, removing the applet do not crash the Panel.

## Panel reset

Any panel may be reseted to its default view for current panel layout. Do not reset panel appearance on your daily driver systems without screenshot or other way of backup.

Steps to test:
1. Reset the panel 
    * Move mouse above needed MATE Panel and do right mouse click and select *Reset Panel*
    * Use terminal and run `mate-panel --reset` command here
1. Ensure that panel was reseted to the current layout defaults

Expected results:

* MATE Panel was running with some appearance, then it was reseted to current layout default and it is still running.

## Panel restart/replace

Steps to test:
1. Open MATE Terminal
1. Execute `mate-panel --replace &`
1. Close MATE Terminal

Expected results:

* MATE Panel was running with some appearance, then it was restarted/replaced and it is still running.

## Using Run dialog

Steps to test:
1. Open *Run Application* dialog

    * Press `<Alt>+<F2>`
    * Open terminal and execute `mate-panel --run-dialog`
1. Enter application name - for example `mate-calc` and click *Run*
1. Ensure that application is started

Expected results:

* the *Run Application* window was shown, reacted on the user input and started needed application after click on *Run*.

## Screenshot

MATE Panel package provides `mate-panel-screenshot` for creating screenshots. It is a just a symlink to `mate-screenshot`.

Steps to test:
1. Open MATE Terminal
1. Execute `mate-panel-screenshot`
1. Save the screenshot somewhere

Expected results:

* The *Save screenshot* window was shown, user is able to save screenshot.

