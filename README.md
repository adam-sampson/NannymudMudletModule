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

# Changes and improvements

Please feel free to make changes and improvements. You can fork this repo for your own use. You can also submit a pull request or add an issue to request an improvement.
