This is Version 2.0 of the Unity Universal Culling Fix Mod. I would like to thank Koochyrat for programming this version of the script which directly references openvr_api.dll, eliminating
the need for referencing Valve.VR. This makes the mod much simpler and more universal. I implemented it into a mod and did lots of testing.

**Instructions**

First determine the type of Unity game that you want to patch:

- Go into the root game folder and open the <Game>_Data folder where <Game> is the title of the game. Inside that folder, if you see a folder named "il2cpp_data"
that means you'll need to place UniversalCullFixil2cpp.dll in the Mods folder. The following Il2cpp games are confirmed to work: VRChat, Pistol Whip, The Room VR, and Audica.
This game doesn't work: Until You Fall

- Inside <Game>_Data folder if you see a Managed folder instead, open that. If you see a long list of files with UnityEngine.CoreModule.dll in there, then it is a Mono 4 Unity game.
That means you'll need to place UniversalCullFixMono4.dll in the Mods folder. The following Mono4 games are confirmed to work: Blade & Sorcery, Republique VR, Iron Wolf VR, Arizona Sunshine, Superhot VR, and Thief Simulator VR.
This game doesn't work: Virtual Battlegrounds

- If instead you see very few files inside the Managed folder and you only see UnityEngine.dll file, then it is a Mono 3.5 Unity game. That means you'll need to place
UniversalCullFixMono3.5.dll in the mods folder. The following Mono3.5 games are confirmed to work: H3VR, Shadows Legends, and Sairento VR. This game doesn't work: The Forest

In rare cases, a game that look like it is Mono 4 may actually be Mono 3.5. If you see a TargetFrameworkVersioning error in the MelonLoader command line, then try another version. 

Please let me know if you encounter any bugs or issues!
