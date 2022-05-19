# linuxfix 0.4.4
# Do not bother using this if you are on Windows.

This addon will need to be autoloaded via your init.

This code has only been tested with fairly standard en-US keyboards.

This addon restores full keyboard functionality in Windower with newer versions of Wine and bypasses the need to build your own version of Wine with a specific commit reverted.

It also remaps Windows key bindings and makes them functional again with the exception of bindings with multiple modifiers such as %^!1 (Ctrl+Super+Alt+1). The listbinds command is only capable of returning a single modifier and thus they cannot be remapped correctly. (This is currently being looked at by the development time and may be fixed in the future.)

It reads and parses the content of the 'listbinds' command anytime it runs and forwards the keys as appropriate to the client. It also hides the output of this command to avoid console spam.

It's not a fix since it doesn't actually repair the original issue of the keybinds using raw keyboard input but it does work nicely as a workaround.

When there are a left and right version of a key such as lctrl and rctrl windower sends the lctrl dik even when the right key has been pressed. This also applies to enter and numpadenter.

While the correct keys are in the table below, windower will just use the left version.

For lack of a better method of keeping the keybinds up to date, the list is refreshed every time you press a key. This was done because Gearswap files frequently rebind keys between jobs.

Since this caused significant lag, a limit was placed so it could not run more than once per second. This limit can be modified using the 'check_rate' variable.

The binds are also now added to a table and don't have to be parsed everytime you press a key which has reduced overhead as well.

Big shoutout and thanks to Rubenator, he took the awful code Surik and BeYoNDLiFe gave him and made it so much better.
