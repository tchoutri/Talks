# Lazy evaluation
## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

---

### Sommaire

* La 5<sup>e</sup> dimension
* Après l'effort, le réconfort


---

### La 5e dimension

```Haskell
λ❯ let liste = [1..1000000000] :: [Int]
xs :: [Int]

λ❯ :sprint liste 
xs = _

```
---
### La 5e dimension

* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement

---
### La 5e dimension

* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement

* ➡️ Cette liste à un milliard d'éléments ne sera peut-être jamais allouée en mémoire ! 🎉
---
### La 5e dimension

```Haskell
λ❯ take 5 liste
[1,2,3,4,5]
it :: [Int]
```
---
### La 5e dimension

```
λ❯ take 5 liste
[1,2,3,4,5]
it :: [Int]
λ❯ :sprint liste
liste = 1 : 2 : 3 : 4 : 5 : _
```
---


### Après l'effort, le réconfort
