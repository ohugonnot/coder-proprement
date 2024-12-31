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

## Nommage

| **Principe**                      | **Description**                                                                                              | **Exemple**                                                                                                       |
|-----------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Noms significatifs                | Utiliser des noms explicites pour refléter leur rôle et intention.                                          | `calculateTotalPrice()` au lieu de `calcTP()`.                                                                    |
| Pas d'abréviations obscures       | Éviter les abréviations qui ne sont pas évidentes ou standard.                                               | `userCount` au lieu de `uCnt`.                                                                                    |
| Cohérence des conventions         | Adopter un style de nommage cohérent dans tout le projet.                                                   | Utiliser camelCase ou snake_case de manière uniforme.                                                             |
| Éviter la désinformation          | Ne pas utiliser des noms qui pourraient induire en erreur sur leur fonction ou contenu.                     | Mauvais : `list` pour une file. Bon : `queue`.                                                                    |
| Faire des distinctions significatives | Ne pas utiliser des noms trop similaires qui peuvent prêter à confusion.                                    | Mauvais : `data1`, `data2`. Bon : `userData`, `transactionData`.                                                  |
| Prononçables                      | Les noms doivent pouvoir être lus ou prononcés facilement.                                                  | `generatedTransaction` au lieu de `genVarTxn`.                                                                    |
| Compatibles avec une recherche    | Choisir des noms qui facilitent la recherche dans le code.                                                  | `temporaryFile` au lieu de `tmp`.                                                                                 |
| Éviter la codification            | Ne pas utiliser des notations désuètes comme la notation hongroise.                                          | Mauvais : `strUserName`. Bon : `userName`.                                                                        |
| Noms des classes                  | Donner des noms qui reflètent des objets ou concepts du domaine métier.                                      | `InvoiceManager` au lieu de `DoStuff`.                                                                            |
| Noms des méthodes                 | Utiliser des verbes ou phrases verbales pour les noms des méthodes.                                          | `fetchData` ou `saveUser`.                                                                                        |
| Un mot par concept                | Utiliser le même terme pour désigner un même concept dans tout le projet.                                    | Ne pas mélanger `fetch` et `retrieve` pour des opérations similaires.                                             |


------------------------------------

## Fonctions

| **Principe**                       | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Faire court                        | Les fonctions doivent être courtes pour rester lisibles et faciles à comprendre.                                                | Fractionnez une fonction longue en plusieurs petites fonctions.                                                  |
| Faire une seule chose              | Chaque fonction doit se concentrer sur une seule tâche bien définie.                                                            | Séparez la validation et la sauvegarde dans deux fonctions distinctes.                                           |
| Un niveau d’abstraction par fonction | Chaque fonction doit opérer à un seul niveau d’abstraction (bas, moyen ou élevé).                                                | Créez une fonction intermédiaire quand il y a if ou un for qui peut être isolé.                             |
| Lire le code de haut en bas        | Organisez le code pour qu’il soit lisible comme une histoire : du général au particulier.                                        | Implémentez une fonction principale qui appelle des sous-fonctions bien définies.                                |
| Instruction switch                 | Évitez des blocs `switch` complexes ; préférez des mappings ou des stratégies pour simplifier.                                   | Utilisez un tableau associatif pour mapper les types d’utilisateur à leurs tableaux de bord.                     |
| Arguments limités                  | Réduisez le nombre d’arguments par fonction (idéalement 2 ou 3 maximum).                                                        | Séparez les arguments booléens en fonctions spécifiques, passer des arguments de type est une mauvaise idée.                    |
| Éviter les effets secondaires      | Une fonction ne doit pas modifier l’état global ou des variables inattendues.                                                   | Passez les dépendances comme paramètres plutôt que d’utiliser des variables globales.                            |


------------------------------------

## Commentaires

| **Principe**                | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Commentaires pertinents     | Écrire des commentaires pour expliquer les "pourquoi" et non les "quoi".                                                        | Mauvais : `// Itère sur les utilisateurs`.<br>Bon : `// Vérifie que tous les utilisateurs ont confirmé leur e-mail.` |
| Préférer un code explicite  | Réécrire le code pour qu'il soit compréhensible sans nécessiter de commentaire.                                                  | Remplacer un commentaire par une fonction nommée explicitement.                                                  |
| Ne pas compenser le mauvais code   | Refactorisez le code au lieu de le couvrir par des commentaires explicatifs inutiles.                                            | Utilisez des noms de variables clairs au lieu d'un commentaire.                                                  |
| Clarifier ou avertir des conséquences | Ajoutez des commentaires pour indiquer des impacts critiques ou inattendus.                                                     | `// Ne pas modifier cette valeur critique.`                                                                       |
| Commentaires TODO                 | Utilisez-les pour signaler des tâches ou des améliorations à effectuer.                                                          | `// TODO: Implémenter la gestion des erreurs pour les cas limites.`                                              |
| Éviter les commentaires trompeurs  | Assurez-vous que les commentaires reflètent la réalité du comportement du code.                                                  | Mauvais : `// Vérifie les utilisateurs actifs` si le code ne fait pas cela.                                      |
| Éviter trop d’informations         | Ne surchargez pas les commentaires avec des détails inutiles.                                                                    | Concentrez-vous sur les points essentiels.                                                                       |


