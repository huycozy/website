---
title: Component theme normalization
description: >-
  `CardTheme`, `DialogTheme`, `TabBarTheme` and `BottomAppBarTheme` have been normalized to follow
  Flutter's convention for component themes in the Material library.
---

## Summary

`CardTheme`, `DialogTheme`, `TabBarTheme` and `BottomAppBarTheme` were refactored to 
conform to Flutter's conventions for component themes.
`CardThemeData`, `DialogThemeData`, `TabBarThemeData` and `BottomAppBarTheme` were added to
define overrides for the defaults of the component visual properties.
Releases of Flutter continue to normalize component themes like these for
a more consistent theming experience in the material library.

## Migration guide

In `ThemeData`:

- The type of the `cardTheme` property has been
  changed from `CardTheme` to `CardThemeData`.
- The type of the `dialogTheme` property has been
  changed from the `DialogTheme` to `DialogThemeData`.
- The type of `tabBarTheme` property has been
  changed from `TabBarTheme` to `TabBarThemeData`.
- The type of `bottomAppBarTheme` property has been
  changed from `BottomAppBarTheme` to `BottomAppBarThemeData`.

The return type of the component theme `xTheme.of()` methods and
`Theme.of().xTheme` have also changed to `xThemeData` accordingly.

Code before migration:

```dart
final CardTheme cardTheme = Theme.of(context).cardTheme;
final CardTheme cardTheme = CardTheme.of(context);

final DialogTheme dialogTheme = Theme.of(context).dialogTheme;
final DialogTheme dialogTheme = DialogTheme.of(context);

final TabBarTheme tabBarTheme = Theme.of(context).tabBarTheme;
final TabBarTheme tabBarTheme = TabBarTheme.of(context);

final BottomAppBarTheme bottomAppBarTheme = Theme.of(context).bottomAppBarTheme;
final BottomAppBarTheme bottomAppBarTheme = BottomAppBarTheme.of(context);
```

Code after migration:

```dart
final CardThemeData cardTheme = Theme.of(context).cardTheme;
final CardThemeData cardTheme = CardTheme.of(context);

final DialogThemeData dialogTheme = Theme.of(context).dialogTheme;
final DialogThemeData dialogTheme = DialogTheme.of(context);

final TabBarThemeData tabBarTheme = Theme.of(context).tabBarTheme;
final TabBarThemeData tabBarTheme = TabBarTheme.of(context);

final BottomAppBarThemeData bottomAppBarTheme = Theme.of(context).bottomAppBarTheme;
final BottomAppBarThemeData bottomAppBarTheme = BottomAppBarTheme.of(context);
```

## Timeline

Landed in version: 3.32.0-1.0.pre<br>
Stable release: 3.32

## References

API documentation:

* [`ThemeData`][]
* [`CardTheme`][]
* [`DialogTheme`][]
* [`TabBarTheme`][]
* [`BottomAppBarTheme`][]

Relevant PRs:

* [Normalize ThemeData.cardTheme][]
* [Normalize ThemeData.dialogTheme][]
* [Normalize ThemeData.tabBarTheme][]
* [Normalize ThemeData.bottomAppBarTheme][]

[`ThemeData`]: {{site.api}}/flutter/material/ThemeData-class.html
[`CardTheme`]: {{site.api}}/flutter/material/CardTheme-class.html
[`DialogTheme`]: {{site.api}}/flutter/material/DialogTheme-class.html
[`TabBarTheme`]: {{site.api}}/flutter/material/TabBarTheme-class.html
[`BottomAppBarTheme`]: {{site.api}}/flutter/material/BottomAppBarTheme-class.html
[Normalize ThemeData.cardTheme]: {{site.repo.flutter}}/pull/153254
[Normalize ThemeData.dialogTheme]: {{site.repo.flutter}}/pull/155129
[Normalize ThemeData.tabBarTheme]: {{site.repo.flutter}}/pull/156253
[Normalize ThemeData.bottomAppBarTheme]: {{site.repo.flutter}}/pull/
