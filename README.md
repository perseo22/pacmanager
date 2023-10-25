PAC (Perl Auto Connector) is a SecureCRT/Putty/etc. (connections manager with automations) equivalent for the Linux world.

PAC is developed by David Torrejon Vaquerizas (david.tv@gmail.com), and is FREE software, released under GNU's GPLv3 license.

# Current features

- Simple GUI to manage/launch connections to remote machines.
- Scripting possibilities, 'ala' SecureCRT
- Configurable [Pre|Post]-connection local commands execution.
- Configurable list of macros (commands) to execute locally when connected or to send to connected client.
- Configurable list of conditional executions on connected machine via 'Expect':
  * forget about SSH certificates
  * chain multiple ssh connections
  * automate tunnels creation
  * with line-send delay capabilities!! etc...
- KeePassX integration!
- Ability to connect to machines through a Proxy server!
- CLUSTER connections.
- TABBED/WINDOWED terminals
- Wake On LAN capabilities
- Local and Global variables, eg.: write down a password once, use it ANY where, centralizing its modification for faster changes! use them for:
  * password vault
  * reusing connection strings
- Seamless Gnome/Gtk integration.
- Tray icon for 'right button' quick launching of managed connections. Screenshots and statistics!
- DEB, RPM and .TAR.GZ packages available
- Written in Perl/Gtk (wait, *is* that a feature? Well, it is for me! ;=)
- It is FREE (as in freedom) and licensed under GNU GPLv3.

# Installation

- Preferably, use GetDeb:

```sh
echo 'deb http://archive.getdeb.net/ubuntu <your_distrib_name>-getdeb apps' | sudo tee --append /etc/apt/sources.list
```

If you can't/don't want to use it, simply download the corresponding package from [SourceForge](http://sourceforge.net/projects/pacmanager) for your system and install it.

Now you can take a look at your Gnome's menu under "Applications" -> "Internet" -> "PAC", or type "pac" in your terminal.

# Changelog

- 4.5.5.8:

* Fixed a bug that prevented PAC from starting with "clusters" view selected

- 4.5.5.7:

* Fixed *for real* the Vte.so for perl 5.22 64 bit (... so tired... Forget about 4.5.5.6, it was just bullshit, and may be this will also be the same).

- 4.5.5.6:

* Added support for perl 5.22 64bit for library Vte.so
* Minor variable substitution (`<ASK:desc|opt1|opt2|...|optN>`) bugfixing

- 4.5.5.5:

* Modified "SSH" Advanced Options, to be more GUI friendly, and with a context menu to show available SSH advance options (those '-o "xx=yy"')
* Modified "SFTP" Advanced Options, to be more GUI friendly, and with a context menu to show available SFTP advance options (those '-o "xx=yy"')
* Added an option to show the command line that each connection will launch, under "Edit"->"Advanced Parameters"->"Get Command line"
* Fixed a bug that prevented some SSH users from forwarding ports: "/" syntax not recognized by *every* SSH client. Goung back to ":"
* Minor fixes

- 4.5.5.4:

* Added support to allow per-connection "select by words"
* Nth "/r" fixxxxxxxxxxxxx... :(

- 4.5.5.3:

* Another "/r" bugfix... (hope it's the last!)

- 4.5.5.2:

* Fixed a bug with older Perl version not recognizing "/r" regexp modifier (terminal ransparency related...)
* Fixed a bug which prevented the use os "word chars" in a "per terminal" basis

- 4.5.5.1:

* Added support for ARMV7L devices! (Tested on my HTC One M7 phone with Perl v5.20!)
* Fixed a bug that prevented terminal transparency from being saved
* Fixed a bug that prevented forwarding CLIPBOARD for "rdesktop" connections (xfreerdp is still buggy!)
* Removed the `ALT+W` shortcut to open the "Wake On LAN" window
* Fixed a little bug regarding "autohide connections list on connection open" not working correctly
* Fixed a little bug  regarding Preferences window not showing again if previously was clos viz the "x" window button
* Modified the "Split" routine to try to give same space to splitted terminals

- 4.5.5:

  * Fixed a behaviour that could lead to show VNC passwords on status bar tooltip
  * Fixed a bug that made main PAC window move on every new terminal creation
  * Changed behavior to not take a screenshot if "show screenshots" checkbox is unselected
  * Added support (libraries) for Perl 5.20, in both 32 and 64 bit
  * Minor code cleanup

- 4.5.4:

  * Added the capacity to change "MOSH" protocol SSH port and Server-side UDP port
  * Minor bug-fixes

- 4.5.3.9:

  * Fixed nth bug regarding main window not showing when "start minimized" is selected ("blank window" bug!)

- 4.5.3.8.1:

  * Added "Font Smooth" option to "xfreerdp" connections (may not work on all 'xfreerdp' client versions) Tested with 'freerdp-x11 1.0.2-1'
  * Finally fixed the problem with Terminal loosing focus when changing from TAB!! :)
  * Fixed a bug that prevented PAC from using all the available space for embedded RDP windows
  * Fixed a regression bug that prevented using both "Auto reconnect" and "Delay char sending" at the same time

- 4.5.3.8:

  * Modified history widget to prevent execution of commands if Terminal is disconnected (strange thing could happen!)
  * Fixed a bug that prevented the "Config" window from being closed under some circumstances
  * Changed Wake-on-lan shortcut from `ALT+O` to `ALT+W`
  * Minor changes to optimize how right-click "SFTP" from SSH connections work
  * Minor bug fix to prevent showing main connection on very particular circumstances

- 4.5.3.7.2:

  * Another bugfix for some Gtk2 versions not respecting some methods

- 4.5.3.7.1:

  * Nth micro bugfix... (I'm so sorry for being such a lame programmer... :(  )

- 4.5.3.7:

  * Added a confirmation dialog when deleting keypress-history
  * Fixed a bug regarding "Disconnect and restart" session
  * Added requirement for "libgtk2-unique-perl" library

- 4.5.3.6:

  * Added support for PowerPC 64 bit architecture! (awesome community job!!!)
  * Added an option to show a list at Terminals right side to show the command history!
  * Much better algorithm to detect terminal prompt for history to be detected!!
  * Added support to Bulk Edit EXPECT fields also!
  * Given some love to Unity's launch icon right click menu (quick conn + local shell)
  * Added `--password=<pwd>` to allow autologon without interactively asking user for password when PAC's protection is ON
  * Minor code optimizations

- 4.5.3.5:

  * Added "Run with 'sudo'" under "Method". Password and prompt is defined in "Preferences -> PAC Main Options -> Advanced"
  * Modified the "autoreconnect on disconnection" to handle better disconnections, and distinguish between correct (manual) and forced disconnections
  * Minor GUI improvements
  * Fixed a bug that prevented PAC from using "autossh"
  * Little GUI change to make more visible SSH/SFTP's "Advanced options" entry box

- 4.5.3.4:

  * Added support for "other" Gnome2::Vte versions different than 0.9 and 0.10 (0.11??)

- 4.5.3.3:

  * Added "$TERMINAL{get_prompt}" to PAC Scripts' API, in order to "try" to guess connection's prompt with minimal effort
  * Added an option to allow starting more than one PAC instance (only first instance allows modifying PAC configuration)
  * Added option "--readonly" to command line to allow starting PAC in READ ONLY mode (no config changes allowed)
  * Much more love given to PAC Scripts (engine and gui)
  * Added DONATORS list to PAC on "About" -> "License". To all of you: THANK YOU SO MUCH!!!!!!!!
  * Added an option to allow to remove or not CONTROL chars when automatinc log saving is active (on both global/pero connection preferences)
  * Added "--dump-uuid=>uuid>" command line option to dump information about a connection
  * Added "--scripts" command line option to auto-start PAC Scripts window
  * Added an option under "Preferences" -> "Terminal Options" -> "Look & Feel" to allow switching TABs with ALT-Left/Right instead of CTRL-PgUp/PgDown
  * Added shortcut `CTRL+ALT+R` to easily remove a Terminal from it's current Cluster
  * Added $PAC{start_uuid} and $PAC{start_uuid_manual} to Scripting to allow starting sessions based on UUIDs instead of names
  * Fixed a minor bug for autostarting PAC at session startup

- 4.5.3.2:

  * Fixed a bug that prevented PAC from using a proxy under some circumstances (no ip/port defined on Global Preferences)
  * Fixed some minor glitch

- 4.5.3.1:

  * Added "Vte.o" library for RASPBERRY "Raspbian" support!! ;)

- 4.5.3:

  * Added support for SOCKs proxies!
  * Added support for defining proxies configuration PER CONNECTION! :)
  * Added an option to "Auto save" every PAC change in realtime, without user interaction
  * Added preliminary date/time information on disconnections
  * Added support for Perl 5.18
  * Fixed a minor bug with PAC `<ASK:...>` substitution variables
  * Changed PAC's behaviour to prevent password from appearing on "ps" command for RDP (both rdesktop and xfreerdp commands)

- 4.5.2.3:

  * Fixed a bug that prevented PAC from starting when a connection was autostarted and "hide to systray" was checked

- 4.5.2.2:

  * Added an option to allow copying or not mouse selection to global clipboard
  * Added an option to allow choosing whether sending or not a `<INTRO>` keypress for remote commands/macros
  * Added '--list-uuids' command line option to list current connections/groups and their corresponding UUIDs
  * Added '--no-splash' command line option to avoid presenting a splash screen on startup
  * Added '--iconified' command line option to make PAC go to tray once started
  * Added an option to open a file manager on current dir (pwd) for Local Shells
  * Added an option to PAC Scripts's function "$TERMINAL{send_get}" to allow skipping `<INTRO>` from being sent
  * Fixed the "star PAC on session startup" behavior
  * Fixed a bug that prevented right-click menu from appearing when RDP embedded windows were closed

- 4.5.2.1:

  * Added Regular Expressions to "Bulk Edit"
  * Added options to let user choose what happens when last tab is closed: nothing, close or hide (Preferences -> Terminal options -> Look&Feel)
  * Added "-r scard" option to "rdesktop" method, in order to be able to use SmartCard authentication
  * Added SeamlessRDP options to 'RDP' backends
  * Added options to define prompts for: unknown host key, remote host key changed and pres any key to coninue
  * Added "--start-shell" command line to auto start a local terminal on PAC startup
  * Added some "bash completion" for command line options
  * Added "Clipboard redirection" option for 'xfreerdp' connections (off by default: buggy!)
  * Added some "love" to PAC man page
  * Fixed a bug that prevented saving "Width" & "Height" value unless focus out those entry boxes on RDP connections edit
  * Fixed some minor gui glitches

- 4.5.2:

  * Added support for non UTF-8 encodings in KeePass!!
  * Added the possibility to have BOTH "rdesktop" and "xfreerdp" connectors at the same time, allowing user to choose which one to use! :)
  * Added the possibility to "EMBED" RDP windows when using 'xfreerdp' (only tested/working on Ubuntu/Unity). It doesn't always honour the "-X" option :(
  * Added the possibility to "EMBED" VNC when using 'xtightvnc' (only tested/working on Ubuntu/Unity). It doesn't always provide/honour the embedding option :(
  * Added an option to not cipher text when exporting connections (more compatibility when importing from another machine)
  * Added `<KPXRE_GET_(title|username|password|url)_WHERE_(title|username|password|url)==YourPerlRegExp==>` PAC variable to choose a value from KeePass given a source and a Perl Regular Expression ( i.e: `<KPXRE_GET_username_WHERE_title==^.*local\d+$==>` here, '^.*local\d+$' is the Perl Regular Expression )!!
  * Added command line option `--start-uuid=<uuid-of-connection-to-start>[:<cluster-where-to-start-it>]`
  * Added command line option `--edit-uuid=<uuid-of-connection-to-edit>` to start PAC directly editting a connection
  * Added command line option `--start-script=<script_name_to_start>` to start given script directly on PAC startup
  * Added command line option `--quick-conn` to start 'Quick Connect' GUI dialog on PAC startup
  * Added command line option `--preferences` to start 'Preferences' GUI dialog on PAC startup
  * Added conneciton's "UUID" information on Advanced options of connections
  * Added right-click populate menu to "Private key" authentication method for both User and Passphrase
  * Added an option to start/stop automatic string sending from right-click submenu on connections
  * Changed KeePassX infer behavior to allo using a Regular Expression to match against a Title
  * Changed PAC behavior when no Gnome2 or Unity are available, allowing user to activate PAC's tray icon
  * Fixed some bugs with TigerVNC authentications
  * Fixed a bug with remote RDP forwardings not being correctly saved
  * Fixed a bug tha tprevented starting RDP terminals with 'xfreerdp' under some circumstances
  * Fixed a bug with private SSH file not being correctly saved
  * Other minor code changes / improvements

