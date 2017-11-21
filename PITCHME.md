<!-- $theme: gaia -->
<!-- template: invert -->

<img src="assets/images/haskell-paris.jpeg" width="307" align="right"/>

# Lazy evaluation
## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

---

<img src="assets/images/haskell-paris.jpeg" width="307" align="right"/>

# Lazy evaluation

## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

* La 5e dimension
* Les astuces (1<sup>e</sup> partie)
* Les 


---

# La 5e dimension

```Haskell
  λ❯ let xs = [1..1000000000] :: [Int]
  xs :: [Int]

  λ❯ :sprint xs 
  xs = _

```
---

# La 5e dimension

```Haskell
  λ❯ let xs = [1..1000000000] :: [Int]
  xs :: [Int]

  λ❯ :sprint xs
  xs = _

```

Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement


---

# La 5e dimension

```Haskell
  λ❯ let xs = [1..1000000000] :: [Int]
  xs :: [Int]

  λ❯ :sprint xs
  xs = _

```

Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement
 

:arrow_right: Cette liste à un milliard d'éléments ne sera peut-être jamais allouée en mémoire ! 🎉