------------------------------------

## Mise en forme

| **Principe**                       | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Métaphore du journal               | Organisez le code comme un journal : informations clés en haut, détails en bas.                                                 | Placez les fonctions principales en haut, les fonctions utilitaires en bas.                                      |
| Espacement vertical des concepts   | Ajoutez des espaces verticaux entre des blocs logiques pour améliorer la lisibilité.                                             | Ajoutez des lignes vides entre les fonctions ou sections logiques.                                               |
| Concentration verticale            | Groupez les éléments liés proches les uns des autres dans le fichier.                                                           | Regroupez des fonctions qui partagent une logique ou une dépendance.                                             |
| Distance verticale                 | Réduisez la distance entre une déclaration et son utilisation.                                                                   | Placez une variable proche de son utilisation.                                                                   |
| Rangement vertical                 | Structurez le code dans un ordre logique : variables, fonctions principales, fonctions auxiliaires.                              | Placez les déclarations importantes en premier.                                                                  |
| Cohérence de style          | Utiliser un style de codage uniforme (indentation, espacement, etc.) pour toute l'équipe.                                        | Tous les développeurs doivent adopter la même convention (par exemple, deux espaces pour l'indentation).         |


------------------------------------

## Objets et structures de données

| **Principe**                       | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Abstraction de données             | Cachez les détails d’implémentation et exposez uniquement une interface claire.                                                  | Utilisez des getters et setters au lieu d’accéder directement aux propriétés.                                     |
| Antisymétrie données/objets        | Les objets encapsulent des comportements, les structures exposent des données.                                                  | Une classe `User` avec `hasPermission()` vs. une structure `UserData` avec des champs.                            |
| Loi de Déméter                     | Un objet ne doit interagir qu’avec ses dépendances immédiates.                                                                   | Évitez les chaînes d’appels longues comme `$order->getCustomer()->getAddress()->getCity()`.                       |
| Catastrophe ferroviaire            | Évitez les chaînes d’appels excessives et fragiles.                                                                              | Regroupez des appels complexes dans une méthode unique.                                                           |
| Hybrides                           | Évitez de mélanger des comportements et des données exposées.                                                                    | Séparez clairement les objets des structures de données.                                                          |
| Cacher la structure                | Ne révélez pas la structure interne d’un objet ; exposez des méthodes abstraites.                                                | Utilisez `getCity()` au lieu de `$user->address->city`.                                                           |
| Objets de transfert de données (DTO) | Utilisez des structures simples pour transférer des données entre les couches.                                                   | Une classe `UserDTO` avec des champs publics pour transporter les données.                                        |
| Enregistrement actif               | Une structure de données avec des méthodes pour interagir avec la base de données.                                              | Une classe `User` avec des méthodes `save()` et `delete()`.                                                       |


------------------------------------

## Gestion des erreurs

| **Principe**                | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Utiliser des exceptions     | Préférer lever des exceptions pour les cas d’erreurs plutôt que d’utiliser des codes de retour.                                  | `throw new IllegalArgumentException("Paramètre invalide");` au lieu de retourner `-1`.                           |
| Pas de capture silencieuse  | Ne pas ignorer les exceptions silencieusement ; loguer ou gérer les erreurs correctement.                                        | Mauvais : `try { ... } catch(Exception e) {}`<br>Bon : `try { ... } catch(Exception e) { log(e); }`              |
| Fail Fast (Échouer tôt)     | Faire échouer le programme dès qu’un état invalide ou une erreur grave est détectée.                                             | Valider les entrées utilisateur au début d’une fonction.                                                         |
| Écrire `try-catch-finally`         | Utilisez des blocs `try-catch-finally` pour traiter des opérations sensibles aux erreurs (e.g., accès aux fichiers).             |                                                                            |
| Fournir un contexte avec les exceptions | Ajoutez des détails spécifiques à l’erreur dans les messages d’exception pour faciliter le débogage.                           | `throw new InvalidArgumentException("Paramètre invalide : " . $param);`                                           |
| Classes d’exceptions spécifiques   | Définissez des classes d’exceptions personnalisées pour différents types d’erreurs.                                              | `FileNotFoundException`, `FilePermissionException`.                                                              |
| Définir le flux normal             | Utilisez des exceptions pour des cas exceptionnels, pas pour des flux normaux.                                                  | Utilisez un `if` pour gérer les utilisateurs introuvables plutôt qu’une exception.                                |


