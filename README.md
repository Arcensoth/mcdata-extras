# mcdata-extras
Additional handwritten data to go along with Minecraft's generated data.

## Properties
### `repeatable`
Boolean `true`/`false`. Whether the argument can be repeated multiple times in the same selector. For example, `tag=a,tag=b` to select entities with both tags `a` and `b`.

### `negatable`
Boolean `true`/`false`. Whether the argument can be negated. For example, `tag=!c` to select entities *without* the tag `c`. Note that negatable arguments are repeatable in their negated form even if their positive form is not repeatable.

### `nullable`
Boolean `true`/`false`. Whether the argument can be specified but empty. For example `team=` to select entities not on any team, `name=` for [entities without a name](https://i.imgur.com/PtmHGa1.png), and similarly `tag=` for [entities without any tags](https://i.imgur.com/ptycRFS.png).

## Parsers
These are custom parsers under `mcdata_extras` as to not pollute the `minecraft` and `brigadier` namespaces present in the generated `commands.json`. Following are explanations of their intended implementation.

### `mcdata_extras:advancement_map`
The advancement dictionary syntax used to specify which advancements - and, optionally, their criteria - a player has obtained.

```
advancements={minecraft:story/smelt_iron=true}
advancements={minecraft:story/obtain_armor={iron_helmet=true}}
```

The advancement name itself is a `resource_location`, followed by `=`, and then either a criteria map or a boolean `true`/`false`. Each key-value pair is separated by a comma `,`.

The criteria map follows a similar format, except that the criteria name is a `word` and the values are limited to boolean `true`/`false`.

Note that some cases of vanilla criteria are actually [invalid in-game](https://i.imgur.com/RAeBk27.png):

```
advancements={minecraft:adventure/adventuring_time={minecraft:swamp=true}}
```

[MC-139908] addresses this issue in more detail.

### `mcdata_extras:choice`
TODO

### `mcdata_extras:double_range`
TODO

### `mcdata_extras:entity_tag`
TODO

### `mcdata_extras:positive_integer`
TODO

### `mcdata_extras:score_map`
TODO

### `mcdata_extras:team`
TODO

### `mcdata_extras:quotable_string`
TODO

## Relevant bugs
- [MC-121692]: Many commands break on unquoted special characters, quoting support inconsistent
- [MC-132806]: You cannot grant/revoke specific advancement criteria because of a colon in its name
- [MC-139908]: Criterion names in advancement selector argument limited to unquoted strings

[MC-121692]: https://bugs.mojang.com/browse/MC-121692
[MC-132806]: https://bugs.mojang.com/browse/MC-132806
[MC-139908]: https://bugs.mojang.com/browse/MC-139908
