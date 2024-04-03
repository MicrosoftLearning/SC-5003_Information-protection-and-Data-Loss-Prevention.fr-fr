---
lab:
  task: Create a custom sensitive information type
  exercise: Exercise 1 - Create a custom sensitive information type
---

## Locataires WWL - Conditions d’utilisation

Si un locataire vous est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation.

Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder.

Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment.

# Tâches d'apprentissage

Votre tâche consiste à créer un type d’informations sensibles personnalisé (SIT) qui respecte les critères requis :

- **Modèle d’expression régulière pour l’ID des employés** : Incluez un modèle d’expression régulière qui identifie la configuration d’ID unique des employés, comptant 9 caractères, de votre organisation : 3 chiffres et un tiret suivis de 5 lettres (par exemple, 123-abcde).
- **Liste de mots clés associés aux ID des employés** : Incorporez une liste de mots clés couramment associés aux ID des employés pour améliorer l’exactitude de la détection.

## Tâche 1 : créer un type d’informations sensibles

1. Accédez au portail de conformité Microsoft Purview.
1. Développez **Classification de données**, puis sélectionnez **Classifieurs**.
1. Sélectionnez **Types d’informations sensibles**, puis **+ Créer un type d’informations sensibles**.
1. Dans la page **Nommer votre type d’informations sensibles**, donnez à votre type d’informations sensibles un **Nom** et une **Description** explicites, puis sélectionnez **Suivant**.
1. Dans la page **Définir des modèles pour ce type d’informations sensibles**, sélectionnez **Créer un modèle**.
1. Dans la page **Nouveau modèle**, sélectionnez **+ Ajouter un élément principal** > **Expression régulière**.
1. Dans la **page Ajouter une expression régulière**, donnez à l’expression régulière un nom explicite pour **ID**, puis entrez `\d{3}-[a-zA-Z]{5}` dans le champ d’**Expression régulière** pour prendre en charge l’exigence de l’organisation. Sélectionnez **Terminé** lorsque vous avez terminé.
1. De retour dans la page **Nouveau modèle**, sous **Éléments pris en charge**, sélectionnez **+ Ajouter des éléments ou un groupe d’éléments pris en charge** > **Liste de mots clés**.
1. Dans la page **Ajouter une liste de mots clés**, donnez un **ID** explicite à votre liste de mots clés. Dans **Groupe de mots clés n° 1** sous **Insensible à la casse**, entrez :
   - `Employee ID`
   - `Staff number`
   - `Work ID`
1. Sélectionnez **Terminé** lorsque vous avez terminé.
1. De retour dans la page **Nouveau modèle**, sélectionnez **Créer**.
1. Sélectionnez **Suivant** dans la page **Définir des modèles pour ce type d’informations sensibles**.
1. Dans la page **Choisir le niveau de confiance recommandé à afficher dans les stratégies de conformité**, laissez la valeur par défaut sélectionnée, puis sélectionnez **Suivant**.
1. Passez en revue vos paramètres, puis sélectionnez **Créer**.
1. Dans la page **Votre type d’informations sensibles est créé**, sélectionnez **Terminé**.

Vous avez maintenant correctement créé un type d’informations sensibles (SIT) personnalisé pour améliorer la sécurité et la gestion des numéros uniques des ID des employés de votre entreprise.
