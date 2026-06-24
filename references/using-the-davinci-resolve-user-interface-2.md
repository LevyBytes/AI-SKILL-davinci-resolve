# Using The Davinci Resolve User Interface (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Pick Edit > Undo (Command-Z) to reverse whatever you changed most recently.
- Pick Edit > Redo (Shift-Command-Z) to step forward to the change you just reversed.

Reverting many edits in one move is also possible through the History submenu and its window. As of this writing, that multi-step capability is limited to the Media, Cut, Edit, and Fairlight pages. Here is how stepping backward or forward via that submenu works: 1 Open the Edit > History submenu, which lists (up to) the twenty most recent actions you’ve taken. 2 Pick any entry to roll the project back to that moment. Your latest action sits at the top of the listing, and whatever you just did carries a check mark beside it. Entries you’ve reversed yet could still reapply stay visible in this menu, letting you gauge your remaining options. That said, once you reverse a batch of edits and then introduce a fresh change, further undo is no longer available and those reversed entries vanish from the menu. The instant you pick a step to revert to, the menu dismisses and the project refreshes to reflect its present condition.

The History submenu, the tool for rolling back multiple steps in a single action

Stepping backward or forward by way of the separate Undo window goes like this: 1 Choose Edit > History > Open History Window. Once the History dialog opens, pick an entry from the listing to revert the project to that moment. In contrast to the menu, here your latest action is shown at the foot of the listing. Picking a change in this view dims the changes that remain reapplicable, while the project refreshes to reflect its present condition. 2 After you finish, shut the History window.

The Undo History window, where you can scan through the full undo stack on hand for the page in view
