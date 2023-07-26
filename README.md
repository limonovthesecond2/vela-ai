# Vela AI (Auto attack logIc)
[MindCode](https://github.com/cardillan/mindcode) logic written to compile into [Mindustry](https://github.com/Anuken/Mindustry) Logic. Automate Vela attacks on enemy units, turrets, cores, generators, spawns. Units are automatically healed at near powered repair turrets. Automatically changes the priority target when the selected target is destroyed or captured. All units, when there is no enemy nearby, move towards 1 target at a time. You can manually control the approach point in the arc tower and select the item taken from the vault.

## How to run
The easiest way is to download `vela-ai-scheme.msch` and import it from mindustry's `Schematics` menu. First of all, download the file. To do this, click on it and then click on the download icon on the right.
![Select file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/302faa4a-3e54-4c95-83c4-68d55298aa78)
![Download file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/a3c0c9f8-307a-4b9c-a6e4-c649305f9e58)

Once the file is downloaded, go to Mindustry. Open `Schematics` (in the main window `Database` => `Schematics`), click `Import Schematics`, `Import File` and select the downloaded file. Now you can use this schema in your schematics. 

## Development
Recommend using [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension 
The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first. 
The code is divided between several processors with 3 line comments:
```
//
// Main Processor
//

Main Processor code

//
// Cell Processor
//

Cell Processor code

//
// Message Processor
//

Message Processor code
```

## Compiling
- After making changes in the code of a particular processor, select all the code of this processor.
- Go to MindCode Online Compiler: [http://mindcode.herokuapp.com/](http://mindcode.herokuapp.com/?s=clean)
- Paste the code on the left
- Click the `Compile` button
- If there are no errors, copy compiled code from the right
- Go to your processor in Mindustry
- Click in the processor `Edit`
- Click `Import from clipboard`
