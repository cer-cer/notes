- [《Flutter实战·第二版》](https://book.flutterchina.club/)
- [Dart keyword-static](https://www.geeksforgeeks.org/dart-static-keyword/)
- [flutter 实战](https://wizardforcel.gitbooks.io/gsyflutterbook/content/Flutter-1.html)





### FAQ
- Can't load App.Framework.  `Failed to find assets path for "flutter_assets"`.
  - “$FLUTTER_ROOT/packages/flutter_tools/bin/xcode_backend.sh” build
  - “$FLUTTER_ROOT/packages/flutter_tools/bin/xcode_backend.sh” embed
  - [Reference](https://github.com/flutter/flutter/issues/29974)

- Can't Hotreload.
  - 
  - [Reference](https://github.com/flutter/flutter/issues/61956)


- Flutter Native Crash analyze
  -  https://github.com/flutter/flutter/wiki/Crashes
  -  

- Dart VM pragma annotations
  - https://mrale.ph/dartvm/pragmas.html
  - https://mrale.ph/dartvm/

```
vm:entry-point	Defining entry-points into Dart code for an embedder or native methods
vm:never-inline	Never inline a function or method
vm:prefer-inline	Inline a function or method when possible
vm:notify-debugger-on-exception	Marks a function that catches exceptions, making the VM treat any caught exception as if they were uncaught. This can be used to notify an attached debugger during debugging, without pausing the app during regular execution.
vm:external-name	Allows to specify an external (native) name for an external function. This name is used to lookup native implementation via native resolver associated with the current library through embedding APIs. This is a replacement for legacy VM specific native "name" syntax.
vm:invisible	Allows to mark a function as invisible so it will not appear on stack traces.
vm:always-consider-inlining	Marks a function which particularly benefits from inlining and specialization in context of the caller (for example, when concrete types of arguments are known). Inliner will not give up after one failed inlining attempt and will continue trying to inline this function.
```
