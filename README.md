# JsMacros script template

Trying to create more complex [JsMacros](https://www.curseforge.com/minecraft/mc-mods/jsmacros) scripts in typescript/javascript?  
This is a template for that purpose.  

- Create a repo from the template and clone it (or just download the ZIP of this repo)
- Open the repo folder with VSCode
- Open a terminal (in vscode: Terminal->New Terminal) in the repo folder and run `npm i`
- Run `npm run watch` and leave that command running in the background. It will automatically re-process your code files when anything changes.
- Your script outputs are now located in the `dist` folder.
- To load the dist files into JsMacros without having to move them into your minecraft folder each time, you can use this powershell command:
- `New-Item -ItemType SymbolicLink -Path "C:\Path\To\Your\.minecraft\config\jsMacros\Macros\dist" -Target "C:\Path\To\Your\JsMacros-script-template\dist"`
- You should now have a `dist` folder in your JsMacros file browser

A short overview of the directory structure:
- `dist/`: Contains the generated files to load in JsMacros, don't make manual changes to the files in this folder.
- `src/`: Contains all source code of your JsMacros projects
  - `scripts/`: Contains the actual script files that will be used as entry points, meaning you intend to load them directly ingame.
  - `lib/`: Contains code that your scripts need to run, but that isn't a macro by itself

If you create a folder in `scripts/` and put a `ts`/`js` file with the same name as the folder into it (like `scripts/TreeFarmer/TreeFarmer.ts`), only that file will be treated as an entry point. That way you can organize files without dumping everything that's not a JsMacros script into `lib/`.

The repo contains a bunch of existing lib and script files from aMelonRind's script repository. You can keep them and reuse the lib files / use them as reference, or just delete them all. Many of the `lib` files are quite useful though!