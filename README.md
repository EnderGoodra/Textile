# Textile
A Balatro mod that overrides the base game's `evaluate()` function, adding in some extra style options for text.

## Added styles:
`{B:<integer>}` Creates a box around the selection, much like `{X: }` does for the base game. The color for the box is selected in a similar way to `{V: }`, where the provided integer acts as the index in the `colours` table, returned from `loc_vars`.

Curiously, this seems to allow spaces, unlike `{X: }`, but I am still learning why.
```lua
text = {
  'This is a {B:1,C:white}test{} for the {B:2,C:red}B{} style'
}
```
```lua
loc_vars = function(self, info_queue, card)
  return {
    vars = {
      colours = {
        G.C.SECONDARY_SET.Tarot, -- at index 1
        HEX("38000b"), -- at index 2
      },
    },
  }
end
```
