# Vela Attack logIc
Units are automatically repaired near the closest working repair turret, if it is not too far away. They will approach to the nearest enemy core if there are no dangerous enemy units or turrets around them. If a unit is unable to land and thus open fire, it goes into 'kamikaze' mode. This means that it will move straight towards the enemy and will not repair until it lands or explodes over the enemy. You can select the desired bomb type in the sorter or place an unassigned one. You can also tell units where to fly and shoot from the arc turret if they are not busy attacking the enemy.

## How to use
The easiest way is to download [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) and import it from mindustry's `Schematics` menu.

- Open [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) file
- Download the file. To do this, click on the download icon on the right

![Download-file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/0484e3a3-e2e8-4db2-988e-4a21613f59d6)

Once the file is downloaded, go to Mindustry. Open `Schematics` (from the main window `Database` then `Schematics`), click `Import Schematics`, `Import File` and select the downloaded file. Now you can use this schematic from your `Schematics` menu.

> [!NOTE]
> There is also a scheme for the Eradication Rapid server named [vela-ai-scheme-rapid.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme-rapid.msch)

## Development
The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first if you are not already familiar with it. For syntax highlighting, you can use [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension.

The scheme consists of 2 cloned `Main` hyperprocessors and 1 `Message` microprocessor.

Their purpose:
- `Main`: All logic related to units, including repair, bomb loading, attack, approach etc
- `Message`: Writes messages, defines the item in the unloader/item source and enables the logic if the player controls the arc turret

### How to paste changed code into the game
- Copy all strings of your Mindcode (.mnd) file
- Go to MindCode Online Compiler: [http://mindcode.herokuapp.com/](http://mindcode.herokuapp.com/?s=clean)
- Paste the code on the left
- Click the `Compile` button
- If there are no errors and warnings, copy compiled code from the right
- Go to your processor in Mindustry
- Click in the processor `Edit`
- Click `Import from clipboard`
