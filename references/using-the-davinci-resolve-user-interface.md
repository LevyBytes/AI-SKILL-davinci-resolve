# Using The Davinci Resolve User Interface (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the DaVinci Resolve User Interface

Here you'll find a tour of the implicit rules and ways of interacting that the DaVinci Resolve graphical user interface (GUI) relies on. Topics covered include the manner in which the buttons on your mouse, pen and tablet, or trackpad get used by the assorted windows and interface widgets, the way commands are spread across the program through the menu bar, contextual menus, and option menus, plus how you work with fields and the rest of the controls. A number of these rules line up with the familiar interface behaviors of your platform's file system and of other media tools, yet a few are particular to DaVinci Resolve, which is why even seasoned users of other software will benefit from a read-through.

### Basic Documentation Terminology

For those completely new to the software, here's a quick note on a few foundational terms this manual uses.

### What Is the “UI” or “GUI”

Throughout these docs, UI is shorthand for “user interface,” and GUI stands for “graphical user interface.” Both point to the windows, screens, and controls through which you do your creative work in DaVinci Resolve. There's no shame in not having known that; this is a far more common question than you'd expect.

### What Is “the Pointer”

Any time you see “the pointer” mentioned here, it means the arrow on your screen that you use for clicking interface elements, whichever device happens to be driving it: a mouse, trackpad, pen and tablet, trackball, or anything else. Given how many distinct ways exist to operate a computer, calling it merely “the mouse” would be misleading.

### About Keyboard Shortcuts

Every keyboard shortcut in this manual is written in the macOS style, using the Command key and the Option key. So that things stay consistent on Windows and Linux, no default shortcut maps to the macOS Control key (you can still bind it yourself when customizing shortcuts). Wherever macOS uses the Option key, Windows and Linux substitute the ALT key, and wherever macOS uses the Command key, those platforms substitute the Control key.

### Customizing the DaVinci Resolve Interface

At a glance the DaVinci Resolve interface might look fairly rigid, but in practice it offers plenty of ways to shape the panels on each page around how you personally work.

### Working Full Screen vs. Within a Floating Window

Based on your preferred workflow, you can run DaVinci Resolve inside a floating window whose title bar lets you resize, reposition, minimize, and run it next to other windows. Alternatively, picking Workspace > Full Screen drops DaVinci Resolve into Full Screen mode, in which the title bar vanishes and the program fills the entire span of your monitor. Someone editing across several apps at once might lean toward the windowed approach. Colorists and mixers often gravitate to Full Screen mode, since it removes the pale title bar that some people find distracting and frees up a sliver of extra space for everything else on screen.

### Panels and Panel Focus

A DaVinci Resolve page is built from several panels. Every panel gathers the controls and readouts tied to one slice of that page's job. Take the partial screenshot below of the upper Media page: the Media Storage panel is for browsing files, the Viewer panel is where you watch video, and the Audio panel shows playback level through a bank of audio meters. Though each panel carries its own set of controls, all of them live inside the one main window of the DaVinci Resolve user interface.

A trio of panels lined up across the Media Page: Media Storage, the Viewer, and the Audio panel Whichever panel you're using takes on “focus”: clicking any item or control inside a panel promotes it to the active panel, and that routes the keyboard shortcuts shared by many panels to whichever one you're currently in. To make the focused panel visible, switch on the “Show focus indicators in the User Interface” checkbox found in the UI Settings panel of the User Preferences. With it enabled, a red line across the top of the active panel marks that it holds focus.

### Showing and Hiding Panels Using the Interface Toolbar

Every DaVinci Resolve page carries an Interface Toolbar stretched across its top edge. The buttons on this toolbar reveal and conceal the various functional panels so you can tackle different jobs:

- Panels that stay hidden by default can be brought up, because the majority of pages hold lots of functional panels that remain tucked away until you call for them.
- Individual panels can be toggled on and off via keyboard shortcuts you assign, giving you instant UI reconfiguration. Use the Keyboard Customization window to map those toggle shortcuts.
- You can swap which panel occupies a given spot in the UI, such as alternating between the Media Pool and Effects in the top-left corner of the Cut or Edit pages.
- Panels you have no use for can be dismissed to open up more room within the ones you're actively working in.

