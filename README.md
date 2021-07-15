# Quickenu

Quickenu is a simple utility that allows the creation of shortcuts to files, folders, and executables, which are presented as a menu accessed from the system tray.

## The Name

The name Quickenu came from combining `Quick` and `Menu`. I liked it because it could also be interpreted as "quicken you", which is the goal of the application, to make it quicker to access things you might otherwise was time locating on you computer. It's not super clever, but I like it 😊.

## Goals

The goal of Quickenu is to provide a system tray icon that will show a popup menu when clicked. The menu should provide the following:

- Menu items that open a file, folder, executable, or combination thereof.
- Menu items that point at a folder and provide a submenu of the contents of the file (optionally filtered by simple file masks)
- Grouping of menu items. Groups separated by standard separators
- Configuration should also support putting menu items within another menu item

## Status

No code yet. Currently fleshing out configuration ideas.

## Proposed Configuration

Quickenu's configuration is a JSON file.

```json
{
    "settings": {},
    "menu" : {
        [
            "group": {
                "menuitem": {
                    "caption":"visible in menu",
                    "groups":[
                        // optional subgroups
                    ],
                    "targets":[
                        {
                            "file":{
                                "path":"path to file",
                                "parameters":"optional parameters for executables"
                            }
                        },
                        {
                            "folder":{
                                "path":"path to folder",
                                "knownfolder":"a supported know folder (downloads)",
                                "listcontents":"boolean indicating a folders contents should be generated as a submenu",
                                "listmasks":"an optional list of masks that filter the files shown in generated submenu"
                            }
                        },
                    ]
                }
            }
        ]
    }
}
```
