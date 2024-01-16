# Type notes
Some notes regarding types and typeclasses in Haskell.


### Type constructor vs Value constructor

It's crucial to distinguish between the type constructor and the value constructor.\
When declaring a data type, the part before the `=` is the type constructor, and the constructors after it (possibly separated by |'s) are value constructors


### Nullary value constructors

It's when all the value constructors take no parameters.

e.g.:
```hs
ghci> data Day = Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday
```


### Type parameter

It is the parameter that we define in the type constructor.\
For example, `a` is s type parameter.

```hs
data Maybe a = Nothing | Just a  
```

### Concrete type

When I apply an extra type to `Maybe`, like `Maybe String`, then I have a **concrete type**.\
**Values can only have types that are concrete types!**


### Type synonyms

Here's how the standard library uses type synonym to define `String` as a synonym for `[Char]`.

```hs
type String = [Char]
```
