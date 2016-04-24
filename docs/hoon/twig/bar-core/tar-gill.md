---
sort: 6
---

# `:gill, |*, "bartar", {$gill p/moss q/seed}`

Form a gill, a wet one-armed core with payload `{sample context}`.

## Expands to

```
:new   p
:core
+-  $
  q
--
```

## Syntax

Regular: *2-fixed*.

## Discussion

In a normal (dry) gate, your argument is converted into the
sample type.  In a generic (wet) gate or gill, your argument type
passes through the function, rather as if it was a macro (there
is still only one copy of the code, however).

Genericity is a powerful and dangerous tool.  Use gills only if
you think you know what you're doing. 

## Examples

Wet and dry gates in a nutshell:

```
~zod:dojo> =foo :gate({a/* b/*} [b a])
~zod:dojo> =bar :gill({a/* b/*} [b a])
~zod:dojo> (foo %cat %dog)
[6.778.724 7.627.107]
~zod:dojo> (bar %cat %dog)
[%dog %cat]
```

The dry gate does not preserve the span of `a` and `b`; the wet
gate does.