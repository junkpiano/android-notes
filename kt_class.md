By default, kotlin classes are final - they can't be inherited.
To make a class inheritable, mark it with the `open` keyword:

```
open class Base // Class is open for inheritance
```

To declare an explicit supertype, place the type after a colon in the class header:

```
open class Base(p: Int)
class Derived(p: Int) : Base(p)
```

If the derived class has a primary constructor, the base class can(and must) be initialized
in that primary constructor according to its parameters.

If the derived class has no primary constructor, then each secondary constructor has to initizlize
the base type using the `super` keyword of it has to delegate to another constructor which does.
Note that in this case different secondary constructors can call different constructors of the base type:

```
class MyView: View {
    constructor(ctx: Context) : super(ctx)
    constructor(ctx: Context, attrs: AttributeSet) : super(ctx, attrs)
}
```
