# Vela Attack Logic
Units automatically repair near the nearest active repair turret if it’s not too far away. They will approach to the nearest enemy core if there are no dangerous enemy units or turrets around them. If a unit can’t land to attack, it switches to kamikaze mode, flying straight at the enemy until it lands or explodes. You can select the desired bomb type in the sorter or place an unassigned one. You can also direct units to attack automatically repairing them

## How to use
The easiest way is to download [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) and import it from mindustry's `Schematics` menu.

1. Open [vela-ai-scheme.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/vela-ai-scheme.msch) file
2. Click the Download button (the icon on the top right):

![Download-file](https://github.com/limonovthesecond2/vela-ai/assets/118817903/0484e3a3-e2e8-4db2-988e-4a21613f59d6)

3. Launch **Mindustry**
4. Open **Database** → **Schematics**
5. Click **Import Schematics** → **Import File**, and select the downloaded `.msch` file

> [!NOTE]
> There’s also a version optimized for the *Eradication Rapid* server: [vela-ai-scheme-rapid.msch](https://github.com/limonovthesecond2/vela-ai/blob/main/rapid_version/vela-ai-scheme-rapid.msch)

## Development
The source code is written in [MindCode](https://github.com/cardillan/mindcode), so, please, read the [documentation](https://github.com/cardillan/mindcode/blob/main/doc/syntax/SYNTAX.markdown) first if you are not already familiar with it. For syntax highlighting, you can use [VSCode](https://code.visualstudio.com/) with [Mindcode](https://marketplace.visualstudio.com/items?itemName=TomSchi.mindcode) extension.

The scheme consists of 2 cloned **Main** hyperprocessors and 1 **Message** microprocessor.

Their purpose:
- **Main:** All logic related to units, including repair, bomb loading, attack, approach etc
- **Message:** Writes messages, defines the item in the unloader/item source and enables the logic if the player controls the arc turret
