# love-eclipse-ldt

LOVE2D Eclipse LDT Execution Environment. That means you get autocomplete and all that.

This repository is the contents of a .zip file you could feed into Eclipse LDT.

![Eclipse LDT LOVE2D Screenshot](http://i.imgur.com/x8shhcc.png)

# Pre-requisites

Obviously you will need to have the [eclipse LuaDevelopmentTools](https://eclipse.org/ldt) installed. Also fundamental: A working LOVE2D interpreter. You *can* use the Execution Environment with eclipse using the default Lua5.1 interpreter or any other, but don't blame me or open an issue if your (well, at least autocompleted) code won't run (Spoiler: It won't). So, please check out the [Getting Started pages at the LOVE2D-Wiki](https://love2d.org/wiki/Getting_Started) and the [LDT Wiki on interpreters](https://wiki.eclipse.org/LDT/User_Area/User_Guide#Managing_Interpreters) first.

# Pre-built

Lucky for you, installation of the Execution Environment is a breeze thanks to the latest in archiving technology!

1. Grab the latest .zip package from https://github.com/leafi/love-eclipse-ldt/releases .
2. Start a new Lua project in LDT
3. Under 'Targeted Execution Environment' in the new project options, click Configure Execution Environments...
4. Click Add...
5. Browse to the .zip file you downloaded
6. Just use that, basically. It should work. Open an Issue if it doesn't!
7. ...And if this isn't a brand new project from the default template, then you **also** need to go in the build path options (right-click project on left, click Properties, then go to Lua > Build Path) and on the Libraries tab, click Add Library... and add the execution environment zip. Sorry, just discovered that myself.

# Building it yourself

The api.zip is built using https://github.com/leafi/love-api-to-ldt-luadoc, a tool which *itself* takes the LOVE2D API definitions from https://github.com/love2d-community/love-api. Phew!

1. Go to https://github.com/leafi/love-api-to-ldt-luadoc and follow the instructions in the README - carefully.
2. With those instructions thoroughly followed, you now find yourself with an api.zip file.
3. Download the contents of *this* repository, and replace api.zip with the one you made.
4. In the love-eclipse-ldt folder, zip everything. You must be INSIDE the folder. The top-level of the .zip should be .rockspec, api.zip and all that - no love-eclipse-ldt folder in sight!
5. Follow the 'Pre-built' instructions above from step 2 onwards to install the bugger.

# Issues

Current TODOs:

* utf8 Lua module missing - tell me where to find a definition file and I'll stuff it in.
* No enum definitions.
* All functions only have their last definition output. Function overloading is ignored! I can't find a good way to implement this. I think we just need to conjure up a good heuristic to pick the 'best' option.

# Credits

@sirskunkalot for updating from 0.9.2 to 0.10.1. And continuing.

Original Koneki (pre-LDT) API files: https://github.com/mkosler/LOVELuaDoc

And https://github.com/love2d-community/love-api is the definition set we produce api.zip from nowadays.
