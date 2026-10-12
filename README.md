# retrolunar2-packages

Recipes in the v2 TOML format, for `retrolunar` 2. They live here while the format is
still moving; when it settles they move into `retrolunar-packages` and this tree goes
away.

Current content is the test rig: one system (`system@clang-native`) and the cheapest
packages that exercise every build system and the dependency machinery, on the host's own
compiler — `m4` (autotools), `zlib` (cmake), `libpng` (autotools, needs zlib), `fribidi`
(meson, no dependencies) and `pngprobe` (a hand-compiled probe that links libpng).

Nothing Android or cross is here yet, by design.

## Using it

```sh
retrolunar deps --packages . 'pngprobe@native'
retrolunar generate --packages . --nest ./nestdir -x 'pngprobe@native'
```
