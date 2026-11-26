# ImperatorArmyAi

A custom `objective_independent` AI objective with twelve weighted priorities, so armies handed
to the AI defend the places that matter.

**Game:** Imperator: Rome 2.0.5

## What it changes

A single file, `common/ai_objectives/objective_independent.txt`, redefining the
`objective_independent` unit objective (used when the player delegates armies). It sets
`interface_priority = 100`, `mode = none`, and a `weight` block that scores every province in
the unit's scope; more negative means more attractive.

| # | Priority | Weight |
| --- | --- | --- |
| 1 | defend the capital (enemies in or adjacent) | −1,000,000 |
| 2 | defend national territory | −800,000 |
| 3 | attack nearby enemy armies | −500,000 |
| 4 | siege nearby enemy territory | −300,000 |
| 5 | siege the enemy capital | −400,000 |
| 6 | attack resource-rich enemy provinces | −200,000 |
| 7 | siege distant enemy provinces | −100,000 |
| 8 | reinforce borders | smaller negative weight |
| 9 | garrison interior provinces | smaller negative weight |
| 10 | reinforce the capital when it is safe | smaller negative weight |
| 11 | nearby neutral provinces | smallest negative weight |
| 12 | no preferred target | fallback |

## Notes

- Weights are fixed-point integers: keep totals well below the 2,000,000 overflow the vanilla
  comment warns about.
- Comments inside the file are in Spanish; the script itself is plain Paradox script.
- Replaces the vanilla objective file, so it conflicts with any mod shipping the same path.

## Installation

Copy the folder into the game's user mod directory and enable it in the Paradox launcher:

```
%USERPROFILE%\Documents\Paradox Interactive\Imperator\mod\<FolderName>\
```

`descriptor.mod` must stay at the root of the folder.

## License

Released under the MIT License (see `LICENSE`). Game assets, vanilla script files and trademarks
remain the property of their respective owners; only the changes made here are MIT.
