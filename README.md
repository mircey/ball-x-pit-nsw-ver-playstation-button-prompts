# BALL x PIT (Nintendo Switch) PlayStation button prompts
this is a mod for the Nintendo Switch Release of BALL x PIT, which overwrites the standard Nintendo Switch button prompts with PlayStation button prompts.

<!--<img width="1920" height="1080" alt="Screenshot_20260311-015539" src="https://github.com/user-attachments/assets/026667df-98e8-4990-ae96-5d947e2d2bbe" />-->
<img width="1920" height="1080" alt="Screenshot_20260311-145808" src="https://github.com/user-attachments/assets/701aa03b-6e05-4496-98f0-938da74116c6" />


## features
- DualShock face buttons
- DualShock shoulder buttons
- DualShock triggers
- DualSense-inspired dpad

## compatibility
currently, only the BALL x PIT base game (version `1.251`) is supported. the mod has been tested with [Eden](https://git.eden-emu.dev/eden-emu/eden) `0.1.1` on android.

## how to install
first, download the latest release zip [here](https://github.com/mircey/ball-x-pit-nsw-ver-playstation-button-prompts/releases/tag/2).

### on pc
1. open [Eden](https://git.eden-emu.dev/eden-emu/eden)
2. rclick BALL x PIT in the games list
3. click Open Mod Data Location
4. extract the content of the release zip to the folder, that just opened

this is how the final folder structure should look like:
```
eden
└─load
  └─010086A022444000
    └─PlayStation prompts
      └─romfs
        └─Data
          └─resources.assets
```

### on android
1. either extract the release zip on your pc and move it to your android device via USB, or unzip it on the android device directly using [ZArchiver](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver&hl=en)
2. open [Eden](https://git.eden-emu.dev/eden-emu/eden)
3. long press BALL x PIT in the games list
4. tap Add-ons
5. tap + Install
6. choose Mods and cheats
7. select the extracted `PlayStation prompts`, which has the `romfs` folder within it.

## motivation
i love the PlayStation aesthetic, so i modded my Odin 2 Mini emulation handheld console with [SakuraRetroModdings custom PlayStation buttons](https://www.etsy.com/de-en/listing/4351698824/odin-2-mini-black-playstation-ps-psx?ls=s&ga_order=most_relevant&ga_search_type=all&ga_view_type=gallery&ga_search_query=buttons+sakura+retro+modding&ref=sr_gallery-1-14&sts=1&content_source=38afd973-31fd-4964-a630-0a43001e9681%253ALTbda6958b38dad150fa3e02f9a39de8eba9379783&organic_search_click=1&logging_key=38afd973-31fd-4964-a630-0a43001e9681%3ALTbda6958b38dad150fa3e02f9a39de8eba9379783)! i prefer to play all my indie games that have switch releases through Eden, for performance and efficiency reasons. everything about this works perfectly, except for the games button prompts; wouldnt it just be lovely to have "native" PlayStation button prompts show up in games on my DIY modern PS Vita?

## documentation
i am not planning on doing an xbox version anytime soon, although there probably are a few people looking for one. but dont fret!! you can do it yourself! i documented everything i did:
1. open [Eden](https://git.eden-emu.dev/eden-emu/eden)
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

## credits
thanks to [Kenny Sun and Friends](https://kennysun.com/) for bundling the official PS4 button prompts in the switch release!
