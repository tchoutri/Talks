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
  <dd>Lier un processus (supervisé) à un autre processus (superviseur) à son démarrage</dd>
  <br />
<dt>Stratégie</dt>
  <dd>Le plan d'action qui va être mis en place à la mort d'un processus supervisé</dd>
</dl>

---

### Stratégies

<dl>
  <dt>`one_for_one`</dt>
    <dd>Tu meure, tu reviens à la vie</dd>
  <br />
  <dt>`one_for_all`</dt>
    <dd>Ta pote meure, t'es bonne pour y passer aussi :/</dd>
</dl>

---
### Stratégies 

<dl>
  <dt>`rest_for_one`</dt>
    <dd>C'est toi le facteur biologique, tous les poulets qui sont nés après toi vont passer à la trappe</dd>
  </br />
  <dt>`simple_one_for_one`</dt>
  <dd>Les processus vont démarrer et s'arrêter pendant l'execution de l'application, dans 30 secondes ou 10 ans.</dd>
</dl>

---

### Superviser son architecture

<img src="images/Superviser.png" width=600 height=500/>

---

## Renforcer son application

---

### Renforcer son application

* Lui donner une base stable

* Pratiquer un niveau d'isolation supérieur à la simple supervision ou aux acteurs

---

### Renforcer son application

OTP est une histoire de composants

---

### Renforcer son application

OTP est une histoire de composants

* Micro-composants
* Moyen-composants
* Macro-composants

@[1](Le processus, l'acteur)
@[2](L'application OTP)
@[3](Les regroupemments d'applications)


---

### *Fin*

Référence:

>Cesarini, Vinoski – Designing for Scalability with Erlang/OTP

Moi:
<img src="images/qrcode.jpg" width="250" align="right"/>
* @TechnoEmpress
* github.com/tchoutri

