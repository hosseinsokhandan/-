# Record Syntax
It is an alternative way to write data types.


### Why
- Beautiful is better than ugly.
- Explicit is better than implicit.
- Readability counts.
- Automatic built-in look-up functions.


### Example

Definition:

```hs
data Car = Car String String Int deriving (Show)
data Car = Car {company :: String, model :: String, year :: Int} deriving (Show)
```


Making a new car:
```hs
Car {company="Ford", model="Mustang", year=1967}

```


Automatic lookup functions:
```hs
ghci> let car = Car {company="Ford", model="Mustang", year=1967}
ghci> model car
"Mustang"
ghci> year car
1967
```