------------------------------------

## Limites

| **Principe**                       | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Utiliser du code tiers             | Intégrez des bibliothèques tierces seulement si elles sont bien maintenues et adaptées à vos besoins.                            | Préférez une solution native (`date()`) à une bibliothèque lourde.                                               |
| Explorer et apprendre les limites  | Étudiez les limites des outils et technologies que vous utilisez pour anticiper les problèmes.                                   | Identifiez quand passer à une base NoSQL pour des données hiérarchiques complexes.                               |
| Apprendre à utiliser les logs      | Configurez et exploitez des outils de journalisation pour le suivi et le débogage des applications.                              | Utilisez Monolog pour capturer et gérer des messages de log en PHP.                                              |
| Tests d’apprentissage              | Testez les bibliothèques ou concepts dans un environnement isolé avant de les intégrer.                                          | Créez un mini-projet pour explorer une bibliothèque de validation.                                               |
| Utiliser du code inexistant        | Concevez des abstractions avant les implémentations pour un code plus flexible et maintenable.                                   | Définissez une interface `PaymentGateway` avant de choisir un fournisseur.                                       |


------------------------------------

## Modularité

| **Principe**                      | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| SRP (Single Responsibility Principle) | Respecter le principe de responsabilité unique : une classe doit avoir une seule responsabilité clairement définie.              | Une classe `UserService` ne doit pas gérer les connexions à la base de données.                                  |
| Réduction des dépendances         | Minimiser les dépendances entre les modules pour améliorer la maintenabilité et la testabilité.                                  | Utiliser l'injection de dépendances au lieu de créer directement des instances dans les classes.                 |
| Favor Composition Over Inheritance | Préférer la composition à l’héritage pour une plus grande flexibilité et un couplage réduit.                                     | Injecter un objet `Engine` dans une classe `Car`, au lieu d’hériter de `Vehicle`.                                |
| LoD (Law of Demeter)              | Chaque module ou classe ne doit interagir qu’avec ses dépendances immédiates.                                                   | Fournir une méthode `getCityName()` au lieu de `user.getAddress().getCity().getName()`.                          |

------------------------------------

## Tests

| **Principe**                              | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Test Early, Test Often (Tester tôt et souvent) | Écrire des tests dès le début et valider chaque fonctionnalité régulièrement.                                                    | Rédiger un test avant même d’implémenter la fonction.                                                             |
| FIRST (Fast, isolated, repeatable, self-verifying, timely)                                     | Les tests doivent être rapides, indépendants, répétables, auto-vérifiants et écrits au bon moment.                               | Éviter les dépendances entre tests ou des tests nécessitant des bases de données complexes.                       |
| AAA (Arrange-Act-Assert)                 | Structurer les tests en trois étapes : Préparation (Arrange), Exécution (Act) et Vérification (Assert).                          |                                                         |
| Pyramid de tests                          | Priorisez les tests unitaires (rapides et nombreux), suivis des tests d’intégration, puis des tests end-to-end (plus rares).     | Évitez un excès de tests end-to-end qui ralentissent le développement.                                            |
| Mocking et Stubbing                      | Simulez des dépendances externes avec des mocks ou des stubs pour tester isolément votre logique métier.                         | `createMock(Service::class)->method('fetchData')->willReturn(['key' => 'value']);`                                |
| RED-GREEN-REFACTOR                       | En TDD, écrivez d’abord un test qui échoue (RED), faites-le passer (GREEN), puis améliorez le code (REFACTOR).                   | Implémentez une fonctionnalité minimale pour satisfaire un test avant d'optimiser.                               |
| Tests des limites       | Testez les cas limites, comme les listes vides, les valeurs nulles, ou les extrêmes.                                             | Calculer une moyenne pour une liste vide ou avec un seul élément.                                                |
| Don’t Test the Framework | Ne testez pas les fonctionnalités fournies par des bibliothèques ou le framework.                                               | Ne pas écrire un test pour vérifier si `strlen()` fonctionne correctement.                                       |
| Coverage                    | Assurez-vous que les tests couvrent les chemins critiques et les cas d’erreur, sans viser une couverture parfaite inutile.        | Vérifiez les scénarios principaux mais évitez de tester des getters et setters triviaux.                         |
| Data-Driven Testing                      | Utilisez des données dynamiques ou des fournisseurs de données pour couvrir plusieurs cas avec un seul test.                    | Fournir des cas comme `[100, 10, 90]` pour tester `calculateDiscount()`.                                         |


------------------------------------

