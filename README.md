# Vela AI (auto Attack logIc)
Automates Vela's attack on enemy units, turrets, cores, generators and spawns. Units are automatically repaired near working repair turrets if they are not too far away. After destroying all enemy cores, the logic switches from attack to survival mode. Units will fly to the last enemy unit detected. If there is no enemy left, land around the spawn if there is no lava or water under them. You can manually select the desired type of bombs or place an unassigned one. Also in the arc turret you can tell units where to fly and shoot. The logic was written in [MindCode](https://github.com/cardillan/mindcode), which compiles into [Mindustry Logic](https://mindustrygame.github.io/wiki/logic/0-introduction).

## How to run
The easiest way is to download `vela-ai-scheme.msch` and import it from mindustry's `Schematics` menu. First of all, download the file. To do this, click on it and then click on the download icon on the right.
![Select file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/302faa4a-3e54-4c95-83c4-68d55298aa78)
![Download file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/a3c0c9f8-307a-4b9c-a6e4-c649305f9e58)

Once the file is downloaded, go to Mindustry. Open `Schematics` (in the main window `Database` => `Schematics`), click `Import Schematics`, `Import File` and select the downloaded file. Now you can use this schema in your schematics. 

## Development
The source code file is vela-ai.mnd. Recommend using [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension. The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first. 
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
