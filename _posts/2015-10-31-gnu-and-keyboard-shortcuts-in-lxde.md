---
layout: post
title: GNU and Keyboard Shortcuts in LXDE
---
I have recently attended GNU/Linux training at [Istanbul Hackerspace](https://istanbulhs.org/wiki/blog/gnu-linux-egitimi/). It was informal and eye-opening event for me. Besides, Philosophy of GNU is deeply impressed me. If you'd like to get more information about GNU like me, I recommend you to read *Free Software, Free Society: Selected Essays of Richard M. Stallman* book. I have been reading the book, too. It is avaible in Turkish too.

I have made a few decisions after the training like using free software as far as possible, removing Windows from my computers. So, **Debian and LXDE** have been my choices.

After installation, I have noticed that general keyboard shortcut of terminal (Ctrl+Alt+T) is not implemented in LXDE. After searching on a web, i have figuered how i will do.

In LXDE, general settings hold in `~/.config/openbox/lxde-rc.xml` file. Keybindings, too.

Control keys (Ctrl, Fn, Windows Button, Alt) are implemented differently as shown in below.

<table><tbody>
<tr><th>Control Key</th><th>Implementation</th></tr>
<tr><th>ALT</th><th>A-</th></tr>
<tr><th>CTRL</th><th>C-</th></tr>
<tr><th>SHIFT</th><th>S-</th></tr>
<tr><th>Windows Button</th><th>W-</th></tr>
</tbody></table>

Lets impelement whole part.

```xml
<!-- Launch LXTerminal with Ctrl+Alt+T by FG -->
<keybind key="A-C-t">
  <action name="Execute">
    <command>lxterminal</command>
  </action>
</keybind>
```

- LXDE uses`lxterminal`. So, execute command of lxterminal is `lxterminal` too.
- In Keybind part, requested keyboard shortcut is implemented.
- Be careful about, implementing the add-on between `<keyboard>` and `</keyboard>`.

For nonworking volume buttons, this tutorial works too.

```xml
<!-- Volume Up by FG -->
<keybind key="A-F12">
  <action name="Execute">
    <command>amixer -D pulse sset Master 5%+</command>
  </action>
</keybind>
```

- Volume button uses amixer program. For more information, execute `man amixer` at terminal.
