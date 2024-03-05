# Vela Attack logIc
Units are automatically repaired near the closest working repair turret, if it is not too far away. They will approach to the nearest enemy core if there are no enemy units with max health more than 600, turrets, cores or generators around them. If a unit is unable to land and open fire on an enemy building, it goes into 'kamikaze' mode. This means that it will not repair until it lands or explodes above an enemy. You can select the desired type of bombs in the sorter or place an unassigned one. Also, you can tell units where to fly and shoot from the arc turret if they are idle. Simply enter this turret to take control of them.

## How to run
The easiest way is to download `vela-ai-scheme.msch` and import it from mindustry's `Schematics` menu.

- Open [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) file
- Download the file. To do this, click on the download icon on the right

![Download-file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/0484e3a3-e2e8-4db2-988e-4a21613f59d6)

Once the file is downloaded, go to Mindustry. Open `Schematics` (from the main window `Database` then `Schematics`), click `Import Schematics`, `Import File` and select the downloaded file. Now you can use this schematic from your `Schematics`.

> [!NOTE]
> There is also a scheme for the Eradication Rapid server named [vela-ai-scheme-rapid.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme-rapid.msch)

## Development
The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first if you are not already familiar with it. For syntax highlighting, you can use [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension.

The scheme consists of 2 `Main` hyperprocessors and 1 `Message` microprocessor.

Their purpose:
- `Main`: All logic related to units, including repair, bomb loading, attack, approach etc
- `Message`: Writes messages, defines the item in the unloader/item source and enables the switch if the player controls the arc turret

You may notice a lot of "unnecessary" variable declarations like
```
arcx = arc1.shootX
arcy = arc1.shootY
isNear = within(arcx, arcy, arcRange)
```
instead they can be replaced with
```
isNear = within(arc1.shootX, arc1.shootY, arcRange)
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
