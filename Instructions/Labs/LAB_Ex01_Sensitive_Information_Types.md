---
lab:
  task: Create a custom sensitive information type
  exercise: Exercise 1 - Create a custom sensitive information type
---

# Tâche de renforcement des compétences

Votre tâche consiste à créer et à publier des étiquettes de confidentialité au sein de votre organisation qui classifient et protègent les données sensibles en fonction de leur niveau de confidentialité et des contrôles d’accès nécessaires.

**Tâche** :

- Créer un type d’informations sensibles personnalisé

## Tâche - Créer un type d’informations sensibles personnalisé

Dans cette tâche, vous allez créer un nouveau type d’informations sensibles personnalisé qui reconnaît le modèle des ID d’employés via les mots clés « Employé » et « ID ».

1. Dans **Microsoft Edge**, accédez à **`https://purview.microsoft.com`** et connectez-vous au portail Microsoft Purview en tant que l’utilisateur que vous avez désigné en tant qu’**administrateur de conformité** lors d’une tâche précédente.

1. Dans la barre latérale de gauche, sélectionnez **Solutions**, puis **Protection des données**.

1. Dans la barre latérale de gauche, développez **Classificateurs**, puis sélectionnez **Types d’informations sensibles**.

1. Sur la page **Types d’informations sensibles**, sélectionnez **+ Créer un type d’informations sensibles** pour démarrer la configuration du type d’informations sensibles.

1. Sur la page **Nommer votre type d’informations sensibles**, saisissez :

    - **Nom :** `Contoso Employee IDs`
    - **Description** : `Pattern for Contoso employee IDs.`

1. Cliquez sur **Suivant**.

1. Dans la page **Définir des modèles pour ce type d’informations sensibles**, sélectionnez **Créer un modèle**.

1. Dans le panneau volant **Nouveau modèle** à droite, sélectionnez **+ Ajouter un élément principal** > **Expression régulière**.

1. À droite, dans le panneau volant **+ Ajouter une expression régulière**, saisissez :

    - **ID** : `Contoso IDs`
    - **Expression régulière** : `[A-Z]{3}[0-9]{6}`
    - Sélectionnez la case d’option * Correspondance de chaîne*

1. Sélectionnez **Terminé** au bas du panneau volant.

1. De retour sur le panneau volant **Nouveau modèle**, dans **Éléments complémentaires**, sélectionnez le menu déroulant **+ Ajouter des éléments ou un groupe d’éléments complémentaires**, puis sélectionnez **Liste de mots clés**.

1. À droite, dans le panneau volant **Ajouter une liste de mots clés**, saisissez :

    - **ID** : `Employee ID keywords`
    - **Insensible à la casse :**

       ```text
       Employee
       ID
       ```

    - Sélectionnez la case d’option *Correspondance des mots*

1. Sélectionnez **Terminé** au bas du panneau volant.

1. De retour sur le panneau volant **Nouveau modèle**, dans **Proximité des caractères**, réduisez la valeur **Détecter les éléments principaux ET complémentaires** à `100` caractères.

1. Sélectionnez le bouton **Créer** au bas du panneau volant.

1. De retour sur la page **Définir des modèles pour ce type d’informations sensibles**, sélectionnez **Suivant**.

1. Sur la page **Choisir le niveau de confiance recommandé à afficher dans les stratégies de conformité**, utilisez la valeur par défaut, puis sélectionnez **Suivant**.

1. À la page **Vérifier les paramètres et terminer**, passez en revue les paramètres, puis sélectionnez **Créer**. Une fois la création réussie, sélectionnez **Terminé**.

Vous avez créé un nouveau type d’informations sensibles pour identifier les ID d’employés suivant le modèle de trois caractères majuscules, six nombres et les mots clés « Employé » ou « ID » dans une plage de 100 caractères.
