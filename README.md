# faq

A repository filled with questions that I ask a lot during development.

## Unity (2D + 3D)

- Questions I ask while developing 2d games.

## Blender

- Questions I ask when creating 3D models.

## Windows Reinstall

- Questions that I ask each windows reinstall.

### Question 1: What programs should I reinstall

    - CLIs:
      - Aria2c - downloader
      - Cmder - downloader
      - PhantomJS - headless browser
      - Vagrant - virtual machines
      - YoutubeDL - downloader
    - Programs:
      - Chrome - browser
      - Firefox - browser
      - Opera - browser
      - IfranView - image viewer
      - VLC Media Player - media viewer
      - CCleaner - windows cleaner
      - Malwarebytes - virus finder
      - YoutubeDLG - downloader
      - Pot Player - media viewer
      - Docker Desktop - development containers
      - Steam - gaming
      - qBittorrent - torrent downloader
      - NordVPN - vpn
      - Teamviewer 14 - remote controlling
      - JDownloader 2 - downloader
      - WinSCP - ssh client
      - Putty - ssh client
      - Oracle VM Virtualbox - virtual machines
      - Steamlabs OBS - streaming
      - Zenkit - kanban board
      - Krita - digital drawing
      - Blender 2.8 - 3D modeling  
      - Paint.net - digital drawing
      - Draw.io - diagrams
      - Sketchbook - digital drawing
      - Synctrazor - file synchronization 
      - Visual Studio Code - IDE
      - Intellij Idea - IDE
      - Eclipse - IDE
      - Unity Hub - game development 

### Question 2: How to setup Cmder

  Guide for step 1: <https://github.com/cmderdev/cmder/wiki/Setting-up-Environment-Variables>

  Guide for step 2: <https://github.com/cmderdev/cmder/wiki/Context-menu-integration>

  Guide for step 3: <https://github.com/cmderdev/cmder/wiki/Seamless-VS-Code-Integration>

  Guide for step 4: <https://github.com/HamidFaraji/panda-theme-cmder>

  Customizations: <https://github.com/cmderdev/cmder/wiki/Customization>

  1. Add Cmder to path:
     1. Press the windows key and type path.
     2. Select "Edit the System Environment Variables"
     3. Press "Environment Variables"
     4. Select "New" under System variables.
     5. Create a new variable with the name "CMDER_ROOT" with the value being the path to your install of Cmder ex: "C:\Cmder"
     6. Double click on PATH then select "New"
     7. Add the path from step 5.
  2. Add Cmder to context menu
     1. Create a new file called OpenCmderHere.reg
     2. Add the following to the file:

        ```
        Windows Registry Editor Version 5.00

        [HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder]
        @="Open Cmder Here"
        "Icon"="\"%CMDER_ROOT%\\icons\\cmder.ico\",0"

        [HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder\command]
        @="\"%CMDER_ROOT%\\Cmder.exe\" /START \"%v\""
        ```

      3. Double click on the file to run the script.
      4. If the script does not work properly (as in an error pops up when trying to open Cmder through the context menu) open regedit.
      5. Type the following into the search bar: HKEY_CLASSES_ROOT\Directory\Background\shell
      6. Click on Cmder > Icon and select which ever icon color ico file then change %CMDER_ROOT% to the path of your Cmder install location.
      7. Select Cmder > command > Default then change %CMDER_ROOT% to the path of your Cmder install location.
   3. Integrate Cmder into VS Code
      1. Press CTRL + , in VSCode
      2. Search for settings.json
      3. Select Edit in settings.json
      4. Add the following:

        ```
        {
            "terminal.integrated.shell.windows": "cmd.exe",

            "terminal.integrated.env.windows": {
            "CMDER_ROOT": "C:\\Cmder"
            },
            "terminal.integrated.shellArgs.windows": [
                "/k C:\\Cmder\\vendor\\init.bat"
            ],
        }
        ```
    4. Set Cmder theme to panda
       1. Open Cmder's settings.
       2. Select Features > Colors.
       3. Set the Standard colors to #RRGGBB (hex)
       4. Set the colors to these #RRGGBB (hex) values:
        ```
        Row 1: Left
        #292a2b
        #6fc1ff
        #ff75b5
        #ff9ac1
        Text: Auto 

        Row 2: Middle left
        #ff2c6d
        #45a9f9
        #ffb86c
        #e6e6e6
        Back: #0

        Row 3: Middle right
        #676b79
        #000000
        #19f9d8
        #45a9f9
        Popup: Auto

        Row 4: Right
        #ff75b5
        #b084eb
        #ffcc95
        #ffffff
        Back: Auto
        ```
