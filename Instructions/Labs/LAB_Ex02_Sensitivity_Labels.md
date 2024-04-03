---
lab:
  task: Create and publish a sensitivity label
  exercise: Exercise 2 - Create and publish a sensitivity label
---

# Tâches d’acquisition de compétences

Votre tâche consiste à créer et à publier des étiquettes de confidentialité au sein de votre organisation qui classifient et protègent les données sensibles en fonction de leur niveau de confidentialité et des contrôles d’accès nécessaires.

- **Créer une étiquette de confidentialité** pour catégoriser les données.
- **Créer une sous-étiquette** sous l’étiquette parente pour regrouper les données.
- **Créer une stratégie d’étiquette** pour établir des règles et des instructions afin de gérer les étiquettes de confidentialité au sein de l’organisation.

**Objectif** : créer et publier une étiquette de confidentialité pour améliorer la protection des données dans le service des ressources humaines. Votre tâche consiste à configurer une étiquette parente appelée _Internal_ avec une sous-étiquette appelée _Employee Data (HR)_.

## Tâche 1 – Créer une étiquette de confidentialité

1. Accédez au portail de conformité Microsoft Purview.
1. Développez **Protection des informations**, puis sélectionnez **Étiquettes**.
1. Dans **Étiquettes**, sélectionnez **+ Créer une étiquette**.
1. Dans **Fournir des détails de base pour cette étiquette**, entrez les informations suivantes :

    - **Nom :** `Internal`
    - **Nom d’affichage** : `Internal`
    - **Description pour les utilisateurs** : `Internal sensitivity label.`
    - **Description pour les administrateurs** : `Internal sensitivity label for Contoso.`

1. Cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, **Fichiers** et **E-mails**, puis **Suivant**.
1. Dans la page **Choisir les paramètres de protection pour les types d’éléments que vous avez sélectionnés**, sélectionnez **Suivant**.
1. Sélectionnez **Suivant** et acceptez les valeurs par défaut jusqu’à ce que vous arriviez à la page **Vérifier vos paramètres et terminer**, puis sélectionnez **Créer une étiquette**.
1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

## Tâche 2 – Créer une sous-étiquette

1. Dans la page Protection des informations, mettez en surbrillance (sans sélectionner) l’étiquette **Internal** que vous venez de créer, puis sélectionnez les points verticaux (**...**). ![Image du menu à points verticaux](../Media/SensitivityLabelDotMenu.png)
1. Sélectionnez le **+ Créer une sous-étiquette** dans le menu.
1. Dans **Fournir des détails de base pour cette étiquette**, entrez les informations suivantes :

   - **Nom :** `Employee data (HR)`
   - **Nom d’affichage** : `Employee data (HR)`
   - **Description pour les utilisateurs** : `This label is the default label for all documents in the HR Department.`
   - **Description pour les administrateurs** : `This label is created in consultation with the Director of HR.`
1. Cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, **Fichiers** et **E-mails**, puis **Suivant**.
1. Dans la page **Choisir les paramètres de protection pour les types d’éléments que vous avez sélectionnés**, cochez la case **Contrôler l’accès**, puis sélectionnez **Suivant**.
1. Dans la page **Contrôle d’accès** :
   - Vérifiez que la case d’option **Configurer les paramètres de contrôle d’accès** est sélectionnée.
   - Sous **Attribuer des autorisations maintenant ou laisser les utilisateurs décider ?**, sélectionnez **Attribuer des autorisations maintenant**.
   - Sous **L’accès des utilisateurs au contenu expire**, sélectionnez **Jamais**.
   - Sous **Autoriser l’accès hors connexion**, sélectionnez **Uniquement pendant un certain nombre de jours**.
   - Dans le champ **Les utilisateurs ont accès hors connexion au contenu pendant ce nombre de jours**, entrez 14.
   - Sous **Attribuer des autorisations à des utilisateurs et groupes spécifiques** sélectionnez le bouton **Attribuer des autorisations**.
1. Dans la page **Attribuer des autorisations**, sélectionnez **+ Ajouter des utilisateurs authentifiés**, puis **Enregistrer**.
1. De retour dans la page **Contrôle d’accès**, sélectionnez **Suivant**.
1. Sélectionnez **Suivant** et acceptez les valeurs par défaut jusqu’à ce que vous arriviez à la page **Vérifier vos paramètres et terminer**, puis sélectionnez **Créer une étiquette**.
1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

## Tâche 3 – Publier une étiquette de confidentialité

1. Dans la page **Étiquettes**, cochez les cases en regard de l’étiquette **Internal** et de la sous-étiquette **Employee data (HR)** que vous venez de créer.
1. Dans la page **Choisir les étiquettes de confidentialité à publier**, vérifiez que les étiquettes de données Internal et Employee data (HR) sont affichées sous **Étiquettes de confidentialité à publier**, puis sélectionnez **Suivant**.
1. Sélectionnez **Suivant** jusqu’à ce que vous arriviez à la page **Paramètres de stratégie**.
1. Dans la page **Paramètres de stratégie**, cochez la case **Les utilisateurs doivent fournir une justification pour supprimer une étiquette ou réduire sa classification**.
1. Sélectionnez **Suivant** jusqu’à ce que vous arriviez à la page **Nommer votre stratégie**.
1. Dans la page **Nommer votre stratégie**, entrez les informations suivantes :

   - **Nom :** `Internal HR employee data`
   - **Entrez une description pour votre stratégie d’étiquette de confidentialité** : `This HR label is to be applied to internal HR employee data.`

1. Cliquez sur **Suivant**.
1. Dans la page **Vérifier et terminer**, sélectionnez **Envoyer**.
1. Dans la page **Nouvelle stratégie créée**, sélectionnez **Terminé**.

Vous venez de créer une étiquette de confidentialité qui permet de classifier les données des employés pour le service des ressources humaines.
