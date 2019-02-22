# mcdata-extras
Additional handwritten data to go along with Minecraft's generated data.

## Properties
### `repeatable`
Boolean `true`/`false`. Whether the argument can be repeated multiple times in the same selector. For example, `tag=a,tag=b` to select entities with both tags `a` and `b`.

### `negatable`
Boolean `true`/`false`. Whether the argument can be negated. For example, `tag=!c` to select entities *without* the tag `c`. Note that negatable arguments are repeatable in their negated form even if their positive form is not repeatable.

### `nullable`
Boolean `true`/`false`. Whether the argument can be specified but empty. For example `team=` to select entities not on any team, `name=` for [entities without a name](https://i.imgur.com/PtmHGa1.png), and similarly `tag=` for [entities without any tags](https://i.imgur.com/ptycRFS.png).