On the Color page, its Interface toolbar is where you tailor that page's controls A right-click anywhere on the UI toolbar surfaces two choices: “Show Icons and Labels” and “Show Icons Only.” Choosing icons only trims the clutter from the UI toolbar. The choices on offer vary from page to page, mirroring what each page is able to do.

The Edit page's UI Toolbar set to icons only, conserving space

### Showing and Hiding Panels in the Workspace Submenu

With this feature you can enable or disable panels by selecting them from the Workspace > Show Panel in Workspace drop-down menu. Which panels are listed, for instance Inspector, Media Pool, Metadata, and so on, hinges on the page you're currently in. As another option, you can give these panels their own keyboard shortcuts.

### Adjusting the Size of Different Panels

To resize neighboring panels, place the pointer on the dividing edge between any two of them and drag, which grows one panel while shrinking the other.

### (Before/After) Resizing UI regions

A handful of panels and palettes will grow larger, shifting some other portion of the UI in the process, when you click a little gray Expand button. As an example, clicking the expand button in the upper-right of the Keyframe Editor on the Color page widens the Keyframe Editor and, to make space, conceals the controls sitting in the middle.

### (Before/After) Expanding the Keyframe Editor

A few of the tall, vertical panels, including the Media Pool, Effects Library, Metadata Editor, and Inspector, can be sized to either half-display-height or full-display-height, letting you add or remove space for their contents or controls on demand. You trigger this with a small button on the UI toolbar that flips between expanding and contracting whichever UI element it governs.

The button for expanding a panel to full height

The button for contracting a panel to half height

The upshot is that the targeted panel either grows or shrinks. In the screenshots that follow, the Inspector of the Edit page appears first in half height mode, leaving the Timeline space to stretch out, and then in full height mode, where the Timeline gets shorter but the Inspector gains the room to display every control.

(Left) A half-height Inspector that frees space for the Timeline, (Right) A full-height Inspector that frees space for its controls

### Using Single- vs. Dual-Monitor Layouts

You move the Media, Edit, Color, and Fairlight pages between single-screen and dual-screen layouts by selecting Workspace > Dual Screen > On. A dual-screen layout puts far more controls in view simultaneously, typically across a wider workspace that helps you handle more clips, more Gallery stills, and the like. You can resize the second display of a dual-screen layout, though you can't rearrange it. Owners of a single ultra-wide monitor can adopt the dual-monitor layout too, and DaVinci Resolve will scale its interface as though two ordinary monitors sat side by side.

### The Edit page in Dual-screen mode

While in Single-screen mode, you decide which monitor presents the DaVinci Resolve UI through Workspace > Primary Display > (Monitor Name). While in Dual-screen mode, the same command swaps what each of the two monitors shows.

### Using the Full Screen Timeline Option in the Edit Page

When you're on the Edit page in Dual-screen mode and want the largest possible timeline for cutting through your program, selecting Workspace > Dual Screen > Full Screen Timeline reveals a layout that devotes one whole screen to a single oversized timeline while parking every other Edit page panel on the second display.

### The Edit page in Dual-screen Timeline mode

### Video Clean Feed (Studio Version Only)

You can now drive a full-screen Viewer onto a second monitor wired straight to your computer. Turn this monitor on by choosing Workspace > Video Clean Feed and then picking your display from the submenu.

### Selecting a monitor for full-screen display

### Saving Custom Screen Layouts

