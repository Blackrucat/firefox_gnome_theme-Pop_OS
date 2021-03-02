<h1 align="center">
	<img src="icon.svg" alt="Firefox GNOME Pop!_OS! theme" width="100" height="100"/><br>
 Firefox GNOME theme
</h1>

<p align="center"><strong>A Firefox GNOME Pop!_OS! theme</strong></p>

<p align="center">Active tab.</p>

![image](https://user-images.githubusercontent.com/56588184/109405529-43fe0e80-7950-11eb-8a10-ff67d707d46a.png)

<p align="center">Inactive tab.</p>

![image](https://user-images.githubusercontent.com/56588184/109405697-ed91cf80-7951-11eb-86eb-783b934db9df.png)


<p align="center">This theme follows lastest GNOME Pop!_OS style.</p>



## Description

This is a bunch of CSS code to make Firefox look closer to GNOME's Pop!_OS! native apps.

This theme is supposed to work with current supported Firefox releases:

- Firefox 85
- Firefox 78 ESR
- Firefox 86 Beta
- Firefox 87 Nightly

## Installation
1 - Download the files and extract them

![image](https://user-images.githubusercontent.com/56588184/109405937-cfc56a00-7953-11eb-879e-56231aeef139.png)

2 - search `about:profile` on your browser URL bar
3 - find out which profile is being used on firefox and the copy or open the root folder

![image](https://user-images.githubusercontent.com/56588184/109405887-6cd3d300-7953-11eb-947b-0075afa2d54d.png)

4 - if it doesn't exist create a folder called `chrome` inside of the firefox root folder
5 - Put those tree files on the root folder 

![image](https://user-images.githubusercontent.com/56588184/109405759-aeb04980-7952-11eb-834f-151585a857ca.png)
''
6 - search `about:config` on your browser URL bar and then set toolkit.legacyUserProfileCustomizations.stylesheets to true (default is false)

![image](https://user-images.githubusercontent.com/56588184/109700673-d4b33500-7b70-11eb-9899-2e91e27d08a2.png)

7 - restart firefox or open if it's closed 



## Scrollbars
To achieve Firefox with overlay scrollbars install [firefox-gnome-scrollbars](https://github.com/rafaelmardojai/firefox-gnome-scrollbars).

## Enabling optional features
Optional features can be enabled by creating new `boolean` preferences in `about:config`.

1. Go to the `about:config` page 
2. Type the key of the feature you want to enable
3. Set it as a `boolean` and click on the add button
4. Restart Firefox

### Features

- **Hide single tab** `gnomeTheme.hideSingleTab`

	Hide the tab bar when only one tab is open.

	> **Note:** You should move the new tab button somewhere else for this to work, because by default it is on the tab bar too. See [#54](https://github.com/rafaelmardojai/firefox-gnome-theme/issues/54).

- **Normal width tabs** `gnomeTheme.normalWidthTabs`

	Use normal width tabs as default Firefox.

- **Active tab contrast** `gnomeTheme.activeTabContrast`

	Add more contrast to the active tab.

- **System icons** `gnomeTheme.systemIcons`

	Use system theme icons instead of Adwaita icons included by theme.

	> **Note:** This feature has a [known color bug](#icons-color-broken-with-system-icons).

- **Symbolic tab icons** `gnomeTheme.symbolicTabIcons`

	Make all tab icons look kinda like symbolic icons.

- **Drag window from headerbar buttons** `gnomeTheme.dragWindowHeaderbarButtons`

	Allow draging the window from headerbar buttons.

	> **Note:** This feature is BUGGED. It can activate the button with unpleasant behavior.

## Known bugs

### CSD have sharp corners
See upstream [bug](https://bugzilla.mozilla.org/show_bug.cgi?id=1408360).

#### Wayland fix:
1. Go to the `about:config` page
2. Search for the `layers.acceleration.force-enabled` preference and set it to true.
3. Now restart Firefox, and it should look good!

#### X11 fix:
1. Go to the `about:config` page 
2. Type `mozilla.widget.use-argb-visuals`
3. Set it as a `boolean` and click on the add button
4. Now restart Firefox, and it should look good!

### Icons color broken with System icons
Icons might appear black where they should be white on some systems. I have no idea why, but you can adjust them directly in the `system-icons.css` file, look for `--gnome-icons-hack-filter` & `--gnome-window-icons-hack-filter` vars and play with css filters.

## Development

If you wanna mess around the styles and change something, you might find these
things useful.

To use the Inspector to debug the UI, open the developer tools (F12) on any
page, go to options, check both of those:

- Enable browser chrome and add-on debugging toolboxes
- Enable remote debugging

Now you can close those tools and press Ctrl+Alt+Shift+I to Inspect the browser
UI.

Also you can inspect any GTK3 application, for example type this into a terminal
and it will run Epiphany with the GTK Inspector, so you can check the CSS styles
of its elements too.

```sh
GTK_DEBUG=interactive epiphany
```

Feel free to use any parts of my code to develop your own themes, I don't force
any specific license on your code.

## Credits
Developed by **[Rafael Mardojai CM](https://github.com/rafaelmardojai)** and [contributors](https://github.com/rafaelmardojai/firefox-gnome-theme/graphs/contributors). Based on **[Sai Kurogetsu](https://github.com/kurogetsusai/firefox-gnome-theme)** original work.

## Donate
If you want to support development, consider donating via [PayPal](https://paypal.me/RafaelMardojaiCM). Also consider donating upstream, [Firefox](https://donate.mozilla.org/) & [GNOME](https://www.gnome.org/support-gnome/).
