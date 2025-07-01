

## Prep
1) Download/Create the sound

2) Download mod tool from steam library `Don't Starve Mod Tools`
    - if you can't find it, make sure `tools` is ticked above the steam library search bar

3) Launch `Don't Starve Mod Tools` and select `Launch FMOD Designer` as launch option

## Events 
### Groups
4) Click `File` - `New project`

5) Locate your mod's sound folder(`mod_name`/`sound`) and give it a file name, if you don't have a sound folder then create one

6) Go to `Events` - `Groups` - Rename your untitled group name to `sound` by changing its property name value

7) Next to the `sound` group icon inside `Groups`, click on the `+` symbol to show all events inside the group

8) Right click `event00` and delete it

9) Right click `sound` group - `Add Simple Event...` - Give it a name and press ok

10) Right click on the empty space inside `Sound` below `Playlist` - `Add sound` - Locate your audio/sound file then select it and open it

11) Optional but I like to change my property `Mode` to `3d` & `3D Max Distance` to `30` & 3D Rolloff to `Linear`

12) File path is above the play button

### Category
13) To make the sound volume changeable through in game settings you need to go to `Events` - `Categories`

14) Right click on `master` category - `Add Event Category` - give it a name of `set_sfx`
    - Could also create any of these:
    - `set_sfx`
    - `set_ambience`
    - `set_music`

15) You should be able to see 3 items inside master category `Music`, `set_sfx` and an event of whatever you previously named

16) Drag that event onto your `set_sfx` category

## Banks
17) Click on `Banks`

18) Remove `_bank00` from bank name

## Build
19) Click on `Project` - `Build` or you can just press `Ctrl + B`

20) Select the banks and press on `Build`

21) Now you should be able to see some files generated inside your `mod_name`/`sound` directory. The 2 that is important is xxx.fev and xxx.fsb, the rest you don't need

## How to use it?
22) Inside your modmain.lua or whatever paste in the code below and change it accordingly based on your own naming
``` lua
Assets = {
    Asset("SOUNDPACKAGE", "sound/xxx.fev"),
    Asset("SOUND", "sound/xxx.fsb"),
}
```

23) To use the sound you need to use sound emitter, so something like this
``` lua
-- Check step 12 to locate file path
x.SoundEmitter:PlaySound("your/file/path")
```