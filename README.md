# BoneworksCullingFix
This is a MelonLoader mod for fixing the culling/objects popping in & out issue that occurs in the peripheral vision on wide FOV headsets such as Pimax and the StarVR One. It works with Boneworks and should work with other Unity games with slight code modifications. Credit to KoochyRat for the original code I used in making this mod: https://github.com/koochyrat/SteamVRFrustumAdjust

How to install the mod: 
1. Go to https://melonwiki.xyz/ and install MelonLoader onto the Unity game you want to mod. 
2. Run the game once and then close it. 
3. Go into your game directory and place CullFix.dll inside the Mods folder
4. Run the game and enjoy a culling free experience! 

This mod was made for Boneworks which uses the class ValveCamera, the Camera class may be named differently in other Unity games.

Here are the steps to patch other Unity games that don't use the ValveCamera class: 
1. Download the visual studio source code project template
2. Download Visual Studio 2019 and add the .Net framework component located near the bottom of the list of components. For more information on project type see: https://melonwiki.xyz/#/modders/quickstart
3. In Visual Studio go to File -> New -> Create project from existing code. Select the project template and a wizard will pop up letting you name the project.
4. Download the latest dnspy here: https://github.com/0xd4d/dnSpy/releases
5. Use Dnspy to open Assembly-CSharp.dll file from MelonLoader/Managed folder inside your game directory
6. In dnspy search for "camera OnPreCull" or just "OnPreCull"
7. Look through each result finding a class that contains all three methods that are needed: "OnEnable", "OnDisable", and "OnPreCull" 
8. Take note of the full class name listed in search results (that includes the namespace). 
9. Replace all references of ValveCamera in the code to the class name you found previously.
10. Take note of the methods you want to patch and whether they are public/private or static. If they are public use BindingFlags.Public  If private or protected use BindingFlags.NonPublic and if method is static use BindingFlags.Static instead of BindingFlags.Instance (Not using the appropriate binding flags will result in a Nullreference exception error when loading the mod)
11. Remove the old Assembly-CSharp.dll reference in Visual Studio and add a reference to the one in the game you want to patch.
12. Build the project and place your new CullFix.dll into the Mods folder of the game you want to fix.

If you do patch the culling in another Unity game, please share the dll and class name to save other people time. I'm currently working with Koochyrat on trying to make the mod universal for all Unity games.
