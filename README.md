# Thunderbird (Flathub)

org.mozilla.Thunderbird (aka net.thunderbird.Thunderbird)

[Thunderbird](https://www.thunderbird.net/) for [Flatpak](https://flatpak.org/)
installation instructions are available on the
[Thunderbird app listing at Flathub](https://flathub.org/apps/details/org.mozilla.Thunderbird).

## Known issues

Non-Flatpak packaging issues should be
[reported upstream](https://bugzilla.mozilla.org/describecomponents.cgi?product=Thunderbird).

### Migration from pre-exisiting non-Flatpak installations

In order to migrate your profile from an existing non-Flatpak installation and
preserve all settings, please copy or move the entire **`~/.thunderbird`**
directory into **`~/.var/app/org.mozilla.Thunderbird/.thunderbird`**.

In case Thunderbird opens a new profile instead of the existing one, use the
terminal to execute `flatpak run org.mozilla.Thunderbird -P`, then select the
right profile and confirm that **"Use the selected profile without asking on
startup"** is checked.

### Language support

- [&lsqb;#3&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/3)
  All supported locales are available from the `org.mozilla.Thunderbird.Locale`
  Flatpak extension. One locale that matches the host OS locale will be
  installed and selected by default. For instructions on how to enable more
  locales for your Flatpaks, visit the
  [Flatpak configuration](https://flatpak.readthedocs.io/en/latest/flatpak-command-reference.html#flatpak-config)
  documentation.

- [&lsqb;#90&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/90)
  Dictionary availability is much the same, however they can also be downloaded
  manually from
  [Thunderbird.net](https://addons.thunderbird.net/language-tools/) and
  installed from the
  [Menu Bar](https://support.mozilla.org/kb/display-thunderbird-menus-and-toolbar)
  > `Tools` > `Add-ons` > `Extensions` > `Install Add-on From File`. You will
  need to restart the app in order to finalize the installation.

### New mail notifications

- [&lsqb;#11&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/11#issuecomment-531987872)
  To enable new mail notifications:
  1. [Menu Bar](https://support.mozilla.org/kb/display-thunderbird-menus-and-toolbar)
     > `Edit` > `Preferences` > `Advanced` > `General` > `Config Editor…`, and
     set **`mail.biff.use_system_alert`** to **`true`** (default), or
  1. [Menu Bar](https://support.mozilla.org/kb/display-thunderbird-menus-and-toolbar)
     > `Edit` > `Preferences` > `General` > `Customize…` at "Show an alert" and
     set "Show New Mail alert for:".
- [&lsqb;#79&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/79#issuecomment-534298255)
  Alternatively, you may set **`mail.biff.use_system_alert`** to **`false`**,
  which will make notifications non-native, but clicking on them will open the
  mail item in Thunderbird.

### Wayland

- [&lsqb;#75&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/75)
  To enable the experimental [Wayland](https://wayland.freedesktop.org/)
  compositor backend (assuming the desktop session is also Wayland), execute:
  `flatpak override --user --env=MOZ_ENABLE_WAYLAND=1 org.mozilla.Thunderbird`.

### Smartcard

- [&lsqb;#51&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/51)
  For SmartCard support, you need to be running Flatpak v1.3.2 or newer.

## Other Flatpak issues unresolved yet by upstream

- [&lsqb;#123&rsqb;](https://github.com/flathub/org.mozilla.Thunderbird/issues/123)
  Opening the Profile Directory doesn't work
  ([upstream bug report](https://bugzilla.mozilla.org/show_bug.cgi?id=1625111)).
