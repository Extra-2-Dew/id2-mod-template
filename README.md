# Ittle Dew 2 Mod Template

This is a template for building Ittle Dew 2 mods. It has all the necessary files for the mod to run, so requires minimal effort to get a new mod up and running!

## How to use template
1. Go to the [create a new repo](https://github.com/new) page
2. Select the `Extra-2-Dew/id2-mod-template` template in the "Repository template" dropdown
    a. You don't need to check "Include all branches"
3. Fill out the remaining info and create the repo. This creates a new repo with all the necessary mod files
4. Clone your new repo
5. In your cloned repo, open the `ID2ModTemplate.sln` file in Visual Studio 2022
6. Edit the `ID2ModTemplate.csproj` file and change stuff like assembly name, description, etc. to fit your mod
7. Add a new file to the solution named `[AssemblyName].csproj.user`. This file will contain user-specific path variables used for the project.
8. In this `csproj.user` file, add this boilerplate:
```
    <Project>
	<PropertyGroup>
		<GameInstallPath>PATH\TO\YOUR\GAME\INSTALL</GameInstallPath>
	</PropertyGroup>
</Project>
```
9. Replace `PATH\TO\YOUR\GAME\INSTALL` with the path to your root Ittle Dew 2 directory (the one with the executable in it)
10. Restore packages. In the terminal, run the command `dotnet restore` to install any necessary packages
11. Build the solution. Either run the command `dotnet build` in the terminal or click `Build -> Build Solution`
    a. This will automatically copy all build files to the newly created mod folder and the mod will be added to the game!