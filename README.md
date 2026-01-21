# ProjectZomboidMod

A repo to document my learning of a Project Zomboid Mod Development

Do note this current mod is for development of Build 42, specifically Build 42.13.2, which at current is in an unstable state. I plan on making this mod multiplayer friendly so this might be a smorgasbord of mod ideas all thrown into one mod.
This mod will also be coded in LUA, while Java would be "better" in a sense as its more "open" compared to LUA, the Steam Workshop doesn't accept Java mods - I believe this is down to .jar technically being execution files.

The plan is to iterate through modding development and potentially help new modders out as they will be able to look through all the Pushes to figure out what has been done.
The first push is going for be the folder setup in `C:\Users\[User]\Zomboid\Workshop\[FolderName]`

Some knowledge points:
Zomboid Workshop folder: `C:\Users\[User]\Zomboid\Workshop`
This is where we will actually be making our mods
Note that the "mods" folder found in the same directory is for manually adding mods to the game, this is mainly for the use of Java based mods

Note that I could also use Branches in terms of development, both if I am making a smorgasbord of a mod, if I am working on seperate aspects, or the mod gets very large

---

# File Structure

A bit of information here:

```
.
├── mod.info
├── preview.png
├── README.md
└── Contents
    └── mods
        └── ProjectZomboidMod
            ├── mod.info
            ├── poster.png
            ├── 42
            │   ├── mod.info
            │   ├── poster.png
            │   └── media
            │       └── lua
            │           ├── client
            │           │   └── client.lua
            │           ├── server
            │           │   └── server.lua
            │           └── shared
            │               └── shared.lua
            ├── common
            │   └── .placeholder
            └── media
                └── lua
                    ├── client
                    │   └── client.lua
                    ├── server
                    │   └── server.lua
                    └── shared
                        └── shared.lua
```

### I could be wrong on this, this is just what I know of, I can correct this as needed

This is the current, temp layout that I have, lets work our way top down:

- mod.info
    - This contains information about the mod, specifically the name of the mod, the id of the mod, the author of the mod, the poster and icon for the mod - which is steam related, version for the mod and description
    - must have
- preview.png
    - this is just an image to preview the mod
    - please for the love of all things dont use AI Generated bs for this. Take a screenshot in game, doodle something in paint, ask a friend idk anything but AI
    - must have
- README.md
    - this is what you are reading, you can ignore this as its not apart of the mod development
    - though its good to add in case there are circumstances in which you move on from modding and hand it over to someone else
- Cotents
    - this is a folder. its a must have
- Cotents/mods
    - a folder within Contents. its a must have
- Cotents/mods/ProjectZomboidMod
    - this is the name of your mod, if you are adding a car name it after that car
- Cotents/mods/ProjectZomboidMod/mod.info
    - this is a copy of the first one
    - i believe if this is left blank it will copy the contents of the first one
- Cotents/mods/ProjectZomboidMod/poster.png
    - the preview.png but smaller
    - again, dont use ai
- Cotents/mods/ProjectZomboidMod/42
    - this is specific for Build 42 as Build 42 had a rewrite in some of the code and so it must follow this for versioning
        - you can make folders for the version as well but I believe it only looks at the first decimal i.e. 42.13.1 and 42.13.2 are the same but something like 42.13 and 42.15 are different
    - we can assume that if and when Build 43 is released it will also be 43 for the folder
- Cotents/mods/ProjectZomboidMod/common
    - this is for Build 41 and previous versions of the game
    - this is needed to be here even for build 42 - it can remain empty
- Cotents/mods/ProjectZomboidMod/42/mod.info
    - again, its the same as the other mod.info
    - it feels redunant to have all these mod.info's i know but when you go to upload the mod PZ freaks out at you for not having it -\_-
- Cotents/mods/ProjectZomboidMod/42/poster.png
    - same as the other poster.png
- Cotents/mods/ProjectZomboidMod/42/media
    - container folder
- Cotents/mods/ProjectZomboidMod/42/media/lua
    - container folder
- Cotents/mods/ProjectZomboidMod/42/media/lua/client
    - where client based lua code goes
- Cotents/mods/ProjectZomboidMod/42/media/lua/server
    - where server based lua code goes
- Cotents/mods/ProjectZomboidMod/42/media/lua/shared
    - where code that runs on both client and server goes

Here is a command to create the exact same setup - make sure you are already in your Root folder of `C:\Users\[User]\Zomboid\Workshop\[FolderName]`
`mkdir -p Contents/mods/ProjectZomboidMod/42/media/lua/{client,server,shared} Contents/mods/ProjectZomboidMod/common Contents/mods/ProjectZomboidMod/media/lua/{client,server,shared} && touch mod.info preview.png README.md Contents/mods/ProjectZomboidMod/{mod.info,poster.png} Contents/mods/ProjectZomboidMod/42/{mod.info,poster.png} Contents/mods/ProjectZomboidMod/42/media/lua/client/client.lua Contents/mods/ProjectZomboidMod/42/media/lua/server/server.lua Contents/mods/ProjectZomboidMod/42/media/lua/shared/shared.lua Contents/mods/ProjectZomboidMod/common/.placeholder Contents/mods/ProjectZomboidMod/media/lua/client/client.lua Contents/mods/ProjectZomboidMod/media/lua/server/server.lua Contents/mods/ProjectZomboidMod/media/lua/shared/shared.lua`
