# Ittle Dew 2 Mod Template

This is a template for building Ittle Dew 2 mods. It has all the necessary files for the mod to run, so requires minimal effort to get a new mod up and running!

## How to use Template
1. Go to the [create a new repo](https://github.com/new) page
2. Select the `Extra-2-Dew/id2-mod-template` template in the "Repository template" dropdown
    a. You don't need to check "Include all branches"
3. Fill out the remaining info and create the repo. This creates a new repo with all the necessary mod files
4. Clone your new repo
5. In your cloned repo, open the `ID2ModTemplate.sln` file in Visual Studio 2022
6. Add a new file to the solution named `[AssemblyName].csproj.user`. This file will contain user-specific path variables used for the project.
7. In this `csproj.user` file, add this boilerplate:
```
    <Project>
	<PropertyGroup>
		<GameInstallPath>PATH\TO\YOUR\GAME\INSTALL</GameInstallPath>
	</PropertyGroup>
</Project>
```
8. Replace `PATH\TO\YOUR\GAME\INSTALL` with the path to your root Ittle Dew 2 directory (the one with the executable in it)
9. Restore packages. In the terminal, run the command `dotnet restore` to install any necessary packages
10. Build the solution. Either run the command `dotnet build` in the terminal or click `Build -> Build Solution`
    a. This will automatically copy all build files to the newly created mod folder and the mod will be added to the game!

## Explanation of Files
- `manifest.json` contains the data used by (the future) mod manager, such as mod name, description, thumbnail, etc.
- `default-config.json` contains any options your mod should have by default. If not empty, a `config.json` will be added to mod folder on first launch of the game that will have these default options in it
- `thumbnail.png` is the thumbnail used to represent your mod. It will be displayed in (the future) mod manager
- `NuGet.config` is necessary for BepInEx packages
- `[AssemblyName].csproj.user` contains user-specific path variables used for the project
- `Plugin.cs` is the initialization class. BepInEx will first run this class to initialize your mod

## Configuring Your Mod
- Edit the `ID2ModTemplate.csproj` file and change the AssemblyName property to the name of your mod. This will automatically rename the `ID2ModTemplate.csproj` file (and the user file, if you created that already)
- Edit the `manfiest.json` to fit your mod
- Replace the `thumbnail.png` with a thumbnail that fits your mod
- Edit `default.config.json` to add any options your mod will use. If no options are needed, you can leave this blank
- Edit or delete this `README.md`. It's strongly recommended to use a README for any mod you make to explain how it works

## Conventions
- Keep all code files contained within the `Code` folder
- The `Plugin` class should never be renamed. This is BepInEx convention. This is the class that runs first when mod is initialized
    - Use the `Plugin` class only for initialization stuff