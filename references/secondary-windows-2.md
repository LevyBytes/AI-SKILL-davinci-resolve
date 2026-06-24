# Secondary Windows (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Windows can also serve as a “garbage matte” whenever you pair one with a qualifier. The default behavior pairs a window with a qualifier so that a key emerges solely in the region where the two overlap. That arrangement gives you an easy way to drop troublesome areas of a key that resist removal no matter how much you tweak the qualifier controls. Take the qualification below, meant to single out the woman’s face: it sweeps in some background wood and sky of a similar hue as well. Rather than tearing your hair out trying to chase down those stray parts of the key by reworking a qualification that already nails the skin tones beautifully, you can drop a window over her face instead, cutting away anything beyond the window's edge and making the whole task far less painful.

### A qualified image with highlight on

Should she shift position, you need only track the window so it keeps pace. For straightforward tracking refer to Chapter 140, “Motion Tracking Windows.”

### Now with additional Power Window isolation

Beyond that, the window’s Invert control flips the logic, removing every qualified piece of the key that falls inside the window while keeping every qualified piece that lies outside it. Should you require qualifier/window setups more elaborate than this, layer in extra windows, or route several qualifiers and windows through the Key Mixer node, see Chapter 146, “Combining Keys and Using Mattes.”
