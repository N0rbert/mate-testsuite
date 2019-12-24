# Caja file manager

Caja file manager is preinstalled on MATE DE. It may be called from terminal as `caja`.

## Extra pane in Caja

Steps to test:

1. Open Caja
1. Press `<F3>`

Expected results:

   * Caja opened extra pane in the right of already opened pane.

Press `<F3>` again to close the extra pane.

## Folder backgrounds and emblems

Steps to test:

1. Open Caja
1. Select *Edit* → *Backgrounds and Emblems*

TBW (see https://askubuntu.com/a/1157888/66509 )

## Create archive

Caja allows to create archives from the drop-down menu using *Compress* option.

### Normal archive

Steps to test:

1. Open Caja
1. Select some folder or file
1. Choose *Edit* → *Compress*
1. Select needed archive type and click *Create*

Expected results:

* archive is created. Caja is able to open it with Engrampa.

### Password protected archive

Steps to test:

1. Open Caja
1. Select some folder or file
1. Choose *Edit* → *Compress*
1. Select zip-archive type
1. Click on *Other Options*, enter password into *Password* field
1. Click *Create*

Expected results:

* archive is created. Caja is able to open it with Engrampa using specified password.


## Removable drives

### USB solid state flash disk Eject

Steps to test:

1. Open Caja
1. Insert USB flash drive
1. Wait USB flash drive to be initialized (mounted)
1. On the left side pane under *Devices* section select USB flash drive and press *Eject* button.

Expected results:

* Caja ejected USB flash drive. Desktop notifies user with the message *It is safe to remove the drive*.

### USB hard disk drive safely removal

Steps to test:

1. Open Caja
1. Insert USB hard disk drive
1. Wait USB hard disk to be initialized (mounted)
1. On the left side pane under *Devices* section select USB hard disk, make right mouse click on it and choose *Stop* (or *Safely remove drive*) option.

Expected results:

* Caja stopped USB hard disk. It does not rotate anymore.

## Caja scripts

Caja allows to use custom scripts.

Steps to test:

1. Create folder with scripts with `mkdir -p ~/.config/caja/scripts`
1. Add simple script named `Open Terminal` with

        cat <<EOF > ~/.config/caja/scripts/Open-Terminal-Here
        #!/bin/bash
        
        # Created by oss-lvr (https://github.com/oss-lvr)
        # Open a terminal from anywhere
        
        mate-terminal $CAJA_SCRIPT_CURRENT_URI
        EOF

  and make it executable with `chmod +x ~/.config/caja/scripts/Open-Terminal-Here`

1. Go to some folder, then navigate to or select some folder and click *File*→*Scripts*→*Open-Terminal-Here*

Expected results:

* The MATE Terminal is opened in the location of current (or selected) folder.

## Caja extensions

Install all Caja extensions with the following command:

```
sudo apt install $(apt-cache search caja | awk '{print $1}')
```

restart Caja with `caja -q` and then go to *Edit* → *Preferences* (or run `caja-file-management-properties`), switch to *Extensions* and compare their list with the table below:

| Available Extensions       | 16.04 LTS | 18.04 LTS |  19.10 |
|----------------------------|-----------|-----------|--------|
| libgtkhash-properties-caja |    n/a    |     +     |    +   |
| libcaja-seahorse           |    n/a    |     +     |    +   |
| Image Converter            |     +     |     +     |    +   |
| Share                      |     +     |     +     |    +   |
| User Share                 |    n/a    |    n/a    |    +   |
| Open terminal              |     +     |     +     |    +   |
| libcaja-actions-tracker    |     +     |     +     |    +   |
| libcaja-actions-menu       |     +     |     +     |    +   |
| Wallpaper                  |     +     |     +     |    +   |
| Python: caja-thg           |   manual  |     +     |   n/a  |
| Python: caja-admin         |    n/a    |     +     |    +   |
| Python: folder-color       |    n/a    |     +     |    +   |
| Python: deja (or *dejadup*)|    n/a    |     +     |    +   |
| Python: syncstate-ownCloud |    n/a    |     +     |    +   |
| Python: syncstate-Nextcloud|    n/a    |    n/a    |    +   |
| Python: caja-rename        |    n/a    |     +     |    +   |
| Python: caja-mediainfo-tab |    n/a    |    n/a    |    +   |
| Python: insync-caja-plugin |    n/a    |    n/a    |    +   |
| libeiciel-caja             |    n/a    |     +     |    +   |
| xattr Tags                 |    n/a    |     +     |    +   |
| Atril properties           |    n/a    |     +     |    +   |
| Gksu                       |     +     |    n/a    |   n/a  |
| Engrampa                   |     +     |     +     |    +   |
| Caja Dropbox               |     +     |     +     |    +   |
| Send To                    |     +     |     +     |    +   |
| libfma-caja-tracker        |    n/a    |    n/a    |    +   |
| libfma-caja-menu           |    n/a    |    n/a    |    +   |

Also check the Caja window for the interface elements from the table:

| Package name         | Interface items                                  | 16.04 LTS | 18.04 LTS | 19.10 |
|----------------------|--------------------------------------------------|-----------|-----------|-------|
| caja-actions         | *Caja-Actions Actions* [^1]                      |     +     |     +     |  +    |
| caja-admin           | *Open as Administrator*, *Edit as Administrator* |     +     |     +     |  +    |
| caja-eiciel          | *Properties* → *Access Control Lists*            |    n/a    |     +     |  +    |
| caja-extension-fma   | *FileManager-Actions Actions* [^2]               |    n/a    |    n/a    |  +    |
| caja-gtkhash         | *Properties* → *Digests*                         |    n/a    |     +     |  +    |
| caja-image-converter | *Resize Images*, *Rotate Images*                 |     +     |     +     |  +    |
| caja-mediainfo       | special mediainfo tab                            |    n/a    |    n/a    |  ?    |
| caja-nextcloud       | ???                                              |    n/a    |    n/a    |  ?    |
| caja-open-terminal   | *Open in Terminal*                               |     +     |     +     |  +    |
| caja-owncloud        | ???                                              |    n/a    |     ?     |  ?    |
| caja-rename          | *Rename*                                         |    n/a    |     +     |  +    |
| caja-seahorse        | *Encrypt*, *Sign*                                |    n/a    |     +     |  +    |
| caja-sendto          | *Send to*                                        |     +     |     +     |  +    |
| caja-share           | *Sharing Options*, *Properties* → *Share*        |     +     |     +     |  +    |
| caja-wallpaper       | *Set as wallpaper*                               |     +     |     +     |  +    |
| caja-xattr-tags      | *Tags* column                                    |    n/a    |     +     |  +    |
| deja-dup-caja        | *Revert to Previous version*,*Restore Missing...*|     +     |     +     |  +    |
| folder-color-caja    | *Folder's Color*, *File's Emblem*                |     +     |     +     |  +    |
| nitroshare-caja      | ???                                              |    n/a    |     ?     |  ?    |
| caja-dropbox         | Dropbox folder and Dropbox menu                  |    n/a    |     +     |  +    |

[^1]: to get Caja Actions submenu we need to create custom action from `caja-actions-config-tool` - press *File* → *New action*, go to *Command* tab and the following into *Path* - `zenity --info --text=%b` and then click *File* → *Save*. Then close Caja with `caja -q` and open it again, select some item and make right click on it, then select *Caja-Actions Actions actions* → *New Caja Action*. This will end with showing Information window with the text indicating current item name.

[^2]: to get FileManager Actions submenu we need to create custom action from `fma-config-tool` - press *File* → *New action*, go to *Command* tab and the following into *Path* - `zenity --info --text=%b` and then click *File* → *Save*. Then close Caja with `caja -q` and open it again, select some item and make right click on it, then select *FileManager-Actions actions* → *New Caja Action*. This will end with showing Information window with the text indicating current item name.

### Detecting text file conflicts

Caja has functionality to check text file conflicts using Meld.

Steps to test:

1. Install Meld with `sudo apt-get install meld`
1. Create two text files in two directories using terminal by running `echo text1 > /tmp/file; echo text2 > ~/file`
1. Open Caja with two panes - left pane with home-folder, right pane with `/tmp`
1. Try to copy `file` from left pane to the right pane.

Expected results:

* The File conflict window is shown, it asks user to view differences. Pressing *Differences* will lead to Meld open for file comparison.


### Installing third-party extensions

#### TortoiseHG

Installation:

* on 16.04 LTS it is installable with manual steps with method from [this AskUbuntu Q&A](https://askubuntu.com/a/1132783/66509):

        sudo apt-get install tortoisehg-nautilus caja-extensions-common python-caja

        mkdir -p ~/.local/share/caja-python/extensions
        cp /usr/share/nautilus-python/extensions/nautilus-thg.py ~/.local/share/caja-python/extensions/caja-thg.py

        sudo apt-get purge tortoisehg-nautilus
        sudo apt-get autoremove
        sudo apt-get install tortoisehg mercurial

* on 18.04 LTS and 19.04 you can use `sudo apt-get install tortoisehg-caja`;
* on 19.10 it is not installable.

After installation restart Caja with `caja -q && caja`.

Steps to test:

1. Open Caja
1. Navigate to any folder
1. Make right mouse click on the folder - it should show *TortoiseHG* menu with items *Clone*, *Create Repository Here*, *Global Settings*, *About TortoiseHG*.
1. Click on the *Create Repository Here* and then *Create* button. This will open TortoiseHG Workbench window. Close it and press `<F5>` in the Caja window.

Expected results:

* TortoiseHG repository is created, the freshly created repository has green star icon/emblem shown on top of it.

#### RabbitVCS

Installation:

* for 16.04 LTS, 18.04 LTS and 19.04 install RabbitVCS with method similar to [this AskUbuntu Q&A](https://askubuntu.com/a/1149104/66509):

        sudo apt install rabbitvcs-cli python-caja

        mkdir -p ~/.local/share/caja-python/extensions
        cd ~/.local/share/caja-python/extensions
        wget https://raw.githubusercontent.com/rabbitvcs/rabbitvcs/v0.16/clients/caja/RabbitVCS.py
        caja -q
        caja

* for 19.10 use:

        sudo apt install rabbitvcs-cli python-caja python-tk

        mkdir -p ~/.local/share/caja-python/extensions
        cd ~/.local/share/caja-python/extensions
        wget https://raw.githubusercontent.com/rabbitvcs/rabbitvcs/v0.17.1/clients/caja/RabbitVCS.py
        caja -q
        caja

Steps to test:

1. Open Caja
1. Navigate to any folder
1. Make right mouse click on the folder - it should show *RabbitVCS SVN*, *RabbitVCS Git*, *RabbitVCS Hg* menus with rabbit icon.
1. Click on the *RabbitVCS Git* → *Initialize Repository*. This will open Initialize Repository window. Close it by pressing OK and press `<F5>` in the Caja window.

Expected results:

* RabbitVCS Git repository is created, the freshly created repository has green checkmark icon/emblem shown on top of it.

## Check error output on Caja restart

To check errors and warnings during Caja restart:

1. open two terminal windows
1. execute `tail -f ~/.xsession-errors` on the first terminal
1. execute `caja -q` on the second terminal

Expected results:

* the are no serious messages with `Error`, `Warning`, `Critical` text

## Errors and warnings about Caja itself, Caja-Python and so on

The following example may be considered as safe:

```
/usr/lib/python2.7/dist-packages/gi/overrides/Gtk.py:50: RuntimeWarning: You have imported the Gtk 2.0 module.  Because Gtk 2.0 was not designed for use with introspection some of the interfaces and API will fail.  As such this is not supported by the pygobject development team and we encourage you to port your app to Gtk 3 or greater. PyGTK is the recomended python module to use with Gtk 2.0
  warnings.warn(warn_msg, RuntimeWarning)
sys:1: PyGIWarning: Caja was imported without specifying a version first. Use gi.require_version('Caja', '2.0') before import to ensure that the right version gets loaded.
```

## Caja self check

Caja help page (`caja --help`) shows the following text about self-check (`-c`):

> `-c, --check                     Perform a quick set of self-check tests.`

To run a self-check use:

```
caja --check
```

it should end with the following output 

```
running caja_self_check_file_utilities
running caja_self_check_file_operations
running caja_self_check_directory
running caja_self_check_file
running caja_self_check_icon_container
running caja_self_check_file_utilities
running caja_self_check_file_operations
running caja_self_check_directory
running caja_self_check_file
running caja_self_check_icon_container

```

and zero exit-code (check it with `echo $?`).
