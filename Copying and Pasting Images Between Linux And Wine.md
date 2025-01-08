**Note:** Only tested on Linux Mint.

If you find that copying and pasting images between Linux and Wine does not work, try the following steps, which worked for me:

1. Open a terminal and type in `wine regedit`.

2. Once Regedit is open, locate the following key: `HKEY_CURRENT_USER\Software\Wine\X11 Driver`. If it is not available, add it.

3. Once you find or have added `HKEY_CURRENT_USER\Software\Wine\X11 Driver`, right-click on it and add a `String Value` called `UsePrimarySelection`. If it is already set, ensure its string value is set to `true`.

4. Now close `wine regedit`, and in the terminal, type `wineserver -k`. The next time you start software running under Wine (in my case, `Mp3Tag`), you should be able to paste an image into the cover section of the tag panel that you copied from Linux.

**Note:** `wineserver -k` may not always work, but rebooting Linux should.