## Classes

| **Principe**                       | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Organiser une classe               | Structurez les classes avec une logique claire : propriétés, méthodes publiques, puis privées.                                   | Voir l’exemple d’une classe `User` avec des propriétés et méthodes ordonnées.                                    |
| Encapsulation                      | Cachez les détails internes en utilisant des propriétés privées et exposez des méthodes publiques pour y accéder.                | Utilisez des getters et setters pour gérer les données d’une classe.                                             |
| De petites classes                 | Divisez les responsabilités complexes en plusieurs petites classes spécialisées.                                                 | Créez `OrderValidator`, `OrderProcessor` au lieu d’une seule classe `Order`.                                     |
| SRP (Principe de responsabilité unique) | Une classe doit avoir une seule raison de changer ; elle doit remplir une seule fonction ou responsabilité.                      | Séparez la génération de rapports (`ReportGenerator`) de leur enregistrement (`FileSaver`).                      |
| Cohésion                           | Les classes doivent regrouper des méthodes et propriétés fortement liées pour une tâche spécifique.                              | Une classe `Invoice` contient des méthodes comme `addItem()` et `calculateTotal()`.                              |
| Organiser en vue du changement     | Anticipez les évolutions futures en structurant les classes pour minimiser l’impact des modifications.                           | Utilisez des interfaces et appliquez le principe Open/Closed.                                                    |
| Cloisonner le changement           | Les changements dans une classe ne doivent pas affecter les autres parties du système.                                           | Injectez des dépendances comme `EmailService` pour éviter des dépendances rigides.                               |


------------------------------------

## Principes généraux

| **Principe**                | **Description**                                                                                                                  | **Exemple**                                                                                                       |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| DRY (Don’t Repeat Yourself) | Ne pas dupliquer le code ; privilégier la création de fonctions ou de classes réutilisables.                                     | Extraire une logique commune utilisée à plusieurs endroits dans une fonction `calculateDiscount()`.              |
| KISS (Keep It Simple, Stupid) | Garder les implémentations simples, sans complexité inutile.                                                                     | Éviter d'utiliser des patrons complexes ou abstraits si une boucle ou une condition suffit.                      |
| YAGNI (You Aren’t Gonna Need It) | Ne pas implémenter des fonctionnalités qui ne sont pas nécessaires immédiatement.                                               | Ne pas coder une logique complexe pour gérer un scénario hypothétique qui n'a pas encore de justification réelle. |
| Avoid Premature Optimization (Éviter l'optimisation prématurée) | Ne pas optimiser prématurément ; concentrez-vous d’abord sur la lisibilité et la clarté.                                         | N’optimisez une boucle que si elle a été identifiée comme 
| Avoid Magic Numbers (Éviter les constantes magiques) | Remplacer les constantes numériques par des noms explicites pour améliorer la lisibilité.                                        | Utiliser `const MINIMUM_AGE = 18;` au lieu de `if ($age > 18)`.                                                  |
| Immutabilité préférée              | Favoriser des objets ou des structures de données immuables pour éviter les effets de bord.                                      | Ne modifiez pas directement un tableau ; créez-en une copie modifiée.                                            |
| Concurrence maîtrisée       | Manipuler soigneusement les threads et processus concurrents pour éviter les conflits et les erreurs difficiles à déboguer.      | Utiliser des mécanismes comme `synchronized` ou des bibliothèques comme `java.util.concurrent`.                  |
| **S**ingle Responsibility Principle (SRP)     | Une classe doit avoir une seule responsabilité ou raison de changer.                                                             | Une classe `ReportGenerator` génère un rapport, tandis qu'une classe `ReportSaver` le sauvegarde.                |
| **O**pen/Closed Principle (OCP)               | Le code doit être ouvert à l'extension, mais fermé à la modification.                                                            | Ajoutez une nouvelle stratégie d’expédition dans une méthode sans modifier la classe principale.                  |
| **L**iskov Substitution Principle (LSP)       | Une classe dérivée doit pouvoir être utilisée partout où sa classe parente est acceptée, sans comportement inattendu.             | Une classe `Square` ne doit pas casser le comportement de la classe `Rectangle` si elle en hérite.               |
| **I**nterface Segregation Principle (ISP)     | Une classe ne doit pas être forcée d’implémenter des interfaces qu’elle n’utilise pas.                                           | Divisez une interface `Printer` en deux interfaces spécifiques : `ScannerInterface` et `PrintInterface`.          |
| **D**ependency Inversion Principle (DIP)      | Les modules de haut niveau ne doivent pas dépendre des modules de bas niveau ; les deux doivent dépendre d’abstractions.          | Utilisez une interface `NotificationSender` que les classes `EmailSender` et `SmsSender` implémentent.           |
