# Lazy evaluation
## for the eager beginner

<small>Haskell Paris 29/11/2017</small>

---

### Sommaire

* La 5<sup>e</sup> dimension
* Point de cours
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

* Thunk
  Un pointeur vers un calcul qui ne s'effectuera que lorsqu'il sera demandé

* Gargage Collector
  La *garbage collection* est la gestion automatique du recyclage de la mémoire

---


