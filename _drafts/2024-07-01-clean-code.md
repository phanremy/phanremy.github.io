---
layout: post
title: Du Code Propre
categories: Code
description: Sans Smells
keywords: Code
---

"Clean Code: A Handbook of Agile Software Craftsmanship" de Robert C. Martin, souvent appelé Uncle Bob, est un ouvrage de référence en ingénierie logicielle. Il met l'accent sur l'importance d'écrire un code propre, maintenable et efficace. Voici les principaux points à retenir du livre :

1. Noms Significatifs
Descriptifs et Non Ambigus : Choisissez des noms de variables, de fonctions et de classes qui décrivent clairement leur objectif.
Prononçables : Utilisez des noms faciles à prononcer et à communiquer.
Recherchables : Optez pour des noms faciles à trouver dans la base de code.
2. Fonctions
Petites et Focalisées : Les fonctions doivent être petites et ne faire qu'une seule chose.
Un Seul Niveau d'Abstraction : Assurez-vous que chaque fonction opère à un seul niveau d'abstraction.
Noms Descriptifs : Les noms de fonctions doivent clairement indiquer leur but.
Minimiser les Effets Secondaires : Les fonctions doivent éviter de causer des effets secondaires.
3. Commentaires
Seulement Quand Nécessaire : Utilisez les commentaires avec parcimonie et uniquement pour expliquer pourquoi quelque chose est fait, pas ce qui est fait.
Code Auto-Documenté : Visez à écrire du code qui s'explique de lui-même, réduisant ainsi le besoin de commentaires.
4. Formatage
Style Consistant : Maintenez un style et un format de code cohérents dans toute la base de code.
Lisibilité : Le code doit être formaté pour améliorer la lisibilité, en utilisant une indentation et un espacement appropriés.
5. Gestion des Erreurs
Utiliser des Exceptions, Pas des Codes d'Erreur : Préférez les exceptions pour la gestion des erreurs plutôt que les codes d'erreur.
Séparation des Préoccupations : Gérez les erreurs séparément de la logique principale.
Dégradation Gracieuse : Assurez-vous que le système peut gérer les erreurs de manière gracieuse et continuer à fonctionner.
6. Classes
Principe de Responsabilité Unique (SRP) : Chaque classe ne doit avoir qu'une seule raison de changer.
Encapsulation : Gardez les détails de l'implémentation cachés et exposez uniquement ce qui est nécessaire.
Cohésion : Assurez-vous que toutes les méthodes et variables d'une classe sont liées et travaillent ensemble pour remplir la responsabilité de la classe.
7. Objets et Structures de Données
Abstraction des Données : Cachez la représentation interne des données.
Dites, Ne Demandez Pas : Les objets doivent dire aux autres objets quoi faire, plutôt que de demander des données puis d'agir en conséquence.
8. Tests Unitaires
Tests Automatisés : Écrivez des tests automatisés pour garantir la correction du code.
Couverture des Tests : Visez une couverture de test élevée pour couvrir divers cas limites et scénarios.
Tests Lisibles : Les tests doivent être aussi lisibles et maintenables que le code qu'ils testent.
9. Mauvaises Odeurs de Code (ou Code Smells)
Reconnaître et Refactoriser : Apprenez à reconnaître les mauvaises odeurs de code (mauvais motifs de code) et à les refactoriser pour améliorer la qualité du code.
Amélioration Continue : Refactorisez régulièrement le code pour le garder propre et maintenable.
10. Pratiques Agiles
Développement Itératif : Développez des logiciels de manière itérative, en apportant de petites améliorations incrémentales.
Collaboration : Favorisez la collaboration entre les membres de l'équipe pour améliorer la qualité et la conception du code.
Retour d'Information du Client : Cherchez et intégrez continuellement les retours d'information des clients.
En adhérant à ces principes et pratiques décrits dans "Clean Code", les développeurs peuvent écrire un code plus compréhensible, maintenable et évolutif, ce qui conduit finalement à un logiciel de meilleure qualité.
