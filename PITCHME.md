# Lazy evaluation
## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

---

### Sommaire

* La 5<sup>e</sup> dimension
* Les astuces (1<sup>e</sup> partie)


---

# La 5e dimension

```Haskell
  λ❯ let xs = [1..1000000000] :: [Int]
  xs :: [Int]

  λ❯ :sprint xs 
  xs = _

```
---
### La 5<sup>e</sup> dimension

* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement

---
### La 5<sup>e</sup> dimension

* Le `_` signifie que la variable `xs` n'a pas été évaluée par l'environnement

* :arrow_right: Cette liste à un milliard d'éléments ne sera peut-être jamais allouée en mémoire ! 🎉

---
