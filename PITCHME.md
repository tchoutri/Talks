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

#### ⚠️ HALTE ⚠️

Le *GC* ne recyclera pas la liste si il reste un pointeur vers le début (*head*) de cette liste !

---

#### ⚠️ HALTE ⚠️

Le *GC* ne recyclera pas la liste si il reste un pointeur vers le début (*head*) de cette liste !

Cela se traduira en pratique par la conservation de la liste en mémoire, *no matter what*.

---


