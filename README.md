# Functional programming babelfish

This is an attempt to provide a link and comparision between similar concepts and operations and their usage between different functional programming languages
. When learning and working with different languages and concepts, it's nice to have an easy way of looking up the implementations.

Please contribute! I am not an expert in these languages. Please contribute to improvements with PR's and issues to help improve this reference.

# Cheat sheet - condensed overview
(See below for more languages and details)

| Concept | Name | Purescript | Haskell | Elm | F# |
----------|------|------------|---------|-----|----|
Forward function application|Apply/Pipe|```#, applyFlipped```|```&```|```|>```|```|>```|
Function application|Apply/Pipe|```$, apply```|```$```|```<|```|```<|```|
Composition|Forward/right|```>>>, composeFlipped```|```>>>```|```>>```|```>>```|
Composition|Backward/left|```<<<, compose```|```.```|```<<```|```<<```|
Unit type|Empty|```Unit```|```()```|```()```|```()```|
Anonymous function|Lambda|```\x -> x + 1```|```\x -> x + 1```|```\x -> x + 1```|```fun x -> x + 1```|
Identity function||```id```|```id```|```identity```|```id```|
Tuple|Definition|```Tuple a b```|```(Int, String)```|```(Int, String)```|```int * string```|
Tuple|Usage|```Tuple 2 "Test"```|```(2, "Test")```|```(2, "Test")```|```(2, "Test")```|
Record types||```data Point = Point { x :: Int, y :: Int}```|``` data Point = Point { x :: Int, y :: Int}```|```type alias Point = { x : Int, y : Int}```|```type Point = { x : int; y : int}```|
Union types||<code>data Shape Circle Point Int &#124; Line Point Point</code>|<code>data Shape = Circle Point Int &#124; Line Point Point</code>|<code>type Shape = Circle Point Int &#124; Line Point Point</code>|<code>type Shape = Circle of Point * int &#124; Line of Point * Point</code>|
Maybe / Option||<code>data Maybe a = Just a &#124; Nothing</code>|<code>data Maybe a = Just a &#124; Nothing</code>|<code>type Maybe a = Just a &#124; Nothing</code>|<code>type Option<'a> = &#124; Some of 'a &#124; None</code>|
Either / Result||<code>data Either a b = Left a &#124;  Right b</code>|<code>data Either a b = Left a &#124;  Right b</code>|<code>type Result error value = Ok value &#124; Err error</code>|<code>(in F# 4.1) type Result<'T,'TError> = &#124; Ok of 'T &#124; Error of 'TError</code>|
Functor map|Map|```<$>, map```|```<$>, fmap```|```map```|```map```|
Functor apply|Apply|```<*>, apply```|```<*>```|``` ```|```apply ```|
Functor lift||```liftN```|``` liftN```|```mapN```|```mapN```|
Bind||```>>=, bind```|```>>=```|```andThen```|```bind```|
Pattern matching||``` ```|``` ```|``` ```|``` ```|
Let In /Where||``` ```|``` ```|``` ```|``` ```|
Lists||``` ```|``` ```|``` ```|``` ```|
Concat||``` ```|``` ```|``` ```|``` ```|
||``` ```|``` ```|``` ```|``` ```|

# Concepts
## Function application
### Forwards function application / Piping

| Language | Syntax |
|----------|--------|
Purescript | ```# ```
Haskell | ```& ```
Elm | ```|> ```
F# | ```|> ```


#### Notes/links
* [http://stackoverflow.com/questions/1457140/haskell-composition-vs-fs-pipe-forward-operator](http://stackoverflow.com/questions/1457140/haskell-composition-vs-fs-pipe-forward-operator)
```
F#
( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let result = 100 |> function1 |> function2
202

Elm
(|>) : a -> (a -> b) -> b
result = 100 |> function1 |> function2
202

```
### Backwards function application / Backward Piping

| Language | Syntax |
|----------|--------|
Purescript | ```# ```
Haskell | ```$ ```
Elm | ```|> ```
F# | ```|> ```


#### Notes/links
* [https://docs.microsoft.com/en-us/dotnet/articles/fsharp/language-reference/functions/index](https://docs.microsoft.com/en-us/dotnet/articles/fsharp/language-reference/functions/index)
* [https://docs.microsoft.com/en-us/dotnet/articles/fsharp/language-reference/symbol-and-operator-reference/](https://docs.microsoft.com/en-us/dotnet/articles/fsharp/language-reference/symbol-and-operator-reference/)

```
Purescript:
apply :: forall a b. (a -> b) -> a -> b
apply f x = f x
street (address (boss employee))
street $ address $ boss employee

Haskell:
($) :: (a -> b) -> a -> b
F x = f x

F#: Passes the result of the expression on the right side to the function on left side
( <| ) : ('T -> 'U) -> 'T -> 'U
(backward pipe operator)
street (address (boss employee))
street <| address <| boss employee
```

Todo: More details for other concepts. Also happy to receive help with other languages.

### Unit type
### Anonymous function
### Identity function
### Tuple
### Record types
### Union types
### Maybe / Option
### Either / Result
### Functor map
### Functor apply
### Functor lift
### Bind
### Pattern matching
### Let In /Where
### Lists
### Concat

------------------------
### (Template)

| Language | Syntax |
|----------|--------|
Purescript | ``` ```
Haskell | ``` ```
Elm | ``` ```
F# | ``` ```
Elixir | ``` ```


#### Notes/links
* []()
* []()

### Other sites with related content
[https://github.com/hemanth/functional-programming-jargon](https://github.com/hemanth/functional-programming-jargon)
