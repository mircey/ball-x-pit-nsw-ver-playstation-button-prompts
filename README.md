# ball-x-pit-nsw-ver-playstation-button-prompts
a mod for the Nintendo Switch Release of BALL x PIT, that changes the standard Nintendo Switch button prompts to PlayStation button prompts.



## changes
- PS4 face buttons and shoulder buttons
- slightly modified PS4 triggers
- DualSense dpad that i drew from scratch

## motivation
i love the PlayStation aesthetic, so i modded my Odin 2 Mini emulation handheld console with SakuraRetroModdings custom PlayStation buttons! i prefer to play all my indie games that have switch releases through Eden, for performance and efficiency reasons. everything about this works perfectly, except for the games button prompts; wouldnt it just be lovely to have "native" PlayStation buttons in games on my DIY modern PS Vita?

## documentation
i am not planning on doing an xbox version anytime soon, although there probably are a lot of people looking for one. but dont fret!! you can do it yourself! i documented everything i did:
1. open Eden
2. rclick BALL x PIT->Dump RomFS->Dump RomFS
3. open [AssetStudioMod](https://github.com/aelurum/AssetStudio)
4. File->Load Folder
5. select the `010086A022444000\romfs\Data` folder that Eden dumped for you
6. click the Asset List tab
7. Filter Type->Texture 2D
8. search for `controller_btns_outlined`
9. select the single result
10. Export->Selected Assets and choose a destination folder
11. open `controller_btns_outlined.png` that AssetStudioMod exported for you in any image editing software
12. copy the ps4 face button icons and overlay them over the switch face button icons
13. copy the ps4 L1 and R1 button icons and overlay them over the switch L and R button icons
14. copy the ps4 L2 and R2 trigger icons, modify them to be 1 pixel shorter, and overlay them over the switch ZL and ZR button icons
15. draw dualsense-inspired dpad icons that fit the switch dpad icon dimensions from scratch, using google images for `dualsense dpad button` as reference
16. i did not bother with overlaying the ps4 start and share button icons over the switch + and - buttons, because their rects in the atlas dont seem to match nicely at all
17. save your modified `controller_btns_outlined.png` to somewhere as RGBA32
    - in photoshop: File->Export as...
    - Format: PNG
    - check Transparency
    - uncheck Smaller File (8-bit)
    - uncheck Convert to sRGB
18. open [UABEA](https://github.com/nesrak1/UABEA)
19. File->Open
20. select `010086A022444000\romfs\Data\resources.assets`
21. View->Search by name
22. enter `controller_btns_outlined` and hit Ok
23. on the right, click Plugins
24. click Edit texture
25. click Load
26. select your modified `controller_btns_outlined.png`
27. click Save
28. in your file explorer, create the mods folder structure: `playstation buttons\romfs\Data\`
29. tab back into UABEA
30. File->Save As...
31. choose ``playstation buttons\romfs\Data\resources.assets` for the save location
32. test by copying `playstation buttons` into `%appdata%\eden\load\010086A022444000\` and launching the game
33. 

## credits
thanks to [Kenny Sun and Friends](https://kennysun.com/) for bundling the official PS4 button prompts in the switch release!
