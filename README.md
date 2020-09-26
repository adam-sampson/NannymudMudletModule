# NannymudMudletModule

A Mudlet module for getting started with NannyMUD

This module is to help get some very basic commands started in Mudlet for playing Nannymud. Players should be able to use this as a template that has examples to help them figure out how to customize the module themselves.

Some things that are included:

- A speedcommand trigger that parses commands in the form of ".1s3e1n"
- Speedwalking commands to common pubs and guilds
- A Geyser layout that can be used as is, modified, or disabled completely (reset mudlet after disabling)
  - Captures HP/SP
  - Captures HP/SP from other mudlet windows
  - Captures tells, says, and whispers to a comm window
- Examples of multiplayer command functionality using raiseGlobalEvent()
  - Allows you to send commands to other windows using a shortcut alias ("hh pray to lars" sends a command to Helix window to pray to lars)
- Examples of scripts to capture raised global events and to determine whether or not to parse them

# Warranties

None. There are no warranties. Use this at your own risk. If your character dies using this it is completely your problem. Don't use this if you aren't comfortable with that.

# Setup

1) Install Mudlet
2) Create a character in mudlet (each character you have gets a different connection)
3) From the character's playing window click the dropdown next to Package Manager, and then select Module Manager
4) In the Module Manager click Install. Select the nannymud - shared.xml file that you downloaded from this repo.
5) In the Module Manager click the checkbox next to "sync" (this will make it so changes you make to the module will apply to all of your characters and not just one.
6) Close the window and try out some of the triggers and aliases.

Note: Modules can be synced so that when you change it for one character it changes for all characters. I recommend doing this unless you know more about packages.

# Speedwalking

The default speedwalk for this module is is a "." followed by numbers and letters such as ".25w2n". The Regex trigger grabs all characters separated by numbers. Therefore, every command you want to send must be a paired set of a number followed by some letters. The "." speedwalk cannot handle commands that have numbers in them such as "enter portal 2". 

The ".." command attempts to reverse a set of directions. It reverses the order of all of the pairs and tries to reverse the direction. For example "..25w2n" becomes ".2s25e".
If the script does not know how to reverse a direction it will return the direction. For example "..1enter gate" becomes ".1enter gate". The known directions are located under scripts/nannymud module rev2/reverse_directions. You can add more reversable directions but be cautious because not all directions reverse the same in the game. 

The ";" command is currently set as the command split character. You can use "smile;eyepoke Absence" to send two commands simultaneously. This can also compliment directions. For instance you can use ".2e1n3w;enter portal 1;.1n". But be aware that the ";" is a different command than the "." command. So to reverse those directions you would need "..1s;enter portal;..2e1n3w". 

The locations for the speedwalker are added using scripts/nannymud module rev2/add_locations. This script has a string in it called csv_string. A csv string was used because it was easy to export from any spreadsheet and was easier to program than figuring out how to do file manipulations. You can add a csv string in the following format to load your locations into the module. 

  alias,desc,full_to,full_from,safe_to_delta,safe_from_delta,monsters,equipment,other
  monk,To Monk Guild,.3s2w2n1e2s,..3s2w2n1e2s,,,,,Monk Chapel
  
The module doesn't care about any column to the right of these. You can also feel free to change the code. It should be fairly clear how to do that. 

To use locations the command is currently "./alias" to run the "full_to" directions, and "../alias" to run the "full_from" directions. So "./monk;pray to lars;../monk" will help you to build points with the big guy. This can be changed in the aliases by changing the regex for autowalk. 

# Default GUI

The default graphic interface for this module is basic. The goal was to provide information with minimal interuption to the text. Feel free to modify locations and sizes. 

![Image of GUI](https://raw.githubusercontent.com/adam-sampson/NannymudMudletModule/master/GUI_v2.png)

# Changes and improvements

Please feel free to make changes and improvements. You can fork this repo for your own use. You can also submit a pull request or add an issue to request an improvement.
