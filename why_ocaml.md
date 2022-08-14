https://www.youtube.com/watch?v=v1CmGbOGb2I


### Languages
imperative vs functional 
static vs dynamic 

Financial distributions tend to be tail heavy
Really dramatic things happen rarely, but less rarely than you might think, but the have a large impact.
things do not conform to a normal distribution. 

There is an adversary in trading.
Someone is going to be acting against what you are trying to do.  

You want the power of the upside down A, Universal quantification (∀)
For all Cases, testing is one way of somewhat achieving that.

Type systems are a good tool for catching a large set of mistakes, 
and can help better represent the problem you are trying to solve.

### Mismatches in list 
return a list of keys that are in both dictionaries
with different data

```python 
def find_mismatches(d1,):
  mismatches = [];
  for (key,data) in d1.items():
    if data!= d2[key]:
      mismatches.append(key)
  return mismatches 
```

```ocaml
open Core.Std

let find_mismatches map1 map2 = 
  Map.to_sequence map1 
  |> Sequence.filter_map ~f:(fun (key,data)) -> 
    match Map.find map2 key with 
    | None -> None
    | Some data' ->
      if data' <> data then Some key 
      else None 
  )
```

```ocaml
type 'a expr = | True
               | False
               | And of 'a expr * 'a expr
               | Or of 'a expr * 'a expr
               | Not of 'a expr 
               | Base of 'a
// 'a is like generics in Java

let rec eval eval_base expr = 
  let eval' x = eval eval_base x in       // eval' (prime) is another function that knows about eval_base
  match expr with 
  | True      -> true
  | False     -> false
  | Base base -> eval_base base 
  | And (x,y) -> eval' x && eval' y
  | Or (x,y)  -> eval' x || eval' y
  | Not x     -> not (eval' x)
```

You can be a lot more expressive in the type system in ML languages.

### Dynamic range of the language 

### Teaching 
Rob Pike quote at google regarding new googlers not understanding a brilliant language
They need an easy language

### Hiring
Paul Graham - Quote about company choosing an esoteric language because then people that 
care enough to learn it, will likely be really good.

### Tools and Libraries

The tools are no good, and there arent that many libraries.
- opam        = Package management system for OCaml  
- merlin      = Intellisense auto completetion  
- ocp-indent  = Code formatting tool
- codoc       = Documentation format
- extension points  
  module aliases  = language features that make this all good   

Programming languages move slowly and irrationally
- Garbage collection was invented in 1958
- hit the main stream in 1995 with Java

The tools that you use in some ways form the way you think about and approach problems. 

Facebook wrote compilers Hack and Flow
Facebook uses Haskell as well
