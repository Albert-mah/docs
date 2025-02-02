# v0.7.1 : 2022-06-26

## Fonctionnalités Fusionnées

- **chore(create-nocobase-app)** : Correction de certains bugs [`#538`](https://github.com/nocobase/nocobase/pull/538)
- **fix** : Destruction des champs de collection [`#536`](https://github.com/nocobase/nocobase/pull/536)
- **feat(plugin-workflow)** : Ajout d'un nouveau type de noeud "délai" [`#532`](https://github.com/nocobase/nocobase/pull/532)
- **refactor** : Refactorisation de l'application cliente [`#533`](https://github.com/nocobase/nocobase/pull/533)
- **fix** : Correction de la transaction manquante [`#531`](https://github.com/nocobase/nocobase/pull/531)
- **fix** : Ajout de la propriété d'ellipsis dans le sélecteur d'enregistrements [`#527`](https://github.com/nocobase/nocobase/pull/527)
- **fix** : Suppression du modèle sans élément de formulaire [`#528`](https://github.com/nocobase/nocobase/pull/528)
- **fix(plugin-workflow)** : Mise à jour de la propriété "current" lors de la mise à jour [`#526`](https://github.com/nocobase/nocobase/pull/526)
- **fix** : Ordre des valeurs nulles en dernier [`#519`](https://github.com/nocobase/nocobase/pull/519)
- **fix** : Chargement des actions, rafraîchissement du contexte, soumission de formulaire et validation [`#523`](https://github.com/nocobase/nocobase/pull/523)
- **fix** : Correction du modèle de champ [`#520`](https://github.com/nocobase/nocobase/pull/520)
- **fix(plugin-workflow)** : Correction de la largeur minimale du sélecteur de recherche [`#524`](https://github.com/nocobase/nocobase/pull/524)
- **fix** : Modèle avec uniquement des champs [`#517`](https://github.com/nocobase/nocobase/pull/517)
- **fix(plugin-workflow)** : Correction de la mise à jour de la propriété "current" dans le workflow [`#521`](https://github.com/nocobase/nocobase/pull/521)
- **refactor(plugin-workflow)** : Abstraction vers des classes [`#515`](https://github.com/nocobase/nocobase/pull/515)
- **feat** : Colonnes triables et modèle de champ [`#518`](https://github.com/nocobase/nocobase/pull/518)
- **fix(custom-request)** : Support des modèles string/json [`#514`](https://github.com/nocobase/nocobase/pull/514)
- **feat** : Ajout du titre de bloc [`#513`](https://github.com/nocobase/nocobase/pull/513)
- **fix** : Suppression des collections et des champs de la base de données [`#511`](https://github.com/nocobase/nocobase/pull/511)
- **feat** : Amélioration des migrations [`#510`](https://github.com/nocobase/nocobase/pull/510)
- **fix(client)** : Consolidation de l'utilisation des dates/heure en UTC lors du transfert [`#509`](https://github.com/nocobase/nocobase/pull/509)
- **fix** : Correction du bug de la formule [`#508`](https://github.com/nocobase/nocobase/pull/508)
- **fix** : Exportation par défaut des champs [`#506`](https://github.com/nocobase/nocobase/pull/506)
- **feat** : Bloc de champ d'association [`#493`](https://github.com/nocobase/nocobase/pull/493)
- **feat** : Exportation de plugins [`#479`](https://github.com/nocobase/nocobase/pull/479)
- **fix(client)** : Chemin du paquet corrigé (fix #503) [`#504`](https://github.com/nocobase/nocobase/pull/504)
- **fix** : Correction de l'erreur lors de la création ou suppression de collection [`#501`](https://github.com/nocobase/nocobase/pull/501)
- **feat** : Mise à jour des collections et des champs [`#500`](https://github.com/nocobase/nocobase/pull/500)
- **fix** : Rollback lorsque la création d'un champ échoue [`#498`](https://github.com/nocobase/nocobase/pull/498)
- **fix(client)** : Définition de `dropdownMatchSelectWidth` sur `false` globalement [`#497`](https://github.com/nocobase/nocobase/pull/497)
- **fix(client)** : Avertissement de clé manquante dans les éléments de menu utilisateur [`#496`](https://github.com/nocobase/nocobase/pull/496)
- **feat(plugin workflow)** : Ajout du champ cron pour la configuration des déclencheurs programmés [`#495`](https://github.com/nocobase/nocobase/pull/495)
- **feat** : Journaux d'audit [`#494`](https://github.com/nocobase/nocobase/pull/494)
- **refactor(plugin-workflow)** : Ajout d'une colonne de révision à l'exécution [`#491`](https://github.com/nocobase/nocobase/pull/491)
- **feat** : UI Schema pour le champ de relation [`#487`](https://github.com/nocobase/nocobase/pull/487)
- **feat** : Changement du FK en composant de saisie [`#488`](https://github.com/nocobase/nocobase/pull/488)
- **fix(plugin-multi-app-manager)** : Correction des tests de création de base de données pg qui échouent [`#486`](https://github.com/nocobase/nocobase/pull/486)
- **refactor(database)** : Proxy pour les hooks [`#402`](https://github.com/nocobase/nocobase/pull/402)
- **feat** : Blocs de graphiques [`#484`](https://github.com/nocobase/nocobase/pull/484)
- **refactor(plugin-workflow)** : Support des nombres dans la configuration de répétition pour la planification [`#482`](https://github.com/nocobase/nocobase/pull/482)
- **chore(debug)** : Ajout de la configuration de débogage [`#475`](https://github.com/nocobase/nocobase/pull/475)
- **fix** : Correction du bug "has one" [`#478`](https://github.com/nocobase/nocobase/pull/478)
- **feat** : Relations [`#473`](https://github.com/nocobase/nocobase/pull/473)
- **fix(plugin-workflow)** : Correction de la transaction de déclencheur de collection [`#474`](https://github.com/nocobase/nocobase/pull/474)
- **fix(plugin-workflow)** : Solution temporaire pour les conditions de déclencheur de collection [`#472`](https://github.com/nocobase/nocobase/pull/472)
- **fix** : Composant markdown [`#469`](https://github.com/nocobase/nocobase/pull/469)
- **fix** : Champ de formule et champ pourcentage [`#467`](https://github.com/nocobase/nocobase/pull/467)
- **fix(plugin-workflow)** : Correction de la mise à jour de l'action dans le workflow [`#464`](https://github.com/nocobase/nocobase/pull/464)
- **fix** : Mise à jour du champ de formule et du champ pourcentage [`#461`](https://github.com/nocobase/nocobase/pull/461)
- **feat** : Ajout du type de champ formule [`#457`](https://github.com/nocobase/nocobase/pull/457)
- **fix** : Les détails des données associées dans le sous-tableau ne sont pas affichés [`#454`](https://github.com/nocobase/nocobase/pull/454)
- **fix(plugin-workflow)** : Correction des langues [`#451`](https://github.com/nocobase/nocobase/pull/451)
- **fix** : Le hook `afterSync` n'est pas déclenché [`#450`](https://github.com/nocobase/nocobase/pull/450)
- **docs(various)** : Amélioration de la lisibilité [`#447`](https://github.com/nocobase/nocobase/pull/447)
- **feat** : Requête personnalisée [`#439`](https://github.com/nocobase/nocobase/pull/439)
- **feat(plugin workflow)** : Déclencheur programmé [`#438`](https://github.com/nocobase/nocobase/pull/438)
- **feat** : Migrateur de base de données [`#432`](https://github.com/nocobase/nocobase/pull/432)
- **fix(client)** : Le composant de sélection ne peut pas être ouvert dans un bloc de sous-table [`#431`](https://github.com/nocobase/nocobase/pull/431)
- **docs(github)** : Passage au format markdown [`#430`](https://github.com/nocobase/nocobase/pull/430)
- **fix(cli)** : Correction de fautes de frappe [`#429`](https://github.com/nocobase/nocobase/pull/429)

## Problèmes Résolus

- **fix(client)** : Chemin du paquet corrigé (fix #503) [`#503`](https://github.com/nocobase/nocobase/issues/503)

## Commits

- **feat(client)** : Mise à jour des locales [`e57e60e`](https://github.com/nocobase/nocobase/commit/e57e60e6cb84431e694e69830d128cd71938388f)
- **docs** : Mise à jour de la documentation [`e5cb948`](https://github.com/nocobase/nocobase/commit/e5cb94803f738961fcbc1986a94d258ef9e191a9)
- **fix(client)** : Amélioration du composant datepicker, prise en charge des dates avec fuseau horaire et GMT [`1c03fbb`](https://github.com/nocobase/nocobase/commit/1c03fbb853b5885547835f50fc9a0932f63c363b)