Once you've arranged a specific group of resized panels you expect to reach for repeatedly, you can store it next to any other handy screen layouts you've already kept. Ways to work with custom screen layouts: Storing a custom screen preset: Set up the various DaVinci Resolve pages for whatever you're tackling, then choose Workspace > Layout Presets > Save Layout As Preset. Give it a name in the Save Layout as Preset dialog, then confirm with OK. Recalling one you stored earlier: Choose Workspace > Layout Presets > LAYOUT NAME > Load. As many as five separate presets may be tied to keyboard shortcuts through the Keyboard Customization window (Application > Workspace > Layout Presets). Refreshing a stored preset: Pull the layout you're after from the Workspace > Layout submenu, make your edits, and finish via Choose Workspace > Layout Presets > LAYOUT NAME > Update Preset. Removing one: Choose Workspace > Layout Presets > LAYOUT NAME > Delete Preset. Sending one out so another DaVinci Resolve installation can use it: Choose Workspace > Layout Presets > LAYOUT NAME > Export Preset. Bringing one in: Choose Workspace > Layout Presets > Import Layout as Preset.

### Resetting to the Default Layout

Should the present layout not suit you and you'd rather return to the original, choose Workspace > Reset UI Layout.

### Undocking Specific Panels of the Interface

A number of interface elements have a choice: they can stay docked within their home pages, or they can pop out into their own windows.

### A floating Media Pool window

To float a Media Pool bin in its own window, just right-click the bin and pick Open As a New Window from the contextual menu. Although it looks like you're only revealing that bin's contents, what you actually get is a whole second Media Pool, including the Bin list, Browsing area, and every organizational control the docked Media Pool carries. There's no cap on how many floating Media Pools you keep open. Each one can be dragged onto other monitors and dismissed with a button at the top-left of its title bar. On the Color page, the video scopes give you an exact read on the color and contrast of your clips. Clicking the Video Scope button on the Color page toolbar shows them in their docked spot at the right of the Color page palettes.

The video scope sitting in its docked spot beside the remaining palettes along the lower Color page As an alternative, clicking the expand button at the upper-right of the video scope floats the video scopes into their own window, where you can show all four at once, or any one on its own, on whichever monitor is attached to your workstation.

### Video scopes in a floating window

On top of that, plenty of the dual-screen layouts in DaVinci Resolve include both the Audio Mixer and the video scopes. The scopes aren't confined to the Color page; they show up on the Media and Deliver pages too, for moments when you need an objective look at the video signal, like preparing to capture from tape, scan from film, or set up for output. Within the DaVinci Resolve single screen layout, the scopes can be sent to a second computer display when one exists, and they'll briefly vanish if you switch pages or move to a different application.

### DaVinci Resolve User Interface Conventions

Each chapter goes into the distinctive on-screen controls belonging to its own DaVinci Resolve page, but this section recaps how to operate several of the more widespread controls you'll run into.

### Contextual Menus

Almost every panel across every page offers extra functions through contextual menus that pop up when you right-click the relevant item. In some cases the commands you get differ based on whether you right-click a panel's empty background or land directly on an item like a still or node.

Contextual menus expose additional controls in the Color page Viewer

### Drop-Down Menus