- 4.5.1.9:

  * Now fixed (for real!) a bug that prevented PAC from starting under rare circumstances.. :(

- 4.5.1.8:

  * Fixed a bug that prevented PAC from starting under rare circumstances.. :(

- 4.5.1.7:

  * Fixed a bug that prevented PAC from starting under rare circumstances.. :(

- 4.5.1.6:

  * Added an option to ask user for a "cluster" name when adding a terminal to a cluster when no cluster is selected/exists
  * Fixed a bug that prevented using non-UTF8 characters
  * Fixed a bug that prevented saving per connection "Variables" correctly (hmmm... looks like nobody uses this...)
  * Fixed a minor bug regarding starting *many* connections at a time on groups and subgroups

- 4.5.1.5:

  * Fixed a bug at PAC startup for some systems (not all where affected...)

- 4.5.1.4:

  * Added the possibility to export ALL connections from right click menu on "AVAILABLE CONNECTIONS" label
  * Added button so un/select all lines for "Full duplicate connection" window
  * Fixed another little bug when "refreshing" KeePass preferences window
  * Improvements "Copy/Paste/Export/Import" methods
  * Fixed a bug for KeePass that prevented using "special Perl regexp" characters for matching on fields
  * Fixed a bug regarding "Favourites" and "Recent" connections not starting correctly on "Clusters" with right click menu
  * Fixed a little bug with renaming connections on root
  * Small code fixes

- 4.5.1.3:

  * Oooops... I did it again... :( I forgot to add a couple of fixes for KeePass...
  * Fixed PACShell not respecting initial directory
  * Added a... well...mmm...you know......errrr........ Hell! Yes! I just put a "Dumb Easter Egg"(TM) ;)

- 4.5.1.2:

  * Code changes for PACShell (now, part of PACTerminal), so better intergration with PAC functionalities (clusters, search, etc.)
  * Added options to KeePass to add "URL" searches
  * Speed improvement on KeePass integration (right-click menus, startup terminals, etc.)
  * Added an option to no append group name to newly created connections ("Preferences" -> "PAC Main Options" -> "Automatically append group name to...")
  * Added a "best effort" option to set title based on server hostname (you know: *best effort*! No promises at all! :) Shift+Ctrl+G and right-click menu

- 4.5.1.1:

  * Fixed a bug for new tray code changes (shame on me...)

- 4.5.1:

  * Added support for native Ubuntu's "application indicator" (tray unavailable since 13.04) if "libgtk2-appindicator-perl" is installed
  * Disabled tray icon for Gnome-shell (Gnome3) environment (no support by now)
  * Added "-N" option for 'SSH' connections
  * Added shortcuts for "Reset Terminal" (Shift+Ctrl+X) and "Reset and Clear Terminal" (Shift+Ctrl+Alt+X)
  * Added an option to load "KeePass" DDBB "On demand" (off by default) everytime it is required, instead of on menu creation (if 'off', faster menu building)
  * Modified "KeePass" code to offer a list when more than one strings matches a regexp, with an option to always choose the first without asking.
  * Fixed a bug that prevented using "strange" characters for RDP connections (like: $, @, etc.)
  * Modified Black&White tray icon
  * Fixed screenshots/statistics not being reset when copying/duplicating connections
  * RPM package bugfixing (conflict with "filesystem" package!)
  * Nth change to detect Vte version 0.10 (Perl 5.16 w/o Fedora18??) with cleaner code (and less problems!)

- 4.5.0.3:

  * Fixed a bug that made the "select by word" fail when "Use these personal settings" was checked in a connection.
  * Another modified installation code to deal with Vte 0.09 and 0.10 versions

- 4.5.0.2:

  * Added "clipboard redirection" for "xfreerdp" connection method
  * Modified installation code to deal with Vte 0.09 and 0.10 versions
  * Fixed a bug that affected copy/pasting multiple nodes more than once
  * Fixed a bug that made PAC die whe "Restar ALL terminals" was pressed on PCC and some terminals where already disconnected
  * Minor fixes

- 4.5.0.1:

  * Added an option under "Preferences" -> "Terminal Options" -> "Look and Feel" to allow hidding the bottom status bar
  * Removed PAC main's bottom status bar ("too" many pixels just to know how many terminals are open ;)
  * Fixed a security bug that prevented using more than 8 characters for PAC "lock/unlock GUI" feature. After update, *YOU NEED TO REACTIVATE THIS FUNCTIONALITY* in order to use it again (sorry for this...)
  * Fixed a bug that prevented saving confgs if "Infer from KeePass" is checked but no username/password was introduced
  * Fixed a bug that prevented the keyboard focus from being setup on focused tabs
  * Fixed a bug that prevented removing a cluster
  * Added the possibility to temporary change "LOCAL - SHELL" label (right-click mouse menu over terminao)
  * Some aesthetic code changes
  * Some minor code changes

- 4.5:

  * Initial KeePassX support: new right-click menu options and User/Password setup!! (checkout "Preferences" -> "KeePassX Options")
  * Minor GUI modifications to move options to different TABs (advanced, look and feel, etc.)
  * Minor code changes for VNC handling
  * Minor `<Ctrl>` glitches
  * Added another control for detecting "Press any key to continue" when connecting

- 4.4.1.2:

  * Added an option to selectively force to always/never or use default config for using or not Proxy to connect
  * Moved the "start new local shell" keyboard shortcut from `Ctrl+T` to +Ctrl+Alt+T`
  * Moved `Ctrl+T/D` shortcuts to `Ctrl+Shift+T/D` (new terminal/duplicate), in order to avoid WindowManager/connection conflicts

- 4.4.1.1:

  * Fixed a bug with 'freerdp' that prevented some connections from happening
  * Added `Ctrl+Shift+Tab` option to back on Tabs change

- 4.4.1:

  * Modified the "Remote" and "Local" macors buttons/comboboxes to alphabetically sort defined macros
  * Added "WebDAV" connection method via "cadaver" binary
  * Added an option to choose when "incremental search" on connections, to search on Name, IP/Host or Description
  * Added the possibility to reorganize Connections TABS (cluster, history, favourites and connections)
  * Added an option to modify `CTRL+Tab` behaviour: goto next tab or goto last used tab
  * Added a "Description" view for the "Check Auto Cluster condition"
  * Added "LowColourLevel" support for "TigerVNC" connections
  * Added an option to remove running terminals from cluster being deleted
  * Added more options for "RDP" when 'freedrp-x11' is in use
  * Added "Clusters" to right-click context menu for PAC Tray icon
  * Added an option to close ALL terminal from right-click context menu on both Vte and Tab, and also `CTRL+SHIFT+F4` shortcut
  * Fixed some NLS problems authenticating for RDP
  * Fixed some minor bug

- 4.4:

  * Added Clusters saving!! A new TAB has just arrived at main "Connections" TAB, where you may launch already saved "Clusters". Included "Auto Clusters"!!
  * Added an option to choose "Info" TAB font (now defaults to "monospace")
  * Added "-depth" support for "TightVNC" connections
  * Added some GUI artwork changes and fixes

- 4.3.1.3:

  * Added Vte support for Perl 5.16
  * Modified the "Remote commands" code to send button commands to every node in cluster (if new gui box is checked)

- 4.3.1.2:

  * Minor bugfixes

- 4.3.1.1:

  * Fixed a bug that prevented from starting PAC under a certain circumstance (regression bug!)

- 4.3.1:

  * Added a checkbox in the "Choose private key file", "Choose screenshot file" and "Autosave session log" dialogs, in order to allow "Show hidden files"
  * Added an option to change the "combo box" for a "list of buttons" (ala SecureCRT) for remote commands (macros) under "Preferences"
  * Modified the "Statistics" behavior to allow resetting stats for all pac and or groups
  * Fixed an aesthetical bug regarding "Public" key file instead of "Private" key file
  * Fixed a minor bug that prevented the macrosbox from appearing at the bottom of the terminal
  * Fixed a bug that prevented "Local Shell" from receiving keyboard shortcuts
  * Another little bugfix regarding local/remote macros not showing properly on PAC GUI

- 4.3:

  * Awesome PAC startup speed improvement, specially when *too many* connections are configured!
  * Added options to allow/deny both visible/audible terminal bell
  * Added DnD method for the "Local Shell" tab to untab
  * Added `Ctrl+Alt+D` shortcut to duplicate current connection
  * Added `Shift+Ctrl+Alt+D` shortcut to *FULL* duplicate current connection
  * Fixed a bugt that prevented PAC from working properly with "local executions on disconnection"
  * Fixed a bug that prevented PAC from correctly working if both "rdesktop" and "xfreerdp" packages were installed
  * Modified the "Save" connection method to not to allow saving if any error encountered
  * Fixed erroneous check for "cu" connections on save

- 4.2.3.3:

  * Added support for "mosh" connection method (MObile SHell)
  * Another change to handle Ctrl/Shift/Alt combos (many complaints...)
  * Added some other shotcuts (Ctrl+t -> open a new local shell, ...)

- 4.2.3.2:

  * Finally added a good/working version for CTRL-SHIFT-6 (Cisco ping-break combo)
  * Little code to avoid the right-ALT (mod2-mask) from being read (bugs reported!)

- 4.2.3.1:

  * Added an option on the right-click menu over terminals to make an SFTP connection if current connection is SFTP
  * Fixed a bug that prevented some operations on groups, like starting every connection on a cluster
  * Added "auto indentation" for the GtkSourceView2 widget (PACScripts)
  * Little modification for the "USERNAME prompt" field
  * Changed the "Close terminal on disconnection" option to close only if no "bad exit" is detected (no route to host, bad password, ...)
  * Fixed a little bug that made weird things with the "Description" text when using "Favourites"

- 4.2.3:

  * Added a "Quick Connect" button
  * Added support for IBM's 3270/5250 connection method! (thanks, Grant Williamson!)

- 4.2.2.1:

  * Added an option to choose Connection's tree Font
  * Added an option to start connections from within login shells (the one defined at "Preferences" -> "Local Shell Options")
  * Little code change to suggest the installation of some packages (cu, rdesktop, ...) in case their binaries are not found
  * Deep code changes for the "PACTree.pm" and "PACMain.pm" modules, for better object managing and code clarity
  * Modified the port-forwarding options to delete the "insert time" radiobutton, and set the "Local Port" as default sorting method
  * Fixed a bug that prevented saving a SSH connection if the same local port was defined for forwarding, even if on different local ips

- 4.2.2:

  * Experimental ARM support (32 bit ARM Vte.so library included, thanks to 'sourcefabric')
  * Added an option to sort SSH's local/remote/dynamic forwardings by several criteria
  * Added a check for SSH's local/remote/dynamic not to allow repeating same Local Ports 
  * Modified the "Method" text to not link to specific commands (now, 'VNC' appears instead of 'vncviewer', 'RDP' instead 'rdesktop', and so on...)
  * Modified both History and Favourites tree to update GUI when selection changes
  * Fixed a bug that could misconfigure the GUI's "Port" property of connections
  * Fixed a bug that made the keyboard focus move when starting connections

- 4.2.1:

  * Improved and new options to the conditional 'Expect' widgets
  * Added support for "autossh" (if installed) with 'ssh' connections
  * Added a tooltip over connections tree to show info on hovered connection ("Preferences" -> "PAC Main Options" -> "Show connections tooltips", OFF by default)
  * Added an option to "quote" the connection command when using "Prepend command"
  * Added an option under "Preferences" -> "Terminal options" to hide the "Connections" submenu from right-click terminal menu (speed up menu appearing, OFF by default)
  * Improve handling for uninstalled packages, giving hints about them (RDP, VNC and Serial connection methods)
  * Fixed some minor bug about using Pango reserved characters (`<`, `>`, ...)
  * Other minor gui glitches
  * Removed from the dependecy list 'xtightvncviewer', 'tigervnc' and 'rdesktop', for both DEB and RPM packages, and moved to the Suggestes department

- 4.2:

  * Added a Notebook to contain the connections tree and two new categories: favourites and history !!
  * Added "Conditional Expect" !! Wow!! :) Checkout your per-connection "Expect" tab and take a look at those new little options on the right side
  * Added a new Time Out variable for finer conditional "Expect" chaining
  * Added an option to send local/global/environment variables values to a terminal via right-click menu!
  * Added an option to "Chain" a given connection via terminal right-click menu!
  * Added an option to execute a command without user confirmation on connection "Pre exec" and "Post exec"
  * Fixed a bug that could make some connections stop responging/disconnecting when resizing terminal's window
  * Fixed a regression bug that prevented the use of "Authentication fallback prevention"
  * Fixed an ultra-minor reression bug that prevented the "connections tree lines" from appearing if that option was checked
  * Code improvements for the auto show/hide connections tree
  * Fixed minor-gui glitches regarding auto-hide connections

- 4.1.2.3:

  * Fixed a bug that prevented PAC from starting if there is no network and "Check update" is active
  * Minor gui fixes

- 4.1.2.2:

  * Added code to use the newest 'dconf' architecture to detect correctly any proxy system-wide enabled
  * Added the ability to PCC to execute "Explode/Retab/Close all/Restart" in *every* connection if that option is checked
  * Fixed a minor bug that prevented "Bulk Edit" on single-selected connections
  * Fixed a regression bug that made unusable the "TAB / Window title" option for non-english languages
  * Added some sanity checks to PAC's config file
  * Modified the `<ASK:...>` method to allow simple strings beyond integers an listas of description|val_1|...|val_n

- 4.1.2.1:

  * Added the PAC variable `<PASS>`, which references connection's configured password
  * Modified the "Statistics" labels to show well-tabulated data
  * Major improvement to the "Check for update" method
  * Change PAC behaviour to forcefully prevent from starting more than one instance
  * Fixed a bug that prevented using *rare* characters (#, &, ...) in passwords for RDP connections under some circumstances
  * Fixed a bug that prevented "Pasting" on PAC Shell with right-click menu option

- 4.1.2:

  * Added the option to autostart PAC Scripts on connections startup
  * Once again, more Cluster bug fixes... omg, 1 new feature, 1 million new bugs... :( *that's* me programming!!

- 4.1.1.1:

  * Added UTF-8 support for more text fields (password, title, ...)
  * RE-fixed the problem with right-click menu and copy/paste/paste_special

- 4.1.1:

  * Fixed a bug that makes the "Embed" in TAB option for RDesktop option make it fail on recent Gtk libraries
  * Fixed some buggy "Copy" selection to clipboard
  * Fixed a creepy bug about right-click
  * Fixed a bug that prevented "Shells" from getting immediate keyboard focus
  * Fixed a bug regarding Clusters (every keystroke was being sent to every terminal)
  * RE-fixed the problem with session logs

- 4.1:

  * Lightning fast startup of terminals!
  * Added an option under PCC -> "single line entry" to allow showing what you type, and sending commands to cluster on INTRO keypress
  * Added a "$out = $TERMINAL{send_get}( 'command' )" convenience function to PAC Scripts: EXECUTE and then RECEIVE its output (not every terminal type supports this!)
  * Re-added a "Goto TAB" option for rith-click menu on TABs (useful when too many TABs are open!)
  * Better handling of full export/import oc PAC configs
  * Fixed a minor glitch regarding pre-v4.01 and "session logs" with new config directory structure
  * Fixed a regression bug thet prevented the "Paste and Delete..." (CTRL+B) on Terminals from *deleting* the entered string
  * Other ultra-minor/almost-transparent/cuasi-invisible glitches... :)

- 4.0.1:

  * Moved "$HOME/.pac" config directory to "$HOME/.config/pac"
  * Fixed a regression bug that prevented "Chaining" and "FULL Duplicate" connections (not very used, but features in the end! ;)
  * Fixed a bug that prevented the "mouse-over" action to show connections list from working on "Local shell" terminal

- 4:

  * Added "Scripts". Yeah!!! The only *good* thing that SecureCRT had and PAC did not, has just arrived to PAC Manager (but much better, of course! ;) Check out all sample scripts provided, and let your imagination do the rest!
  * PAC Scripts are written in Perl, and the built-in editor has syntax highlighting (if 'libgtk2-sourceview2-perl' is installed) and syntax checking
  * Modified the DEBIAN package dependencies list: rdesktop, xtightvncviewer, cu and remote-tty moved to "Recommended" section of Debian package
  * PCC Multiline `<PIPE:...>` and `<TEE:...>` algorythm modified: added `<PIPE:cmd:prompt>` to allow user choosing the output pattern to match for end of cmd execution detection
  * Added an option to move the connections tree to the right side
  * Added an option to prevent the connections tree from appearing on mouse over
  * Modified the login string for SSH in order to use the "-l" parameter, to allow using "@" in usernames
  * Added a routine to add 'pac' to Unity's systray-whitelist (enable systray ICON!!) You need to restart your X session (or Unity) for changes to apply
  * Substituted the "*ALL PAC TERMINALS*" cluster by a checkbox
  * Better management for `<PIPE:cmd[:prompt]>` PAC variable
  * Fixed a bug that made the "xfreerdp" option unavailable
  * Added "libvte9" as dependency
  * Added right-click options for new PAC variables (UUID, DATE_x, ...) to many entry boxes
  * Fixed some minor bug

- 3.4:

  * Added a *pretty* powerful PAC variable `<PIPE:local command>` to PCC to allow piping output from remote executions throught "local command". That is: execute whatever, and parse it locally (in your PC!)
  * Added a `<TEE:path_to_file>` PAC variable under PCC to "tee" commands' output to files
  * Now, if "auto-hide connections list" is checked (on), moving the mouse to the left side of terminals will make the tree appering, and reverse
  * Added the possibility to choose the name of auto-saved session logs, including patterns! (`<IP>`, `<USER>`, `<NAME>`, `<TITLE>`, `<DATE_Y>`, `<TIME_H>`, ...) Checkout tooltips!
  * Added an option to choose whether remove or not the ESCape sequences from the saved log file
  * Added support for "xfreerdp" (an alternative for 'rdesktop'). Anyway, I still prefer "rdesktop", and if both binaries are found, 'rdesktop' will be used.
  * Added an option to allow disabling the "F11 (fullscreen)" keystroke in Terminals ("Preferences" -> "Terminal Options" -> "Prevent F11 from going fullscreen")
  * Added a special cluster named " *ALL PAC TERMINALS*", which allow quick controlling *every* terminal from PCC, without individually asigning Terminals to clusters
  * Added a way to remember PCC's Window latest status (size, position and multiline input state)
  * Added an option to remember latest syntax highlighting for multi line text entry at PCC
  * Added an option to auto-start a local Shell upon PAC startup.
  * Added a "Restart All" button to PCC, in order to be able to restart every clustered terminal (added by petition)
  * Added the old "/etc/termcap" file in source code, in order to use it if it does not exist in present linux installation (somewhat, buggy...)
  * Modified the `<CMD:...>` PAC variable to: echo it's output if multiline or sending string for executing into terminal if result is single line
  * Fixed a bug that prevented PAC from using "Private SSH keys" with a space on its path
  * Fixed a bug that could make the "Import" phase failing with a "Ciphertext does not begin with a valid header for 'salt'..."
  * Minor bugfixes

- 3.3.10.2:

  * Adde the "-via" option for VNC connections (not much tested!)
  * Fixed a bug that prevented saving some non-ascii characters ( eg: € ) in password and other entry boxes
  * Fixed a potential bug regarding disconnected SOCKETS

- 3.3.10.1:

  * Added an option to allow disabling the key bindings for CTRL, ALT and SHIFT per Connection and in PAC's main UI
  * Fixed a bug that preventing any "Generic" connection method from using the "Expect" capabilities

- 3.3.10:

  * Added an option to password-protect PAC at startup and when restoring from tray (both optional)
  * Added a check to ansure that the user does not accidentally starts *many* connections at once by drag 'n dropping groups
  * Fixed a bug that prevented Ctrl+Shift+V from correctly pasting text (it appended "^M" at the end)
  * Fixed a bug regarding password with *strange* characters (#, $, etc...) for RDP connections
  * Removed the Ctrl+left/right keyboard shortcut to change between tabs (conflict with some SSH functionalities!)
  * Removed the the four Gnome2::Vte libraries (.rpm and .deb files) from the /opt/pac/res directory

- 3.3.9.5:

  * Added an option under "Preferences" to check for new PAC versions on demand (clicking a button)
  * Added Ctrl+left/right to switch between TABs
  * Fixed a bug that prevented PAC form entering '#' (hash) starting passwords in RDP (rdesktop) connections
  * Fixed a minor bug that prevented saving the forwarded port for SSH connections under some circumstances

- 3.3.9.4:

  * Fixed a bug that prevented PAC from importing a previously exported YAML file via "Preferences" -> "Export to... YAML file"
  * Added shortcut Ctrl+Shift+6 to send a "Telnet Escape Character" to the current terminal
  * Removed the toolip from the the PCC multi-line entry

- 3.3.9.3:

  * Fixed a bug that prevented PAC from working with Perl 5.14 (for both 32 and 64 bit OSes)
  * Added a right-click menu option to "Expand/Collapse" all under Connections tree

- 3.3.9.2:

  * Fixed a serious bug that prevented the righ-click context menu from appearing if there were Nodes with "strange" characters (backslash, slash, ...)

- 3.3.9.1:

  * Fixed a bug that made PAC show the `<b>` Pango tags under the Tray connections menu... :)
  * Fixed a bug that prevented PAC's main windows from remember its "Connections Tree" size

- 3.3.9:

  * Added an option (Alt+R) to "Protect" nodes/groups from being edited/deleted/cut/... (identified by an Orange background)
  * Modified the Groups name to appear in "Bold"
  * Fixed a bug that prevented PAC from using "New node/group" button when "AVAILABLE CONNECTIONS" (first row) was selected

- 3.3.8.1:

  * Added field "title" and "user for publickey passphrase" to the list of values to be "bulk-edited"
  * Added the possibility to also do "bulk editting" on Groups, selecting the depth of modifications you want: 1st level or ALL sub-levels children
  * Alt+E now also opens the "Bulk Edit" dialog
  * Added "Local Shell" connection to the right-click context menu of "Shell"

- 3.3.8:

  * Added a very demanded "Bulk Edit" option, which allows changing *some* values (by now: ip, port, user, pass and passphrase)
  * Added an option to allow modifying the same field from above for the selected connections before exporting (to avoid saving passwords, hidde-fields, etc)

- 3.3.7:

  * Added Statistics to show the: numbers a connection has been made, tha last time it was connected, ...
  * Added a "Local Shell" option for the "New connection" right-click submenus
  * Little modification to the string appearing at the start/stop of any execution (shorter/cleaner string)
  * Fixed a bug that under some weird circumstances, could make PAC go to 100% CPU usage
  * Fixed a bug that prevented pasting with mouse-middle-click if selection was outside PAC's terminals
  * Minor icon changes
  * Ultra-minor code changes

- 3.3.6.7:

  * Ehem... welll... 3.3.6.6 detected it's actual version as a new one... always... :(  ...ehemm...

- 3.3.6.6:

  * MANDATORY UPGRADE
  * Fixed a bug that made PAC fail under some circumstances (still debuggin right-click new menus!!!)  :(
  * Removed an unneeded timer for the Tray icon
  * More bug fixes...
  * I think I finally fixed a bug that prevented launching connections from the tray's right-click context menu

- 3.3.6.5:

  * Added an option to check for new PAC versions on PAC startup and notify if they are found
  * Modified the "slow send keypress" to also affect to the pasted text
  * Moved the "New connection..." right-click submenu to the first place

- 3.3.6.4:

  * Fixed a bug that prevented *any* modification in the "Preferences" window

- 3.3.6.3:

  * Added an option to send keystrokes slowly (every X configured milliseconds)
  * Fixed a bug that prevented a "Local Shell" from being started
  * Fixed a bug that prevented a new connectiona from being launched from the Tray Icon

- 3.3.6.2:

  * Changed the behavior of PAC's tray icon, in order to appear on KDE based desktops again
  * Fixed a bug that prevented PAC Terminal from showing its right-click menu under some conditions
  * Restored the "sensitive" property for context menus
  * Restored the "tooltip" property for context menus
  * Little GUI additions

- 3.3.6.1:

  * Fixed a bug that prevented PAC from starting if it did not find the Gtk2::SoureceView2 Perl package :(  (my fault!)
  * Fixed a regression bug that prevented the use of the middle-click to paste on terminal

- 3.3.6:

  * Big changes have been made to code, in order to use Gtk2::UIManager and Gtk2::ActionGroup, for better Gtk3 and future integration of [popup]menus
  * Code modification to allow using PAC without the Gtk2::SourceView2 dependency (simply, force the installation without that package, and it'll work)
  * Added a Ctrl+D shortcut on connections to CLONE
  * Modified the "Rename connection" GUI to allow changing both NAME and TAB/Window TITLE at the same time
  * Fixed a bug that made some connections fail if the TITLE string was not in plain English
  * Fixed a bug that allowed inserting connections/groups *before* the "AVAILABLE CONNECTIONS" node
  * Prevented renaming "AVAILABLE CONNECTIONS" row by pressing "F2"

- 3.3.5:

  * Finally, changed the "AVAILABLE CONNECTIONS" from being a "parent node" (less indentation, more space, cleaner UI)
  * Added an independent "User" entry for the "Public key"  authentication method
  * Added a button to open "Wake On Lan" GUI to allow sending "Magic packets" to any MAC address (no only those configured in PAC)
  * Forced PCC's sysntax higlight text font to "monospace"
  * Fixed a bug that prevented the "Autostart at session startup" from being persistent

- 3.3.4:

  * Added "Syntax highlighting" to the Textview of Power Cluster Controller, with options to load/save the text it contains!
  * Added a "Retab" button to the "Power Cluster Controller", in order to let the user Re-tab those independent connections' windows
  * Fixed a bug that prevented sending Ctrl+F to a terminal (instead, the Incremental Search dialog appeared!)
  * Minor configuration saving modifications
  * Minor code cleanup

- 3.3.3.2:

  * Fixed a bug that preventedlaunching some connections because of a missing character :(

- 3.3.3.1:

  * Fixed a bug regarding the "Prevent single window keystroke broadcast" from "PCC" not working as expected
  * Fixed a bug that made appear the "Incremental search" options when hidding and then showing the Connections tree view
  * Added shortcut Ctrl+Shift+B to do "Paste and delte" on terminals
  * Modified Ctrl+F to make the incremental search appear work wherever the Connections tree has the focus or not (on Terminals, the shortcut is Ctrl+Shift+F)
  * Moved Terminal's Copy/Paste/Paste and delete from submenu to main right-click menu

- 3.3.3:

  * Added a right-click option over Connections tree to Import/Export connections to/from ".yml" (YAML) files!! Finally!! ;)
  * Added a better "Incremental Search" for Connections (start typing to get results, or do Ctrl+F), which accepts Perl Regular Expressions
  * Added some transparent automatic backups with different confi file formats, to avoid some buggy Perl libraries not importing data from previous versions
  * Modified the load configuration function to make a best-effort into loading *any* valid previous config file

- 3.3.2.2:

  * Added an dialog to allow the user choose the file where to export the YAML data (from the "Edit" window) and it's format (by now, YAML and Perl Data::Dumper)
  * Added some checks ir order to avoid data loss when changing between 32 / 64 bit OS (what a pain!)
  * Modified the exit routine to *ALWAYS* save a .yml config file, in order to always have a fully machine independent config file (no matter 32 or 64 bit)
  * More cleanup code for config files

- 3.3.2.1:

  * Added an option (under 'Power Cluster Controller') to write commands on a text entry, and send it at once to the cluster! (exec all, selected or block!)
  * Added an option in the "Chain" gui to optionally allow sending Chains to all the elements of a cluster
  * Fixed a bug that prevented the exported .YML file from being password-encrypted (and thereby, it could not be used to restore it from backup)
  * Fixed a bug that prevented Re-tabbing a tab when it was "fulscreened"
  * Modified the Ctrl+number in order to act the same way whenever tabbed window is in main pac window or in a window apart

- 3.3.2:

  * Added some code to automate  the deletion of "offending keys" from the known_hosts file
  * Little modification to allow choosing wether to send or not a `RETURN` for every command in the "chaining" connection
  * Little modification to allow manual-change of the TAB title when chaining
  * Added an option under "Preferences" to "Export to YAML" the whole configuration. No, no XML (Defective By Design, like PAC ;), but YAML. Read about it.
  * Fixed a bug that prevented the "log amount to save" from the "Edit" window to save the correctly provided value
  * Fixed a bug that could prevent some chains/full duplications from being correctly handled
  * Modified the 'load/save' routines in order to use standard "Storable" functions
  * Modified the packages in order to include dependencies for telnet, ftp ans openssh
  * Faster PAC close when auto-save is turned on
  * Minor code cleanup and optimizations

- 3.3.1:

  * Added a GUI to choose the recorded commands to send to a "FULL Duplicated Connection" and the "Time" between commands
  * Fixed a bug that prevented saving "Terminal character encoding" for particular connections
  * Minor code cleanup

- 3.3:

  * Added Drag And Drop method to "Chain" one connection's "Expect/Execute" chains with an already already running connection!!!! (DND one conn A from the connections Tree into a running TAB/Window conn B, choose conn A expect/execute tuples from the popup, click OK, and see how those "Chains" are automated into conn B !!)
  * Added another option for right-click context menu on "Edit" entry boxes: added the possibility to create a list of choices for the user to choose (beyond the old free-type user input!!)
  * Added a "Pretty-powerful-but-hard-to-debug" option ( `<CMD:command to launch>` ) to execute commands to get values like those from `<GV:#>`, `<ENV:env_variable>`, etc... (image the possibility to use the next string in the "Host" entry box:
		`<CMD:exec bash -c "if [[ 'x`pgrep -f vpn_A`' != 'x' ]]; then echo -n '<GV:Pasarela_VPN_A>'; else echo -n '<GV:Pasarela_VPN_B>'; fi">`
		Of course, having predefined both "Gateway_A" and "Gateway_B" under "Preferences" -> "Global Variables" ...
		F**K YEAH!!!!!!
		And the same applies to the rest of entry boxes!! (checkout `<CMD:*>` right-clicking over entry boxes)
  * Added another option to "FULL Duplicate connection" (terminal right-click button), that is: duplicate and send every registered keystroke!! (beware! ;)
  * Added an option to show/hide lines in the Connections Tree
  * Minor GUI modification for the "Preferences" Window
  * Fixed a minor GUI bug that prevented the "Connections list" panel size to be restored if PAC starts maximized
  * Fixed a minor bug regarding personal background color for splitted connections in TABs
  * Minor bug-fixing and code cleanup

- 3.2.1.1:

  * Fixed a bug regarding "Copy/Cut/Paste"-ing the connections
  * Fixed a minor bug that prevented getting the keyboard focus on the connections tree at PAC startup
  * Little "right-click" menu modification on Terminals to remove the "Disconnect" option from under the "Duplicate" connection option

- 3.2.1:

  * Fixed a bug that prevented PAC from working correctly when "autostarting" connections at PAC startup if those connections had "PreExec" configurations

- 3.2:

  * Added an option per connection to make it auto execute when PAC starts
  * Added an "Auto reconnect" option for every session: if checked, connections will be automatically respawned every time they appear disconnected
  * Added an option to set the background color of TABs per individual connections
  * Added some checking to prevent the config file from being polluted... hmmm... :(

- 3.1.3.4:

  * Fixed a regression bug that prevented "Pre/Post Exec" commands from being executed!! (I see nobody cares about this PAC functionality... ;)

- 3.1.3.3:

  * Fixed a regression bug that prevented a connection from being "duplicated"/"cloned"
  * Added a dependency (gtk2-engine-pixbuf) in order to avoid Gtk warnings in distros with recent Gtk software

- 3.1.3.2:

  * Added support for 'TigerVNC', including embedding VNC connection in a PAC TAB!!
  * Really removed the UUID perl dependency in favour of OSSP::uuid
  * Removed 'cu' and 'remote-tty' as dependencies: now, if they are installed, they'll appear, other else, they will not.
  * Fixed some code to avoid unmet dependencies

- 3.1.3.1:

  * Added 'OSSP::uuid' as a PAC dependency for better RPM based distros compatibility.
  * Added the ability to save the width of the connections list between sessions
  * Modified the build procedure to include a "version-named" directory
  * Fixed a bug that prevented "Exploding" less than 3 Terminals
  * Fixed a minor bug regarding a .png file not being copied

- 3.1.3:

  * Added an "Programaticcaly send string" option to allow sending a given string + INTRO every some seconds to the terminal (allows PAC variables and so!!)
  * Added an "Automatic Take Screenshots" option
  * Added some code to keep the .pac/screenshots directory cleaner and more consistent
  * Added an option to automatically UNSPLIT disconnected Terminals in "Preferences" -> "Terminal Options"
  * Fixed a bug that prevented an embedded 'rdesktop' terminal from being detached from the TABbed view using Drag 'n Drop
  * Fixed a bug that made made a splitted connection to close the whole TAB when "Cloe terminal on disconnect" was selected
  * Fixed a minor bug that prevented correct colouring of TABs labes whith "Splitted" connections
  * Fixed a minor bug that made an unfocused TAB to steal keyboard-focus on connect
  * Modified PAC to not allow the TABs to be "focused" (annoying!)

- 3.1.2:

  * One million dependencies removed!! :) Now, Gnome2::Vte Perl library goes embedded in PAC source code!!
  * Added an option to "Paste and Delete" on Terminals: paste text omitting the specified string/regex
  * Removed the "ssh-askpass-gnome" dependency
  * Fixed a minor bug that prevented using specific options for Text/Bold/Back color for Terminals (regression bug)
  * Minor gui changes for the right-click context menu on terminals to reduce its size
  * Minor code cleanup

- 3.1.1.1:

  * Added an option to convert SSH/SFTP's '-o "IdentityFile=/your/public/keyfile"' to the corresponding "Publickey authentication method"
  * Added an option to allow authentication fallback
  * Fixed "Passphrase" not being encrypted in the config file
  * Fixed some minor gui bug
  * Some code cleanup

- 3.1.1:

  * New proxyfied connections 'pac_conn' code (faster and more reliable)
  * Modified the "connections tree" to sort the connections in a case-insensitive way
  * Added an option to allow more than one disk redirect for "RDP" connections
  * Added a "Disconnect session" option for the right-click menu on Terminals
  * Added an option to allow not to show the  "Tray Icon"
  * Added a "Close ALL" button to the "Power Cluster Controller" to close every terminal in selected cluster
  * Fixed a little annoyance with the PCC and "keypress propagation" 
  * Fixed a minor bug regarding the "Explode" button of "PCC"

- 3.1.0.2:

  * Fixed a little bug that prevented the "Manual" input of "user/pass" under some circumstances
  * Removed some annoying error output on the Terminals

- 3.1.0.1:

  * Modified "ssh/sftp" connection code to handle way better the "Advanced Options"
  * Fixed a bug with the 'vnc' connections

- 3.1:

  * Added a GUI option to use an SSH/SFTP publick key/passphrase for authentication
  * Back to 'freezed' config file format for PAC (file size grow bug fixed): *Faster* load/save operations, but config file obfuscation
  * Removed "FreezeThaw" Perl dependency (freeze/thaw retrieve from the already used "Storable" Perl module: faster!)
  * Added minor Drag And Drop support for the 'Expect' tab page of the "Edit" window
  * Added an option in Default Preferences to remember PAC's main window when closed
  * Added some cfg checks (with GUI feedback!) when saving connections data
  * Added support for VNC 'unix' username authentication
  * Fixed a *serious* bug regarding "Copy/Cut/Paste" of connections
  * Minor fix for "generic" connection type
  * Minor GUI changes for 'Edit' and 'Preferences' windows

- 3.0.1.2:

  * Fixed a bug that made the config file grow and grow indefinitely with every "Save" execution
  * Fixed a bug that prevented starting some connections
  * Removed the ".svn" directories from the ".tar.gz" distribution

- 3.0.1.1:

  * Some bug fixes, including those regarding with PAC prev3 migration... :(

- 3.0.1:

  * Added "Expect" capabilities for the "Generic" connection method
  * Rolled back the config file to the old-and-slow .YML format (terrible bugs made me take this decision!)
  * Fixed a bug regarding the "Clone" option

- 3.0:

  * Finally, added a "tree view" to present the list of connections (any level of folding allowed!)
  * Added Drag 'n Drop support to start connections in Windows or Tabs! You may even drag connections to the "Cluster Administration" window!!
  * Added a new "Power Cluster Controller" way to manage the clusters, 'a la' "clusterssh" (try 'Exploding' the clustered terminals ;)
  * Added an entry in "Preferences" -> "PAC Main Options" to choose the "Word Delimiting Characters"
  * Added support to start terminals directly into clusters
  * Added an option to select the "word delimiter" characters
  * Added an option to choose the 'backspace key binding' both globally and per terminal
  * Added an option to specify the "Terminal Emulation" (xterm, ansi, vt100, whatever...)
  * Added a couple of mnemonics for PAC's Main Window
  * Added an option to choose the "bold" color of the text in both "globally" and "per connection"
  * Modified the management of PAC's pid file to allow multi user concurrent execution
  * Modified the config file for speed purposes. As a collateral effect, I ofuscated it :(
  * Modified the code to support the 'iso-8859-1' text encoding (finally!)
  * Modification to avoid specifying the 'telnet' port when using the standard one (23)
  * Fixed an error that prevented a MAC Address from being saved from session to session when using "Wake On Lan" utility
  * Fixed some minor bug about multiusers
  * Fixed a strange bug that made PAC go out of memory under rare circumstances
  * Fixed a minor bug not showing the main window when restoring from the System Tray (KDE) (thanks goes to Fabio Rossi)
  * Fixed a couple of regression bug whrn 'Renaming' or 'Cutting' a connection
  * Fixed a minor bug that prevented a "rdesktop" shared folder name from being showed in the "Edit" window

- 2.5.5.10:

  * Added a right-click option over the connections list to start more up to 10 instances of every selected connection
  * Added a "Windows Domain" option tor RDP connections under the 'rdesktop' options of the connection editting window
  * Modified some Ctrl+C keypress to try to avoid some undesired disconnections
  * Added mnemonics for saving/closing the "Edit" and "Preferences" windows
  * Ultra-minor connection editor GUI changes 

- 2.5.5.9:

  * *AMAZING* speed improvement for starting connections when you have *many* sessions saved!! (almost instant connection opening!!) ;)
  * Minor GUI changes for the "Edit Connection" window
  * Little GUI change for the "pac.glade" file, to re-allow the autosize of entry boxes

- 2.5.5.8:

  * Solved the bug that prevented restarting the terminals just by pressing "Intro"

- 2.5.5.7:

  * Added a right-click option on connections list to clone a connection
  * Added a workaround to solve a problem with keyborad focus on embedded RDP connections, plus a "get focus" button was added for thos connections
  * Fixed a bug that prevented PAC from choosing more than one connection when a connection was already opened
  * Little bugfix that prevented PAC from asking for confirmation on exit whith connected sessions
  * Added a check to disable any connection method not found in the system (for forced intstallations...hummmm...those RPM based...)
  * Modified a couple of RPM dependencies names ('cu' to 'cunit', 'xtightvncviewer' to 'tightvnc', removed 'ssh-askpass-gnome')
  * Modified the SSH method options page to show the "Local port forwarding" tab by default
  * Modified the "Hostkey changed" SSH connection pattern matching for better performance
  * Added a little utility 'pac_from_mcm.pl' that allows you to build an initial pac.yml file from an MCM exported file
  * Added a check to build '$HOME/.config/autostart' required for PAC to work with 'Autostart when session starts'

- 2.5.5.6:

  * Added an option to restart closed connections by pressing `<ENTER>`
  * Added MAC address saving for WakeOnLan
  * Modified the code to do 'symlink' instead of 'link' when checking 'AutostartPAC at session startup' (thanks to Fabio)
  * Little info addition for [dis]connection in the terminal itself
  * Added an option to skip confirmation on PAC exit
  * A little bit of ultra-minor code cleanup
  * Added some modifications for the RPM builder (implicitly included some dependencies)

- 2.5.5.5:

  * Added 'parity', 'halfduplex' and 'nostop' options to 'cu' connection method
  * Added the 'libsocket6-perl' dependency

- 2.5.5.4:

  * Added an option to choode the Terminal encoding type (both globally and per saved terminal)
  * Added the possibility to define GLOBAL "Remote/Local" macros definitions (good for not repeating every command for every new connection)
  * Fixed a bug that prevented using "-" characters for "Local/Remote/Dynamic" port forwarding!
  * Fixed a bug that prevented doing substitution (global vars, etc) on WakeOnLan window
  * Little code movements to ensure correct IPv6 handling (specially for 'ssh' connection method)

- 2.5.5.3:

  * SSH method: GUI mofifications for the editing window
  * SSH method: added support for more than on "Dynamic Socks Proxy"
  * Added Alt+C (show/hide connections list) support to the "Local Shell"
  * Moved temporary files from /tmp to $HOME/.pac/tmp for security reasons
  * Moved General "Timeouts" from its own tab to "Terminal Options" tab under "Preferences"
  * This is a "premature" release because of Sourceforge's recent attack

- 2.5.5.2:

  * Added the right-click Terminal menu to the terminal's TAB
  * Added a "Duplicate connection" option in Terminal's right-click contextual menu
  * Added righ-click context menu to "Prepend command" entry box to fill with environment/local/global PAC variables
  * Modified the connection's "Copy/Paste" code to change the TAB title accordingly with the new connection name
  * Fixed some global/local/environment variables not being properly updated on connected client
  * Added options under "Preferences" -> "PAC Main Options" and individually for every Terminal to modify both the USERNAME loging regexp and the PASSWORD regexp!!
  * Added some user/password expect strings
  * Little GUI modification for global 'Preferences' UI

- 2.5.5.1:

  * Fixed a minor bug that prevented any old-PAC-configured terminal from being opened where it should (TAB or Window)
  * Added righ-click context menu to IP, Port, User and Password entry boxes to fill with local/global PAC variables
  * Added a splash screen (optional) to PAC startup (it's not that PAC takes too long to start but, you know, it's not as *fast* as older versions... ;)
  * Modified the Alt+C/N behavior over Terminals to *toggle* connection list visibility

- 2.5.5:

  * Added the possibility to embed "RDesktop" (RDP) windows in PAC's TABS!!
  * Added a new "generic" connection method: launch *any* command you want (xdg-open mypicture.jpg, or /usr/bin/firefox http://www.google.com, for example!)
  * Added the possibility to choose a default/perl-profile new connections window size and launch mode (TAB/Windowed)
  * Little GUI modification to clarify the "Proxy" option in "Preferences", previeweing "System proxy" (if any!)

- 2.5.4.4:

  * Solved a bug that made PAC "eat" one CPU when closing a still connected TAB
  * Added an option to hide the most-bottom buttons

- 2.5.4.3:

  * Added a highly demanded option to 'Prepend command' (eg. add the string 'tsocks' to the beggining of the connecting string)
  * Added options to the "cu" method

- 2.5.4.2:

  * Added an option to 'auto hide' the 'connections list' in order to have more horizontal space
  * Moved the "Close tab button (X)" to the right side of tabs (Gnome-compliant??)
  * Ultra-low code cleanup
  * First release with RPM package format at Sourceforge

- 2.5.4.1:

  * Fixed a bug regarding executing terminals from the right-click menu on tray

- 2.5.4:

  * Major code changes: now, event-based Socket-UNIX (file-based) communication between started terminals and PAC main GUI (better performance, cleaner code!)
  * Code improvements: now, 0% CPU usage in PAC when idle (before, it was at least 5% or more!)
  * Added an option to keep every saved session log (by putting '0' -zero- in the "max log files to keep" entry box)
  * Added "per-terminal" save session log option policies
  * Added the possibility to use a description for local/remote macros
  * Added "listen mode" and "view only" mode to VNC connections
  * Fixed a minor bug regarding the Clusters GUI
  * Removed the right-click option to "Go to TAB..." (did anybody use that??)
  * Minor code changes (enhancements)

- 2.5.3:

  * Added the posibility to save more than one screenshot per connection
  * Also, added a mechanism to purge unused picture files from the screenshots folder
  * The screenshots zone accepts drag-and-drop of picture files
  * Modified the screenshots code to save the choosen screenshots with their original size, and for opening them full-sized when 'left-click' over the picture
  * Possibility to choose the tool to open the "clicked" screenshot (internal built-in gui or external application)
  * A little modification to the routine that checks for any other PAC process running

- 2.5.2:

  * Added a right-click option for connections to send a 'magic packet' in order to make a "Wake On LAN" test port reachability
  * Added an option (disabled by default) under "Preferences" to probe server's connection port before connecting
  * Added an option so auto-save every session log  to t user-defined folder
  * Added an option to put TABs at Top, Bottom, Left or Right side of the tabbed window
  * Added Alt+N to do the same as Alt+C: show the connectin window
  * Added an option to allow only one instance of PAC running at the same time (enabled by default)
  * Fixed a micro-bug that prevented the BPP rdesktop option from being correctly read from the config file
  * Modified the "Save" buttons from "Preferences" and "Edit Connection" to save AND close the window

- 2.5.1:

  * Added a right-click option over the "Terminal" to change the TAB title temporarly
  * Added an option to manually choose the size (width x height) for the RDP sessions
  * Removed a bug that prevented copying/renaming/moving the "Connections" from the connections treeview (may fault, MY FAULT! :)
  * Removed a bug that prevented the correct saving of the log file!!
  * OMG!! Removed a bug that prevented launching a connection using the "Connect" button (among other problems...)
  * RDP protocol had a bug, which prevented it from being used!!

- 2.5:

  * Added support for RDP (rdesktop and VNC (vncviewer): some people asked me for it; so, here it is!
  * Global variables in main "Preferences", eg.: write down a password once, use it ANY where, centralizing its modification for faster changes!
  * Added a righ-click menu entry over terminals to show the list of available connections
  * Added a new color for "unfocused terminal activity" (*blue* by default)
  * Revamped "Find..." dialog for terminals: now a textbox appears containing the full output, highlighting when double-clicked the selected matching lines!
  * Revamped "Preferences" dialog
  * Added a little icon different for every kind of connection (ssh, telnet, ...)
  * Fixed a micro-bug that prevented setting the terminal scrollback beyond 19999 (now it is up to 99999 but, really, *don't use that much of scrollback!!*)
  * Removed the option to save session log for "local shells" (did not work at all!)
  * Modified the code for "Save session log", since it did not work before!!

- 2.4.1.7:

  * Added an option to use a Black & White icon in Tray
  * Added an option to choose the Connected and Disconnected TAB label colours
  * Added a GUI option to "Forward Agent" on SSH connections
  * Modified Ctrl+W to Ctrl+Shift+W keyboard shortcut to close terminal (Gnome-compliant shortcut)
  * Added Ctrl+Shift+Q keyboard shortcut to close PAC (Gnome-compliant shortcut)
  * Solved little bug that prevented splitting "Vertically" the "Local Shell"
  * Little GUI modification for "Preferences" dialog

- 2.4.1.6:

  * Added de abbility to split HORIZONTALLY and VERTICALLY
  * Added an option on right-click menu on Terminals to allow to reset and clear terminal settings
  * Added Ctrl+W keyboard shortcut to close terminal (Gnome-compliant shortcut)
  * Added a "Close" button to "LOCAL SHELL" tab
  * Added some missing right-click features for "Local Shell" terminal
  * Modified the default behaviour of TABs: now they are in the main window by default (for *new* installations!)

- 2.4.1.5:

  * Readded a "Close" button to every TAB
  * Now, TAB's titles will be RED on disconnected and DARK-GREEN for connected ones (icon has been removed)
  * Changing a TAB makes the "Environment" and "Connection" update to new focused TAB
  * Modified the tooltip for the "Advanced Options" entry in SSH config GUI (required use of '"', eg: -o "PreferredAuthentications=password")

- 2.4.1.4:

  * Added "Remote Port Forwarding" SSH options to GUI
  * GUI modifications to make some 'entry boxes' smaller
  * Fixed a little regression bug regarding multiple connections selection
  * Added a couple of password pattern matching localizations (Spanish and German)

- 2.4.1.3:

  * Fixed a bug regarding the Advanced Options in SSH configuration
  * GUI modification to allow a smaller size of main window (for los resolution/screens)

- 2.4.1.2:

  * Now, every "Hidden" (and "Password") fields are encrypted (Crypt::CBC + Crypt::Blowfish) in the config file
  * Added an entry to the tray menu to start a "Local Shell"
  * Fixed a minor bug regarding the "Cluster" window

- 2.4.1.1:

  * Guess what? A new bug regarding a newly created 'local shell' was corrected

- 2.4.1:

  * Added a button to start a local shell
  * Added a button to launch local commands on editing window
  * Added option to directly detach tabbed terminal and go fullscreen with F11
  * Added a tooltip for "ENVIRONMENT VARIABLES" shown when editing a connection

- 2.4.0.4:

  * Fixed a GUI-micro-bug regarding local/remote command in terminals
  * Added an option to start PAC main window ( not only the terminals windows) maximized
  * Modified the Terminal to get keyboard focus when "middle-clicking" (paste) with mouse
  * Modified the position of the screenshot frameand the minimal size of the main window to fit in smaller screens

- 2.4.0.3:

  * Fixed some bugs regarding split/tab/cluster/...
  * Fixed a bug that prevented the main window to be shown when "Start Iconified" was choosen
  * Fixed a minor bug that showed the "Local" and "Remote" commands in terminals even if no action was configured

- 2.4.0.2:

  * Fixed a bug that prevented showing the right-click contextual menu under some circunstances
  * Fixed a couple of minor bugs regarding "Screenshots"
  * 1 or 2 *millions* of bugfixes with tabs/splits (Yeah! You know! This is PAC! ;)

- 2.4.0.1:

  * Fixed a bug regarding detach/reattach + splitting terminals

- 2.4:

  * Added the option to *SPLIT HORIZONTALLY* two terminals in a same window!
  * Some libraries cleanup and code reorganization

- 2.3.4.2:

  * Fixed a couple of minor gui bugs

- 2.3.4.1:

  * Added a "Terminal Transparency" option for terminals

- 2.3.4:

  * Added the possibility to modify some 'per-terminal' options: command prompt, timeouts, colours, ...

- 2.3.3:

  * Added an option to embed the tabbed terminals window into Main PAC window
  * Added 'Full screen' option for the Terminals (`F11`)
  * Solved a bug that made a connection failing when connecting and resizing the terminal at the same time
  * Fixed a couple of minor GUI glitches

- 2.3.2:

  * Added a "Take Screenshot" option to make/show a screenshot of every connection
  * Added a command 'History' (`Alt+H`) in the Terminal window for user commands
  * Migrated the config file '~/.pac.yml' to new config dir '~/.pac/'
  * Minor code improvements and bug fixes

- 2.3.1.3:

  * Fixed some bugs regarding specific 'Method' options (you know: new GUI -> new BUGS, that's PAC !! ;)
  * Added some checks for not allowing the entering of non numeric values in numeric Gtk Entry boxes

- 2.3.1.2:

  * Fixed a bug that did not allow to configure "Advanced Options" in 'ssh' connection method

- 2.3.1.1:

  * Fixed a regression bug regarding Telnet and FTP default ports

- 2.3.1:

  * Fixed a bug that prevented every tab other than the 'Method' specific one from being showed! (that Notebook Gtk widget is a little tricky!!)

- 2.3:

  * NEW revamped GUI! Now, every 'Method' for connecting has its own GUI that (finally!!) simplifies the process of configuring
		every connection. No more 'use that text box to put the command line options you want'.
		That is, the differente GUIs allow you to (depending on the method, of course):
			. forward local ports in SSH
			. create local dynamic sockets
			. click to enable/disable flag options
			. etc.
  * Fixed a minor aesthetical bug

- 2.2.1:

  * Added the possibility to edit a connection on-line with realtime updates to GUI (<alt>-e or right-click menu item)
  * Added Ctrl+Ins to copy and Shift+Ins to paste (beyond Ctrl+Shift+C / Ctrl+Shift+V)
  * Fixed a bug with default Telnet && FTP ports!
  * Fixed a bug that prevented PAC from checking for the 'Username: ' string when waiting for login username input.
  * Fixed a bug that prevented a disconnected terminal from being added to a Cluster

- 2.2:

  * Added a GUI to administrate CLUSTERS in realtime.
  * Code improvements (more objects!).
  * Fixed bug that allowed to type in a disconnected terminal and propagate those keypressed to the rest of members in the cluster.
  * Fixed some minor GUI glitches.
  * Code cleanup + improvements.

- 2.1.2.2.1:

  * Fixed a bug that prevented any "Port" modification from being saved.

- 2.1.2.2:

  * Added the possibility to select any number or connections and execute/delete them.
  * Added some code for softly close connections on tab/window close.

- 2.1.2.1:

  * Fixed a couple of minor bugs with "Clustered Connections"
  * Fixed a couple of other minor bugs.

- 2.1.2:

  * CLUSTER connections implemented!! Put any number of connections into a Cluster group, and any command given in any of those terminals will be replicated to all the members in the cluster!!
  * Many bugfixes and GUI glitches.

- 2.1.1.3.1:

  * Fixed *terrible* bug when closing "Tabbed terminals" window!!

- 2.1.1.3:

  * Fixed regression bug that prevented "Description" from being saved.
  * Fixed regression bug that made "Copy/Cut/Paste" fail on "Expect" properties tab.
  * Little improvements on Expect engine's disconnection routine.

- 2.1.1.2:

  * Added the logic to detect "changes" in configuration, allowing for manual/automatic saving, and advertising of exit without saving.
  * Added a check routine to silently test config files at startup (good for version upgrades).
  * Little GUI speedup improvements.
  * More minor bugfixes.

- 2.1.1.1:

  * Added an "Edit Variables" menu entry to quickly modify connections' variables.
  * Minor bugfixes.

- 2.1.1:

  * Added a progressbar next to status bar to know how many 'expectations' there are before getting 'connected'.
  * Little GUI improvements.

- 2.1:

  * Added a status bar to the terminal to show connection status (with a tooltip that shows every step made to connect).
  * Added an option for local/remote commands to be confirmed before their execution.
  * Expect engine refined to allow more variables substitutions and avoid connection glitches.
  * Added option choose whether send (default) or not a "INTRO" keypress in 'Expect' commands.
  * Little GUI readjustment.
  * Minor bugs fixed.

- 2.0.1:

  * Implemented the "so-much-missed" "UNDO" (Ctrl-z)function for every 'text' widget: Variables, Description, etc.
  * Modified the "Search" function in Terminals to allow to cancel any active search (good for unexpected long time searches!)

- 2.0:

  * Well... I do not even know where to begin from!! ;)
  * NEW revamped GUI( more or less): "Simpler, Cleaner and Professional"(TM) ;)
  * Right click on automations provide context menus to fill in
  * Now user variables may contain runtime substitution variables (variables are becoming more powerful on every new release)
  * Added link from '/opt/pac/pac' to '/usr/bin/pac'
  * Restartable session from terminal's right click menu
  * TAB title moved from 'tweak' to connection options
  * Initial preliminary 'man' page!!! (see 'man pac', but do not expect too much by now)
  * 70% of code rewritten (more objects, less bugs, less glitches, funnier!! ;)

- 1.0:

  * Added the posibility to detach tabbed terminals into windows and viceversa !!
  * Revamped "find in terminal" GUI
  * Lots of code rewritten: more modularized, cleaner and faster
  * Recursively auto accept consecutive unknown ssh_hosts connections
  * Added a new set of user defined variables (next to 'OPTIONS' frame) where you can define some connection related variables in order to simplify the modification of pre/post/local/remote/expec options
  * Complete new filesystem architecture: no more use of standard Linux directories: now, everything goes into '/opt/pac'
  * Tweak TAB/window title by putting `<TAB_TITLE:your new title:TAB_TITLE>` anywhere in 'Description'
  * Added autonomous '.tar.gz' package: if you do not want or can not use any pre-built instalable (RPM or DEB), simply unpack 'pac-x.y-all.tar.gz' in your favourite directory and run 'pac' inside the new directory
  * Game over for 'Undo'. I give up (for now). Terrible bugs made me take this decision
  * Many little GUI improvements: icons, correct sizes, etc
  * Minor bugfixes (wrong handling of some `Ctrl` keypresses in terminals)

- 0.9.6.6:

  * Added "search" capability to the Terminal (Ctrl+F3, or right-click menu): a new window will popup with matching lines.
  * Minor code bugfixes: some `Ctrl+key` combinations resulted in corrupted keyboard mappings.

- 0.9.6.5:

  * Added cursor shape selection: block, underline, ibeam

- 0.9.6.4:

  * Added right-click mouse menu for copy/cut/paste/delete full Expect entries

- 0.9.6.3:

  * Implemented Expect executions mobility!!

- 0.9.6.2:

  * Added Terminal right-click option to save terminal's session output

- 0.9.6.1:

  * Bugfixed: added dependency for 'cu' and 'remote-tty'

- 0.9.6:

  * Modified GUI to use a combobox for supported connections methods

- 0.9.5:

  * Added connection checkbox to avoid any expect automation and let the user interact since the begining of authentication
  * Substituted 'trash' icon in Expect notebook tab by a checkbox to use or not that expect in a quick/non-destructive way
  * Changed some GUI updates to avoid some *not-so-brand-new* bug... ;)
  * Minor code improvements

- 0.9.4.2:

  * Added `<<ENV:variable_name>>` for both local and remote commands:  
    substitute this string (`<<ENV:variable_name>>`) for user's given environments 'variable_name' (eg: `export DISPLAY=<<ENV:DISPLAY>>`)

- 0.9.4.1:

  * Added connection support for:
		'sftp',
		'[p]ftp',
		'cu' (experimental!),
		'remote-tty' (experimental!)

- 0.9.4:

  * Right click on Terminal also allows to launch local/remote macros!
  * Some GUI cleanup and fixing
  * Added .rpm packages for gnome's vte dependency (untested!!) in both 32 and 64 bit flavours

- 0.9.3:

  * Removed 'gtkitemfactory' dependency (deprecated) for right click popup menus. Instead, use 'popupmenu' function from Quentin Sculo <squentin@free.fr> (see 'gmusicbrowser', amazing Perl/GTK music organizer!!)
  * Improvements in right popup menus GUI
  * Added tooltip for tray icon menu (shows connection description)
  * PAC's connection engine modified to detect invalid usernames when login
  * Minor code improvements

- 0.9.2:

  * Fixed bug that preventes font type to be taken into account
  * Added right mouse click pop menu for connections list
  * Code cleanup

- 0.9.1:

  * Removed 'escape' key minimizes
  * Added option to minimize instead of closing
  * Fixed som minimizing bugs

- 0.9:

  * Moveable TABS
  * 'UNDO' routine cleanup and bugfix

- 0.8.2:

  * Closing with middle-click on a tab results in closing any other tab *but* the one to be closed!!!
  * 'undo' enhancements and bugfixes

- 0.8.1:

  * Regression bug for selecting tabs with mouse clicks
  * Regression bug when copying/pasting connection

- 0.8:

  * 'UNDO' routine fully implemented (but be careful when using it! ;)
  * Connections 'Cut/Copy/Paste' also fully implemented (TONS of bugfixes!!)
  * TABS selection GUI on terminal improved
  * More code cleanup

- 0.7:

  * Lots of code cleanup!
  * Now only 'PAC Config' window is rendered throught GLADE (everything else is hand made)
  * Environment renaming working again
  * Removed default `<QUICK>` environment/connection
  * Some GUI improvement
  * Many bugfixes

- 0.6.1:

  * Keypress on terminal bugfixes (many) for Ubuntu >= 9.10
  * Some code cleanup

- 0.6:

  * Fixed *terrible* regression bugs: pre/post executions
  * Removed file 'pac_terminal.glade'. Now every terminal widget is hand made! ;)
  * More bugfixes

- 0.5:

  * Icons to close tabs
  * Added tab right-click mouse button menu (copy, paste, change tab and close terminal)
  * TONS of bugfixes for scrolled windows

- 0.4:

  * TABS !!! Now you can choose if new connections must go tabbed in main window or in new ones (navigate the same way you do with gnome-terminal)
  * Minor bugfixes

- 0.3:

  * Added terminal fore/background color ( default = white text over black background ) and font ( default = monospace 9 ) selection support
  * Local & remote execution prompt user for substitution of variables like `<<var_1>>`, `<<var_2>>` and so on
  * Resized trayicon art
  * Bugfixes

- 0.2:

  * Complete code rewrite (now, object oriented from top to bottom!)
  * Removed 'libgtk2-trayicon-perl' dependency
  * Added trayicon information about running connections
  * Moved '/etc/pac.yml' file to '$HOME/.pac.yml'
  * Bugfixes
  * More things I just can't remember right now... ;)


# KNOWN BUGS

Find them for yourself... ;)


# EASTER EGGS

For sure!!! Just figure out the 'Kode' and 'place' to be used! ;)


# FAQ

Q: Why did you started programming this 'little monster'? Could you not simply use *ssh in a terminal*, or *putty for linux*? Eh? Couldn't you?  
A: Hell! NO!! Just take a look at PAC and *tell me* whether you find or not these features in any other piece of Linux software!
	And yes, I wanted a GUI to manage my 'zillion' of connections to administrate servers in my IT job.
	And that GUI should be nice/quick enough as to be usable, and I think I got it! Just let me know!
	(Really: it is 'priceless' to have an intuitive GUI that helps you start with a simple click from the systray a connections that ssh's to one machine, autologins, executes something, then ssh's from that machine to another, autologin again, and finally brings a third machine remote ports locally to my laptop)

Q: Why 'PAC'? It sounds terribly awful and... welll... it sucks!!  
A: You are in reason. In fact, you *should* propose me a *better* name for it...

Q: Why in the world is this piece of cr*p (I mean, 'software') written in Perl language? Is not there any uglier/older/unfashinable language?  
A: I'm glad you ask so. Perl is the only language I know. And I like it.
	And you *should* like it too. You ALL should give *love* to this adorable language by Larry Wall.
	Oh, and no, there is no older or uglier or what-ever-you-ask-for language to program with.

Q: Your programming style sucks! When are you gonna learn to program like human beings?  
A: Since I do not think of myself as a human being, I do not feel the necesity to learn such a thing (despite I know for sure *that* would be great!)

Q: For God's love, I really hate you and the way you program!  
A: That's not a question, but anyway, I do also hate MY programming style
	(believe me, now I am slacking my face and pressing my nipples strongly in order to punish myself for being such a bad programmer! ;)

Q: Anyway, now that I'm used to it, I'm wondering how *often* will you upload new versions. Could you tell me, please?  
A: Well, you know, I AM 'too old', 'too married' and 'too father' as to have *enough* time as to be modifying PAC every day, so... well...mmm...
	NO IDEA!

Q: Oohh... so many questions...  why 'YAML', why 'Gnome2:Vte', why...???  
A: Blah blah blah... shut the f**k up and simply use it if you dare!! ;)
 

# LICENSES
  
PAC uses Gnome2::Vte (http://search.cpan.org/CPAN/authors/id/X/XA/XAOC/Gnome2-Vte-0.11.tar.gz) without modifications, providing a binary set of files in order to help those Linux distros without them.
