# stack-repl-mixin

This is a reproducer for https://github.com/commercialhaskell/stack/issues/5077.

To reproduce the issue, use

```
$ stack repl non-base-prelude
...
/home/simon/src/serokell/stack-repl-mixin/non-base-prelude/src/Lib.hs:1:8: error:
    Ambiguous module name ‘Prelude’:
      it was found in multiple packages:
      base-4.13.0.0 morley-prelude-0.3.0
  |
1 | module Lib where
  |        ^^^
Failed, no modules loaded.
...
```

or 

```
$ stack repl relude-as-prelude
...
/home/simon/src/serokell/stack-repl-mixin/relude-as-prelude/src/Lib.hs:3:6: error:
    Not in scope: type constructor or class ‘Text’
  |
3 | t :: Text
  |      ^^^^
Failed, no modules loaded.
...
```