A single click is all it takes to fire most of the buttons and drop-down menus scattered across the toolbars. As one example, a great many panels, palettes, and windows carry an Option menu shown as three horizontal dots (folks tend to call them “three dot menus,” though they're really option menus) that reveal further options or commands tied to what that panel does.

### Option menus

### Mode drop-down

What's more, a lot of panels and palettes (though not every one) carry a “Mode” drop-down in the top-right corner that lets you switch to a different category of function inside that palette. Certain buttons, like transport controls and toolbar icons, show a small downward-pointing arrow when the pointer hovers over them, signaling that a right-click opens checkmark options controlling how those controls behave.

(Left) Hovering on a button to show that it conceals a menu, (Right) Right-clicking that button to surface its options inside a drop-down

### Adjusting Parameters

In general there are several ways to change a numeric parameter.

### Sliders and Dials

Dragging a slider shifts a parameter's value within a defined range. A dial, by contrast, signals that the value can be adjusted without limit in either direction. Sliders tend to suit big, coarse moves on a parameter. The “virtual sliders” covered next are what you reach for when you want finer control.

### Virtual Sliders and Fields

Wherever a number field shows up, it doubles as a “virtual slider”: hover the pointer over it until the “virtual slider cursor” appears, then click and drag rightward to push the value up or leftward to bring it down (white arrows show which way it's heading). As a rule, a field's virtual slider gives you tighter precision than the real slider sitting to its left.

A slider and a dial with their accompanying number fields

### Using virtual sliders

For the majority of numeric fields, a double-click selects the number, letting you key in a replacement and then press Return to lock in the change.

### Editing of Number Field Values Using Arrow Keys

The arrow keys let you hand-edit numeric parameter values, moving around and tweaking individual decimal places inside number fields. To adjust numeric parameters with the arrow keys: 1 Double-click a numeric value in a field to select it, and a highlight surrounds the value. 2 Use the left/right arrows to move the cursor just to the right of whichever decimal value you intend to change. 3 Use the Up/Down arrows to raise or lower the value at that decimal place. 4 When the whole number is selected, the Up/Down arrows act on the minimum value.

Here the cursor sits ready to change the tenths position by means of the Up and Down arrows.

Copy and Pasting of Number Field Values in Virtual Sliders The usual copy and paste operations work for moving any field's value into any other field. To copy and paste a numeric parameter from one field: 1 Right-click the source field and pick copy (Command-C) from the drop-down menu. 2 Right-click the target field and pick paste (Command-V) from the drop-down menu.

### Icons and Buttons

Certain controls take the form of icons and buttons that you merely click to trigger whatever function they stand for. A pair of buttons with icons to illustrate their functionality

### Resetting Parameters

Returning any editable parameter to its default means double-clicking its text label or, where one is present, clicking the reset button. A master reset button, usually sitting in the header above a group of controls, sends every control in that group back to default. The per-parameter reset controls placed to the right of a parameter normally restore just that single parameter. When no reset control is visible, double-clicking the parameter's name ought to do the trick.

### Reset button

### Using a Mouse or Other Input Device

Whenever they're present, Resolve taps all three buttons on a multi-button mouse, or the three buttons offered by other kinds of input devices. This section runs through a short rundown of every way those three mouse buttons get put to work. Left Button The left button is invariably called a click, as in “click the auto select button.” Clicking switches buttons or other controls on and off, makes selections, and hands focus to regions of the Resolve UI so that keyboard shortcuts perform whatever belongs to that panel or interface area. A double-click on the left button typically opens anything that can be opened, like loading a clip from the Media Pool into the Source Viewer. Double-clicking also handles things such as selecting nodes within the Node Editor on the Color page. Right Button People call the right button a right-click, for example “right-click a clip in the Media Pool.” When you right-click some item or zone of the Resolve interface, you normally get a contextual menu holding extra commands tailored to whatever sat under the pointer. Even so, certain UI zones put right-clicking to special use. As one case, while shaping a color adjustment curve inside the Color page's Curve palette, a right-click on any control point deletes it. Middle Button As for the middle button (typically the scroll wheel button, though enabling it may require a trip to the System Preferences Mouse panel), people term its use a middle-click, and what it does shifts depending on where you are.

- On every page, spinning the scroll wheel while the pointer rests inside a viewer zooms the displayed image in and out for closer, more detailed work.
- Across all pages and panels, holding down middle-click and dragging within a panel scrolls that panel's data view along whichever direction you drag.
- On the Color page, hovering over the Thumbnail timeline and rolling up scrolls rightward while rolling down scrolls leftward. Spinning the scroll wheel with the pointer over the Mini-timeline zooms the area currently shown in or out: rolling up zooms out, rolling down zooms in.
- Holding middle-click and dragging inside a viewer drags the image to pan around it, handy once you've zoomed in with the scroll wheel (or scroll behavior) of your mouse.
- Within the Edit page Timeline, a middle-click drag is a fast way to pan around your edit.
- Middle-click also copies a grade in the Thumbnail timeline of the Color page: start by

selecting the clip you want to copy TO (a plain click) and then middle-click the clip or gallery still you want to copy a grade FROM.

- Finally, while drawing a Bezier window in the Color page Viewer with the Window palette, middle-clicking a control point deletes that point.

TIP: When your pointing device offers no third button, look into whether any third-party drivers or utilities exist that can add one for you.

### Mouse, Trackpad, and Tablet Behaviors

Each input device relies on its own set of gestures to set off particular behaviors in DaVinci Resolve. Below is an up-to-date rundown of those gestures alongside the behaviors each one drives.

### Timeline Scroll Behavior

### Standard Mouse Mac Magic Mouse

### Trackpad

### Tablet and Pen

### Scroll timeline vertically

### Scroll timeline horizontally

Zoom timeline width horizontally Offering a zoom that follows wherever the cursor points Switchable on through the User Workspace preferences Zoom timeline track height vertically Handles the Video and Audio section as two separate zooms Drag Timeline with Hand Tool

### Scroll

### Scroll —

### Scroll

Magic Mouse 1 Finger Pan panning along vertical and horizontal axes Magic Mouse 1 Finger Pan panning both up-down and side-to-side —

2 Finger — Pan panning along vertical and horizontal axes 2 Finger — Pan panning both up-down and side-to-side —

—

—

—

Scroll

—

—

### Middle Mouse Button

### Left Button

### Viewer Behavior

### Standard Mouse Mac Magic Mouse

### Trackpad

### Tablet and Pen

### Zoom towards mouse pointer Can change in preferences

### Free Pan

### Pan with Hand Cursor

Tilt Up and Down

— Scroll

### Middle Mouse Button

### Magic Mouse 1 Finger Pan

Middle Mouse Button

— Left Button

—

—

### Scroll

Pinch to Zoom 2 Finger Pan 2 Finger Pan —

### Press and hold the middle pen button

While sliding it side to side across the tablet.

### Press and hold the middle pen button

Raise the pen nib a couple of millimeters off the pad, and moving the pen shifts the frame within the viewer.

### Press and hold the middle pen button

Raise the pen nib a couple of millimeters off the pad, and moving the pen shifts the hand within the viewer.

### Standard Mouse Mac Magic Mouse Trackpad

### Tablet and Pen

Pan Left and Right

—

—

—

### Scroll

Context Menu

— Right Button

### 2 Finger Touch

Right button on the pen.

Gestures employed across common input devices within DaVinci Resolve

### Keyboard Shortcuts

Because most people running DaVinci Resolve are on macOS, every shortcut in this manual follows the macOS style built around the Command key and the Option key. For everyone on other platforms, each shortcut that relies on the macOS Option key maps to the ALT key on Windows and Linux, and each shortcut built on the macOS Command key maps to the Control key on those systems.

TIP: To hold the controls consistent across macOS, Windows, and Linux, no default shortcut is bound to the macOS Control key. You're free to map your own shortcuts onto the Control key, though, which unlocks an entirely fresh set of shortcuts just for your own macOS workflow.

### Undo and Redo in DaVinci Resolve

Wherever you happen to be in DaVinci Resolve, the Undo and Redo commands let you reverse steps or commands you've carried out and then put them back if you reconsider. DaVinci Resolve can roll back the full record of everything you've done since you created or opened a given project. Closing a project clears that project's complete undo history. When you next open the project, its undo history begins fresh from zero.

Since DaVinci Resolve packs so many capabilities into one application, DaVinci Resolve keeps three independent undo “stacks” to help you stay on top of your work.

- A single shared multiple-undo stack spans the Media, Edit and Fairlight pages, so you can step back through edits you made across the Timeline, the Metadata Editor, the Viewers, and the Media Pool.
- On the Fusion page, every clip carries its own undo stack, so you can independently undo edits to each clip's composition.
- On the Color page, every clip likewise has its own undo stack, so you can independently undo edits to each clip's grade.

Across the board, there's no real ceiling on how many steps you can undo (though your memory may impose one of its own). To capitalize on that, three approaches let you roll work back to an earlier project state regardless of the page you're on. For plain one-at-a-time undo or redo of your edits:
