# Record Syntax

### Example

Definition:
```hs
ghci> data Car = Car {company :: String, model :: String, year :: Int} deriving (Show)

```


Making a new car:
```hs
ghci> Car {company="Ford", model="Mustang", year=1967}

```


Automatic lookup functions:
```hs
ghci> let car = Car {company="Ford", model="Mustang", year=1967}
ghci> model car
"Mustang"
ghci> year car
1967
```
