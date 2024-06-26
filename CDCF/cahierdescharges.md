# Cahier des charges
lien : https://github.com/O-clock-Geri/S03-LocalExpress-JeremyDfr/blob/correction-j1/CDCF.adoc?plain=1
**Société**  localexpress

**Objectif** faire de la livraison de courses à domicile

## Description 

Nous voulons une application web qui permet de commander des produits et de se faire livrer à domicile. Nous ne vendons que quelques produits, qui changent chaque semaine. Il n'est pas nécessaire d'avoir d'historique de commande.

Pour nous démarquer, nous souhaitons :

- Une interface simple, sans navigation. Les produits sont tous sur la même page, simplement rangés par catégories (a-z).
- Compatible smartphone
- Nous privilégions le contact humain
    * paiement à la livraison
    * facture papier (non gérée par l'application)
    * le livreur fera du teasing sur les produits à venir

Nous n'avons pas de contrainte sur la technologie utilisée. Il nous faudra juste un back-office pour gérer les produits et voir les commandes.

## Interface

Voici une idée de l'interface que nous imaginons. Nous ne sommes pas designers, donc n'hésitez pas à nous proposer des améliorations, car nous aimons vos réalisations.

Page d'acceuil :

image::./assets/w1.png[interface]

Page de sélection des produits :

image::./assets/w2.png[interface]

Détail d'un produit :

image::./assets/w3.png[interface]

Finalisation d'une commande :

image::./assets/w4.png[interface]

Commande validée :

image::./assets/w5.png[interface]

## Maquettes et zonage

* Rouge : Header
* Orange : Main - Liste des produits
* Vert : Aside - Panier
* Violet : Footer

image::./assets/zonage.png[Zonage de la page principale]

## Conception

### User stories

En tant que client, je peux :

* voir les produits disponibles
* voir le détail d'un produit
* ajouter un produit dans mon panier
* modifier la quantité d'un produit dans mon panier
* supprimer un produit de mon panier
* vider mon panier
* voir le montant total de mon panier
* valider ma commande

En tant que commerçant, je peux :

* ajouter un produit
* modifier un produit
* supprimer un produit
* voir les commandes en cours

### Cas d'utilisation

```plantuml
include::./assets/usecase.puml[]
```

image::./assets/usecase.png[Diagramme de cas d'utilisation]

### Diagramme d'entité-association

```plantuml
include::./assets/erd.puml[]
```

image::./assets/erd.png[ERD]

### Diagramme de séquence

```plantuml
include::./assets/sequence.puml[]
```

image::./assets/sequence.png[Diagramme de séquence]

### Diagramme d'activité

```plantuml
include::./assets/activity.puml[]
```

image::./assets/activity.png[Diagramme d'activité]

### Diagramme de déploiement


```plantuml
include::./assets/deployment.puml[]
```

image::./assets/deployment.png[Diagramme de déploiement]

### Schéma d'architecture

```plantuml
include::./assets/architecture.puml[]
```

image::./assets/architecture.png[Diagramme d'architecture']