# Modifying Clips And Clip Attributes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Inside the Project Settings, the Camera Raw panel holds parameter groups, one set per camera raw media format that DaVinci Resolve handles. Working through those parameters in the Camera Raw panel lets you supersede the original camera metadata laid down while recording, and tweak every piece of camera raw media across the whole project at once.
- Over in the Inspector, the Image Panel likewise carries the controls for each raw media format DaVinci Resolve recognizes. That lets you target all clips, a handful, or just one for raw debayering.
- On the Color page, the Camera Raw palette gives you a way to dial Camera Raw parameters one clip at a time for the individual clips sitting in the Timeline.
- Should a project lean on Resolve Color Management (RCM) while also relying on Camera Raw formats, the color science supplied by each camera maker drives the debayer or demosaic of every camera raw file toward defined color primaries under linear gamma, keeping all of the source's image data intact and ready for DaVinci Resolve’s color managed image processing pipeline. Because of that, the Camera Raw project settings together with the Camera Raw palette on the Color page go inactive, since RCM now steers the debayering for all camera raw clips, leaving the full image data of the raw file open for conversion into whichever Timeline Color Space you settle on as you grade.

To read up on each of the Camera Raw formats you can tune within DaVinci Resolve, turn to Chapter 7, “Camera Raw Settings.”
