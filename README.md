# Universal Unity Culling Fix

UPDATE: Version 2.0.1 is out now! The process has been made a lot simpler and even more universal!

This is a MelonLoader mod for fixing the culling/objects popping in & out issue that occurs in the peripheral vision on wide FOV headsets such as Pimax and the StarVR One. There are different versions of the mod depending on the type of Unity game, so far Boneworks, Pistol Whip, The Room VR, Audica, Blade & Sorcery, Republique VR, Iron Wolf VR, Arizona Sunshine, Superhot VR, Thief Simulator VR, VTOL VR, H3VR, Shadows Legends VR, Virtual Battlegrounds, and Sairento VR are confirmed to work. Any other Unity game should work too unless it's a unique case. 

Credit to KoochyRat for the original code I used in making this mod: https://github.com/koochyrat/SteamVRFrustumAdjust

How to install the mod: 
1. Go to https://melonwiki.xyz/ and install MelonLoader onto the Unity game you want to mod. 
2. Go into your game directory and place the correct .dll file inside the Mods folder
3. Run the game and enjoy a culling free experience! 

If none of the current .dll files work for a particular Unity game, you can patch it yourself with some easy code modification: 
**These are instructions for Version 1 only. Some of it still applies to Version 2 though** 

1. Download the visual studio source code project template called UniversalCullFixProjV1.zip from Version1 Folder.
2. Download Visual Studio 2019 and add the .Net framework component located near the bottom of the list of components. For more information on project type see: https://melonwiki.xyz/#/modders/quickstart
3. In Visual Studio go to File -> New -> Create project from existing code. Select the project template and a wizard will pop up letting you name the project.
4. Download the latest dnspy here: https://github.com/0xd4d/dnSpy/releases
5. Use Dnspy to open the following files Assembly-CSharp.dll, Assembly-CSharp-firstpass.dll, and SteamVR.dll (if it exists) from MelonLoader/Managed folder or Game_Data/Managed folder.
6. In dnspy search for "CVRSystem". Double click on any search result with Valve.VR.CVRSystem and on the left hand pane DNSpy will skip to the class name. Scroll up and take note of the parent .dll file it is connected to. Click on the dll and you will see some commented metadata information. For example: // Runtime: .NET Framework 3.5
7. In the project, remove the old Assembly-CSharp.dll, Assembly-CSharp-firstpass.dll, and SteamVR.dll references in Visual Studio and add references for those files from the game you want to fix. 
8. Go to project properties and under .Net framework select 3.5 if that is what it showed in DNspy. Select .Net framework 4.7.2 if DNspy showed .Net framework 4.0 or higher.
9. Build the project and place your new .dll into the Mods folder of the game you want to fix.
10. If you do patch the culling in a particular Unity game, please share the .dll with me and I'll add it to the list here.
