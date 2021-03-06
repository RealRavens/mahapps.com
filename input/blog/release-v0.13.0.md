Title: Release 0.13.0
Published: 4/10/2014
Category: Release
Author: punker76
---

# Notes

The 0.13 release of MahApps.Metro marks a very important change in the `MetroWindow` infrastructure along with several other fixes and improvements.

We've also updated the [MahApps.Metro.Resources NuGet package](http://www.nuget.org/packages/MahApps.Metro.Resources/) with the [latest icons](http://modernuiicons.com/).

# Features

## Custom themes

MahApps.Metro now allows to define custom themes for the application. We've rewritten the `ThemeManager` for this (don't worry, your old code should still work, but most old methods are now marked as `Obsolete`)

To add a theme, use the new `AddAppTheme` theme method.

## Completely rewritten `BorderlessWindowBehavior`

The `BorderlessWindowBehavior` has been completely rewritten, to fix a number of issues that have accumulated over time.

For a complete list of fixes, see PR #1156

## Auto-closing flyouts

Flyouts now have an option to be automatically closed when the user clicks outside of the flyout.
We renamed the property `IsPinnable` (that had no use) to `IsPinned` for this. 
`IsPinned` is `true` by default and, if set to false, enables the auto-closing feature.

## RangeSlider

The `RangeSlider` control has been completely rewritten because it was unusably broken before.

See PR #1055 for more info.

## Titlebar enhancements
- The titlebar now supports vector icons
- Added `LeftWindowCommands`
  This means that the normal `WindowCommands` property is now obsolete and is called `RightWindowCommands`
- The minimize/maximize/close button can now be styled
- Added ShowWindowCommandsOnTop property for window buttons #1098 (thanks @100GPing100)

## Others
- Added properties to change the font size of a tile #864 #1013
- Added support for `ToggleButton`s in the window commands #954
- Replace existing `RangeSlider` by new `RangeSlider` - #885 - see PR #920 / #1055 
- `Flyout`s' IsPinnable property doesn't seem to do anything - #866 - #1000 
- Tile Font size - #864 -> #1013 (@100GPing100)
- Update FlatSlider.xaml #858 (thanks @HansHuang)
- Auto-close flyout #962 - #1000 (thanks @100GPing100)
- Added the border to the visual studio styles. - #904 ( @punker76 ) PR #1140 
- Added `ButtonCommandMetroPasswordBox` ( @punker76 ) #993 PR #1097 
- Independently control dialog show/hide animation #1168 (@Savvkin)
- The expander control now has a disabled look #1266 #1267

# Fixes

- Fixed the external dialog not being cleaned up propely and crahsing the next dialog #994 #996
- Fixed various `MetroWindow` issues with multiple monitors #1099 #1136
- Fixed an `OverflowException` in the clean window #897
- Fixed issues with the airspace decorator #1077 #961
- Support `TextOptions.TextFormattingMode="Display"` #889
- Removed the unintended `FocusVisualStyle` from the window command buttons #833 #1012
- Fixed an `OverflowException` that could occur with multiple monitors #624 #1014
- Fixed various issues with the glow border #933 #936
- Fixed an `InvalidOperationException` occuring if a dialog was opened after an external dialog #994 #996
- Fixed the `FlatSlider` ignoring custom dimensions #858
- Fixed an `InvalidOperationException` occuring in the `GlowWindow` #1044
- Fixed various issues with the dialogs #1050
- Fixed a warning in the flyout's style #955 
- Fixed `MetroProgressBar` and `ProgressRing` issue Perfomance GPU" #812 
- Fixed `FlipView` HideBanner uses height, which is often NaN, should probably be ActualHeight instead #1053 
- Fixed the `Tile` static constructor. #1131 (thanks @maw136)
- Fixed after an upgrade to 0.11, title bar icon would have silver background instead of blue (accent). - #922
- Fixed GroupBox issue on flyout with the theme set to accent #1067 PR #1126 (thanks @Tide)
