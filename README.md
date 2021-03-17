# purescript-learning

## Spago
This is the package manager for `purescript`. Just like `npm` is the package manager for `node`.
Usefull commands:
```
spago build - compiles and builds
spago test - runs the tests
spago install <package> - installs a package
```

## Types
Basics: `Number`, `Int`, `String`, `Char`, `Boolean` <br/>
Arrays&Lists: `Array a`, `List a` <br/>
You can define a custom type:
```
type CustomType
  { property1 :: String
  , propety2 :: Int
  , property3 :: SomeOtherCustomType
  }
```
You would then instantiate:
```
record = { property1: 'SomeValue', property2: 3, property3: {...} }
```

## Functions
Function definition: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`add :: Int -> Int -> Int` <br/>
Function declaration: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`add x y = x + y` <br/>
Inline function declaration: &nbsp;&nbsp;&nbsp;&nbsp;`\x y -> x + y` <br/>
Calling a function: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum = add 5 7` <br/>
<br/>
In purescript one would say that functions are `applied` to arguments. Each function has exactly 1 argument. After applying it, the result can be another function. This is called `currying`.<br/>
So you could do this:
```
add5To = add 5
sum = add5To 7
```
`add5To` is a function of type `Int -> Int` that resulted after `partially applying` `add` to `5`. You can the apply `add5To` to any number and you would get the sum of that number and `5`. <br/>

### Property accessor functions
Instead of:
```
getName :: Person -> String
getName person = person.name

bobsName = getName bob
```
you ca do:
```
bobsName = _.name bob
```
You don't need to define the function, you can use the property accessor shortcut.
