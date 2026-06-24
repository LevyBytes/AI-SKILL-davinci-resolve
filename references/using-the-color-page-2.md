# Using The Color Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- On the Fusion page, every clip keeps a separate undo stack, letting you roll back compositing tweaks for that one clip on its own.
- On the Color page, each clip likewise carries its own undo stack, so grade changes can be reversed clip by clip without affecting the others.

For all of these, the count of steps you can step back through is effectively unbounded (though your own memory of them might run out first). To make the most of that, three different methods let you walk a project back to an earlier state regardless of which page you happen to be on. If you just want to step backward or forward one change at a time:

- Choose Edit > Undo (Command-Z) to undo the previous change.
- Choose Edit > Redo (Shift-Command-Z) to redo to the next change.
