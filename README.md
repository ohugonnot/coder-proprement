# coder-proprement

# L'idée fondamentale de "coder proprement"

Le concept de "coder proprement" repose sur les principes suivants pour faciliter la **lecture**, la **compréhension** et la **maintenabilité** du code :

## Principes fondamentaux

1. **Lisible**  
   Le code doit être clair et compréhensible sans nécessiter d'explications supplémentaires.  
   👉 Chaque développeur, même non initié au projet, devrait pouvoir comprendre facilement ce que le code fait et pourquoi il le fait.

2. **Réutilisable**  
   Le code doit être conçu pour être réutilisé dans différents contextes, évitant ainsi la duplication.  
   👉 Cela réduit les efforts de maintenance et limite les risques d'incohérence.

3. **Modulaire**  
   Les responsabilités doivent être **séparées** et **clairement définies**. Chaque fonction, classe ou module doit avoir une **responsabilité unique** (principe de responsabilité unique - SRP).  
   👉 Cela facilite la compréhension et permet d’effectuer des changements dans une partie sans affecter les autres.

4. **Facile à tester**  
   En structurant le code de manière modulaire et en isolant les dépendances, il devient plus facile d'écrire des tests unitaires et de valider le comportement du système.

5. **Simple**  
   Respecter le principe **KISS** ("Keep It Simple, Stupid") en évitant les solutions inutiles, complexes ou abstraites.  
   👉 Une solution simple et fonctionnelle vaut mieux qu'un design sophistiqué difficile à comprendre.

6. **Clair dans le flux logique**  
   Utiliser des techniques comme **early exit** ou **guard clauses** pour réduire l’imbrication des conditions et rendre le flux d’exécution linéaire.

7. **Documenté implicitement**  
   Privilégier des noms significatifs et un code bien structuré pour réduire le besoin de commentaires superflus.

## Pourquoi c'est important ?

- **Maintenance** : Un code propre est plus facile à mettre à jour, car il est compréhensible et bien organisé.
- **Collaboration** : Dans une équipe, un code propre limite les malentendus et permet à chaque membre de contribuer plus efficacement.
- **Fiabilité** : Un code lisible et bien testé réduit les erreurs et les bogues.
- **Évolution** : Les projets évoluent souvent. Un code propre permet d'ajouter de nouvelles fonctionnalités ou de modifier l'existant sans tout casser.

---

### En résumé

**Coder proprement**, c'est écrire un code **simple**, **clair**, **lisible**, **modulaire** et **maintenable**, en respectant des principes qui facilitent la collaboration, la réutilisabilité et la fiabilité du logiciel.

# Résumé : Principes pour coder proprement

# Résumé : Principes pour coder proprement

| **Catégorie**              | **Principe**                | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|----------------------------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| **Nommage**               | Noms significatifs          | Utiliser des noms explicites pour les variables, fonctions, classes, etc. pour refléter leur rôle et leur intention.             | `calculateTotalPrice()` au lieu de `calcTP()`                                                                    |
|                            | Pas d'abréviations obscures | Éviter les abréviations qui ne sont pas évidentes ou standard.                                                                   | `userCount` au lieu de `uCnt`                                                                                    |
| **Structure des fonctions** | Fonctions courtes           | Une fonction doit effectuer une seule tâche clairement définie.                                                                  | Une fonction `validateEmail()` ne doit pas gérer l’envoi d’un e-mail.                                            |
|                            | Early Exit                 | Quitter une fonction dès que les conditions sont remplies, plutôt que d’imbriquer plusieurs blocs conditionnels.                 | `if (x == null) return;` au lieu d’utiliser plusieurs `else` imbriqués.                                          |
|                            | Pas de code mort           | Supprimer tout code inutile ou non utilisé pour garder le code propre et lisible.                                                | Supprimer une fonction inutilisée qui est appelée nulle part.                                                    |
| **Commentaires**           | Commentaires pertinents     | Écrire des commentaires pour expliquer les "pourquoi" et non les "quoi".                                                        | Mauvais : `// Itère sur les utilisateurs`.<br>Bon : `// Vérifie que tous les utilisateurs ont confirmé leur e-mail.` |
|                            | Préférer un code explicite  | Réécrire le code pour qu'il soit compréhensible sans nécessiter de commentaire.                                                  | Remplacer un commentaire par une fonction nommée explicitement.                                                  |
| **Gestion des erreurs**    | Utiliser des exceptions     | Préférer lever des exceptions pour les cas d’erreurs plutôt que d’utiliser des codes de retour.                                  | `throw new IllegalArgumentException("Paramètre invalide");` au lieu de retourner `-1`.                           |
|                            | Pas de capture silencieuse  | Ne pas ignorer les exceptions silencieusement ; loguer ou gérer les erreurs correctement.                                        | Mauvais : `try { ... } catch(Exception e) {}`<br>Bon : `try { ... } catch(Exception e) { log(e); }`              |
| **Modularité**             | Classes bien structurées    | Respecter le principe de responsabilité unique : une classe doit avoir une seule responsabilité clairement définie.              | Une classe `UserService` ne doit pas gérer les connexions à la base de données.                                  |
|                            | Réduction des dépendances   | Minimiser les dépendances entre les modules pour améliorer la maintenabilité et la testabilité.                                  | Utiliser l'injection de dépendances au lieu de créer directement des instances dans les classes.                 |
| **Tests**                  | Écriture de tests unitaires | Vérifier chaque composant de manière isolée pour garantir sa fiabilité.                                                          | Écrire un test pour `calculateTotalPrice` qui vérifie que le calcul est correct pour différents cas d'entrée.     |
| **Style et mise en forme** | Cohérence de style          | Utiliser un style de codage uniforme (indentation, espacement, etc.) pour toute l'équipe.                                        | Tous les développeurs doivent adopter la même convention (par exemple, deux espaces pour l'indentation).         |
| **Performances**           | Concurrence maîtrisée       | Manipuler soigneusement les threads et processus concurrents pour éviter les conflits et les erreurs difficiles à déboguer.      | Utiliser des mécanismes comme `synchronized` ou des bibliothèques comme `java.util.concurrent`.                  |
| **Principe général**       | DRY (Don’t Repeat Yourself) | Ne pas dupliquer le code ; privilégier la création de fonctions ou de classes réutilisables.                                     | Extraire une logique commune utilisée à plusieurs endroits dans une fonction.              |
|                            | KISS (Keep It Simple, Stupid) | Garder les implémentations simples, sans complexité inutile.                                                                     | Éviter d'utiliser des patrons complexes ou abstraits si une boucle ou une condition suffit.                      |
|                            | YAGNI (You Ain’t Gonna Need It) | Ne pas implémenter des fonctionnalités qui ne sont pas nécessaires immédiatement.                                               | Ne pas coder une logique complexe pour gérer un scénario hypothétique qui n'a pas encore de justification réelle. |
|                            | Single Responsibility       | Chaque classe, fonction ou module doit avoir une seule responsabilité ou objectif clair.                                         | Une fonction qui génère un rapport ne doit pas aussi l'envoyer par e-mail.                                       |
                            |
