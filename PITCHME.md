# Lazy evaluation
## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

---

## La 5e dimension

---

### La 5e dimension

```Haskell
λ❯ let liste = [1..1000000000] :: [Int]
xs :: [Int]

λ❯ :sprint liste 
xs = _

```
---
* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement
---
* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement

* ➡️ Cette liste à un milliard d'éléments ne sera peut-être jamais allouée en mémoire ! 🎉
---
```Haskell
λ❯ take 5 liste
[1,2,3,4,5]
it :: [Int]
```

---

```Haskell
λ❯ take 5 liste
[1,2,3,4,5]
it :: [Int]
λ❯ :sprint liste
liste = 1 : 2 : 3 : 4 : 5 : _
```
---

### Point de cours

<dl>
<dt>Thunk</dt>
  <dd>Un pointeur vers un calcul qui ne s'effectuera que lorsqu'il sera demandé</dd>
<dt>Gargage Collector</dt>
  <dd>La *garbage collection* est la gestion automatique du recyclage de la mémoire</dd>
</dl>

---
### ⚠️ HALTE ⚠️

Le *GC* ne recyclera pas la liste si il reste un pointeur vers le début (*head*) de cette liste !

Cela se traduira en pratique par la conservation de la liste en mémoire, *no matter what*.

---

## En pratique

```Haskell
$ ghci +RTS -M100m
GHCi, version 8.0.2: http://www.haskell.org/ghc/  :? for help
Loaded GHCi configuration from /home/tchoutri/.ghci
λ❯ let liste = [1..10^6] :: [Int]
xs :: [Int]
λ❯ sum liste
<interactive>: Heap exhausted;
<interactive>: Current maximum heap size is 104857600 bytes (100 MB).
<interactive>: Use `+RTS -M<size>' to increase it.
```
@[1](On lance ghci en lui allouant 100Mo de mémoire vive)
@[4](On remplit la liste d'un milliard d'éléments)
@[6](On tente la somme)
@[7-9](☠️ RIP ☠️)

---

### T'as le sum ?

```Haskell
somme :: [Int] -> Int
somme []     = 0
somme (x:xs) = x + somme xs
```
---

### T'as le sum ?

```Haskell
somme [1..5]
➡️ 1 + somme [2..5]
➡️ 1 + (2 + somme [3..5])
➡️ 1 + (2 + (3 + somme [4..5]))
➡️ 1 + (2 + (3 + (4 + (5 + 0))))
```

@[1](On commence avec presque rien…)
@[5](… Et on fini par étirer l'accordéon !)

---

### Mais tout n'est pas perdu

```Haskell
$ ghci +RTS -M30m
GHCi, version 8.0.2: http://www.haskell.org/ghc/  :? for help
Loaded GHCi configuration from /home/tchoutri/.ghci
λ❯ Data.List.foldl' (+) 0 [1..10^6]
500000500000
it :: (Enum b, Num b) => b
```
@[1](On alloue 30Mo de RAM)
@[4](On retente l'expérience avec néanmoins l'utilisation de la version stricte de `foldl`)
@[5](On a notre résultat 🎉)

