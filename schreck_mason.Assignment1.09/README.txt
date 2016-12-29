Implemented a series of methods and a class this week to handle player interaction with objects.

inventory.h and inventory.cpp were implemented to provide an interface like relationship for PC and the dungeon items. This helped me to better conceptualize what was going on with the PC
when items were picked up, and what these interactions looked like when acting upon a vector of Item *.

Within ui.cpp I implemented iList() which was to display inventory items and interactions. This is done by pushing 'i' within the main game menu. If the user has any items in their inventory
they are displayed (up to 10 items). Once this screen is open, the user may expunge an item by pressing 'x' and choosing an inventory index to expunge. The user may choose to also inspect an
item, which is done by pressing 'I' then selecting an index to inspect, this prompts the description for the item at a given index. By pushing 'w' when the inventory is open and selecting an index
will equip the item to the PC. Equipping items in turn varies the PC's defense, damage, and speed. If an item is already equipped of that specific item type, the new item selected is equipped and the
PC's stats are updated to reflect the new item. NOTE: that there is no prompt other than in debug.log that an item of the same time has been equipped. In debug.log it simply prompts a message that an 
item of that type is already equipped, then swaps them and the stats are updated.

To un-equip an item, the inventory does not need to be open. During the game simulation, simply push 't' which prompts a warning to choose an equipment index (0-11) to un-equip. 
NOTE: that I varied from the spec here and my equipment is always displayed on the bottom right-hand of the game screen. This idea stemmed from Yuxiang's intro implementation of the equipment slots.
So I do not push 'e' to open equipment, but all equipping of items and un-equiping of items will be visible as occurring in these slots A-L in the bottom right-hand corner of the game.

NOTE: that I did not increase PC's max hp to begin the game as I heard some students and Prof. Shaeffer discuss, I just left the initial hp at 100. 

DESIGN(S): The one thing that I did not like about my implementation, is the printout of the 'inspect item' command. Due to the description parsings, and how the newline is displayed, I disliked the
display of this command. However I feel this README correctly describes how to utilize all functions of this code to satisfty the specification.

NOTE: I was trying to implement equipment item color but couldn't get it and I wanted to submit it to you quickly.
NOTE: All update messages regarding indexing of inventory, equipment, or updating the screen such as inspecting, dropping, equipping, or expunging an item take an extra key click to process through the command, I did it this way to provide a conscious user-input element to aid debugging.
