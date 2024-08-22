# Mac-related tips, issues and fixes

## Brew Install without Fetching Auto Updates

```bash
$ HOMEBREW_NO_AUTO_UPDATE=1 brew install <formula>
```

## Adding Dividers to Mac Dock
I found this useful because I prefer to split my minimised windows based on the projects / tasks I am working on.

![Mac Dock Spacer Example](../img/MacDockSpacer.png)

For example, in the screenshot above, I added two spacers to the right side of my dock, visually splitting my windows by projects.

```bash
# note that this adds a spacer to the right side of your dock
# if you want to add a spacer to the left side of the dock, follow the next block of code instead
$ defaults write com.apple.dock persistent-others -array-add '{tile-data={}; tile-type="spacer-tile";}'

# it is necessary to restart your dock once you add the spacers
$ killall Dock
```

If you want to add a spacer to the left hand side instead:

```bash
$ defaults write com.apple.dock persistent-apps -array-add '{tile-data={}; tile-type="spacer-tile";}'

$ killall Dock
```