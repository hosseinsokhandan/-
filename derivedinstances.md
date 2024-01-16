# Derived instances
A typeclass is a sort of interface that defines some behavior.\
If a type is part of a typeclass, that means that it supports and implements the behavior the typeclass describes.


## Eq
Defines behavior for stuff that can be equated. Mostly with `==`, `/=`, and `elem`.

```hs
ghci> 4 == 4
True
ghci> "foo" /= "bar"
True
```

## Ord
It is for types that have values that can be ordered. Mostly with `>`, `<`, and `compare`. \
If we compare two values of the same type that were made using different constructors, the value that was made with **a constructor that's defined first is considered smaller**.

Given:
```hs
ghci> data Bool = False | True deriving (Ord) 
```
Then:
```hs
ghci> True `compare` False  
GT  
ghci> True > False  
True  
ghci> True < False  
False 
```


## Show
Defines behavior for stuff that can be converted to a string.

```hs
ghci> let mikeD = Person {firstName = "Michael", lastName = "Diamond", age = 43}  
ghci> mikeD  
Person {firstName = "Michael", lastName = "Diamond", age = 43}  
ghci> "mikeD is: " ++ show mikeD  
"mikeD is: Person {firstName = \"Michael\", lastName = \"Diamond\", age = 43}"
```


## Read
It is for converting strings to values of our type.

```hs
ghci> read "Person {firstName =\"Michael\", lastName =\"Diamond\", age = 43}" :: Person  
Person {firstName = "Michael", lastName = "Diamond", age = 43}
```

## Enum
The Enum typeclass is for things that have predecessors and successors.

Given:
```hs
data Day = Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday  
           deriving (Eq, Ord, Show, Read, Enum)
```
Then:
```hs
ghci> pred Tuesday
Monday
ghci> succ Monday
Tuesday
ghci> read "Saturday" :: Day  
Saturday
ghci> [Thursday .. Sunday]
[Thursday,Friday,Saturday,Sunday]
```


### Bounded
It is for things that have the lowest possible value and highest possible value.

Given:
```hs
data Day = Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday  
           deriving (Eq, Ord, Show, Read, Bounded, Enum)
```
Then:
```hs
ghci> minBound :: Day  
Monday  
ghci> maxBound :: Day  
Sunday 
```
