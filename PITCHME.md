## Architectures Résilientes
## Avec Erlang/OTP et Elixir

<small>Vente Privée 08/12/2017</small>

---

### Sommaire: 

1. Modéliser son architecture

2. Superviser son architecture

3. Renforcer son architecture

4. Distribuer son architecture

---

## Modéliser son architecture

---

### Modéliser son architecture

>Hours of programming can save weeks of planning

---

### Modéliser son architecture

>Investir une heure de temps de cerveau peut épargner un mois de réécriture

---

### Modéliser son architecture

![](images/Modéliser.png)
---

### Le Worker, unité de base du modèle d'acteur

Il sait tout faire !

```
* Calculer fibonacci
* Envoyer des requêtes SQL
* Sérialiser du JSON
* Exposer un serveur web
* ➡️ Bam, Fibonacci As A Service!
```

@[1](Du calcul)
@[2](Garder un file descriptor en mémoire)
@[3](Ton client HTTP)
@[4](Ton format de données)
@[5](Ta prochaine startup !)

---

## Superviser son architecture

---

### Point de cours

<dl>
<dt>Superviser</dt>
  <dd>Lier un processus (superviser) à un autre processus (superviseur) à son démarrage</dd>
  <br />
<dt>Stratégie</dt>
  <dd>Le plan d'action qui va être mis en place à la mort d'un processus supervisé</dd>
</dl>

---

### Stratégies

* `one_for_one`  : Tu meure, tu reviens à la vie
* `one_for_all`  : Ton pote meure, t'es bonne pour y passer aussi :/
* `rest_for_one` : Tous les workers d'un arbre de supervision qui ont été déclarés et démarrés après le processus mort seront abattus aussi.
* `simple_one_for_one` : On démarre des processus au cours de l'execution du programme, dans 2 secondes ou 10 ans.

---

### Superviser son architecture

![](images/Superviser.png)

---



---

### *Fin*

Référence:

>Cesarini, Vinoski – Designing for Scalability with Erlang/OTP

Moi:
<img src="images/qrcode.jpg" width="250" align="right"/>
* @TechnoEmpress
* github.com/tchoutri

