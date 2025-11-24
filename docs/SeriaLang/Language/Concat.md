# String concat

In SerialLang, you can concat string. The catch is that it's only for globals

## Explaination

```ucl
&"My name's ${$::name}"
```

`&` before the string
Then you use ${expression} to insert a global
The global needs to be known at compilation

## Example
```ucl
%import entity/kill.uchc

const String $witherStormArmorStandName = "wither_storm"

fun KillWitherStorm():
    Kill()<&"@e[tag=${$::witherStormArmorStandName}]">
KillWitherStorm
```