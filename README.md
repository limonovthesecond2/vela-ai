# Vela AI (auto Attack logIc)
Units are automatically repaired near the closest working repair turret if their health is below 50% and the repair turret is not too far away. Repaired up to 90%. Units will approach to the closest enemy core if there are no enemy units/turrets/cores/generators around. If there are no enemy cores left, the logic switches from attack mode to survival mode. Units will fly to the last enemy unit detected. If there are no enemies left, land around the enemy spawn if there is no lava or water underneath them. You can select the desired type of bombs in the sorter or place an unassigned one. You can tell units where to fly and shoot from the arc turret if they are idle. Simply enter this turret to take control of them.

## How to run
The easiest way is to download `vela-ai-scheme.msch` and import it from mindustry's `Schematics` menu.

- Open [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) file
- Download the file. To do this, click on the download icon on the right

![Download-file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/0484e3a3-e2e8-4db2-988e-4a21613f59d6)

Once the file is downloaded, go to Mindustry. Open `Schematics` (from the main window `Database` then `Schematics`), click `Import Schematics`, `Import File` and select the downloaded file. Now you can use this schematic from your `Schematics`.

## Development
The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first if you are not already familiar with it. For syntax highlighting, you can use [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension.

The scheme consists of 3 types of processors: `Main`, `Cell` and `Message`. There are 2 `Main` hyperprocessors. The `Cell` is the microprocessor closest to the cell. The `Message` is another microprocessor.

Their purpose:
- `Main`: The most essential unit logics including repair, attack, approach etc. Uses variables from the cell
- `Cell`: Calculates variables and writes them to the cell. Defines attack/idle/survival mode
- `Message`: Writes messages and defines the item at the unloader/item source

You may notice a lot of "unnecessary" variable declarations like
```
items = @unit.totalItems
unitCap = @unit.itemCapacity
if items < unitCap
```
instead they can be replaced with
```
if @unit.totalItems < @unit.itemCapacity
```
However, in the compiled code you will then notice several unnamed __temp* variables. It is not very easy to track which one is responsible for what during debugging. Therefore, all possible variables are declared to make debugging easier, since this does not affect performance in any way.

### Compilation after code changes
- Copy all changed code of the processor
- Go to MindCode Online Compiler: [http://mindcode.herokuapp.com/](http://mindcode.herokuapp.com/?s=clean)
- Paste the code on the left
- Click the `Compile` button
- If there are no errors and warnings, copy compiled code from the right
- Go to your processor in Mindustry
- Click in the processor `Edit`
- Click `Import from clipboard`
