# Windows Desktop Rules

## Supported target
The product may target WPF or WinUI, but desktop-native behavior must be preserved.

## DPI matrix
Always reason about 100/125/150/175/200% scaling. Prefer layout that can grow naturally instead of hard-coded pixel geometry.

## WPF warning areas
- Grid/Auto/Star sizing interactions
- ScrollViewer nested around virtualized lists
- DataGrid virtualization disabled by templates
- TextBox/ComboBox height mismatches from local styles
- inherited Foreground causing invisible text
- popup placement on scaled secondary monitors
- Window.SizeToContent misuse
- synchronous Dispatcher work
- event subscriptions preventing GC

## WinUI warning areas
- XamlRoot missing for dialogs/flyouts
- ThemeResource vs StaticResource misuse
- unsupported Windows 11 effects on Windows 10
- ContentDialog lifecycle
- NavigationView compact/expanded state
- packaged/unpackaged behavior differences

## Windows 10 fallback
Never make Windows 11-only visual material necessary for task comprehension. If advanced backdrops are unavailable, fall back to solid surfaces with correct contrast.

## Desktop input
Mouse and keyboard remain primary. Do not inflate every control to touch-first proportions unless the product actually has touch requirements.

## Chinese typography
Test mixed Chinese/Latin/numeric strings, especially:
- DataGrid headers
- buttons
- tree nodes
- ComboBox items
- dialogs
- print status
- finance totals
- file paths
