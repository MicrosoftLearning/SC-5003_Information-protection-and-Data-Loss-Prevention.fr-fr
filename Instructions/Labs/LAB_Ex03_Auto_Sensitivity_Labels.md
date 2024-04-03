---
lab:
  task: Create and assign an auto-labeling policy
  exercise: Exercise 3 - Create and assign an auto-labeling policy
---

# Tâches d’acquisition de compétences

Votre tâche consiste à créer et à publier des étiquettes de confidentialité au sein de votre organisation qui classifient et protègent les données sensibles en fonction de leur niveau de confidentialité et des contrôles d’accès nécessaires.

- **Créer une étiquette de confidentialité** pour catégoriser les données.
- **Configurer l’étiquette en vue de l’étiquetage automatique** pour des fichiers et des e-mails.
- **Configurer une stratégie d’étiquetage automatique** afin de classifier automatiquement des données dans SharePoint et OneDrive.
- **Publier la stratégie d’étiquetage automatique** afin de déployer l’étiquette au sein de votre organisation, en automatisant la classification pour renforcer la sécurité et la conformité.

**Objectif** : Créer et publier une stratégie d’étiquetage automatique pour le service Finance. Votre tâche consiste à configurer une étiquette de confidentialité qui applique automatiquement des étiquettes à des fichiers et des e-mails en fonction des données financières. Vous devez également créer une stratégie d’étiquetage automatique qui applique automatiquement ces étiquettes au contenu dans SharePoint et OneDrive.

## Tâche 1 – Créer une étiquette de confidentialité

1. Accédez au portail de conformité Microsoft Purview.
1. Développez **Protection des informations**, puis sélectionnez **Étiquettes**.
1. Dans **Étiquettes**, sélectionnez **+ Créer une étiquette**.
1. Dans **Fournir des détails de base pour cette étiquette**, entrez les informations suivantes :

    - **Nom :** `Protected Financial Records`
    - **Nom d’affichage** : `Protected Financial Records`
    - **Description pour les utilisateurs** : `Use for documents with sensitive financial data.`
    - **Description pour les administrateurs** : `Applies encryption and access controls to financial documents.`

1. Cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, **Fichiers** et **E-mails**, puis **Suivant**.
1. Dans la page **Choisir les paramètres de protection pour les types d’éléments que vous avez sélectionnés**, sélectionnez **Suivant**.
1. Dans **Étiquetage automatique des fichiers et e-mails** :
   - À l’aide du bouton bascule, activez l’**Étiquetage automatique pour les fichiers et les e-mails**.
   - Sous **Détecter le contenu qui correspond à ces conditions**, sélectionnez **+ Ajouter une condition** > **Le contenu contient**.
   - Sous **Le contenu contient**, sélectionnez **Ajouter** > **Types d’informations sensibles**.
   - Dans la page **Types d’informations sensibles**, recherchez et ajoutez le type d’informations sensibles pour `Credit Card Number`,  `U.S. Bank Account Number` et `ABA Routing Number`. Sélectionnez **Ajouter** pour ajouter les trois types d’informations sensibles, puis **Enregistrer**.
   - Sous **Lorsque le contenu correspond à ces conditions**, sélectionnez **Appliquer automatiquement l’étiquette**.
   - Laissez vide le message facultatif **Afficher ce message aux utilisateurs lorsque l’étiquette est appliquée**.
1. Sélectionnez **Suivant** et acceptez les valeurs par défaut jusqu’à atteindre la page **Vérifier vos paramètres et terminer**, et sélectionnez **Créer une étiquette**.
1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

## Tâche 2 – Créer une stratégie d’étiquetage automatique

1. Dans la page **Étiquettes**, cochez la case en regard de l’étiquette **Enregistrements financiers protégés** que vous venez de créer, puis sélectionnez **Créer une stratégie d’étiquetage automatique**.
1. Dans la page **Nommer votre stratégie d’étiquetage automatique**, entrez les informations suivantes :

   - **Nom :** `Finance Auto-Label Policy`
   - **Entrez une description pour votre stratégie d’étiquette de confidentialité** : `Automates the labeling of financial documents.`
1. Sélectionnez **Suivant** jusqu’à atteindre la page **Définir des règles pour le contenu dans tous les emplacements**.
1. Dans **Définir des règles pour le contenu dans tous les emplacements**, sélectionnez **Nouvelle règle**.
1. Dans la page **Nouvelle règle** :
   - Entrez `Financial data` comme **Nom**.
   - Sous **Conditions**, sélectionnez **+ Ajouter une condition** > **Le contenu contient**.
   - Sous **Le contenu contient**, sélectionnez **Ajouter** > **Type d’informations sensibles**.
   - Dans la page **Types d’informations sensibles**, recherchez et ajoutez le type d’informations sensibles pour `Credit Card Number`,  `U.S. Bank Account Number` et `ABA Routing Number`. Sélectionnez **Ajouter** pour ajouter les trois types d’informations sensibles, puis **Enregistrer**.
1. Sélectionnez **Suivant** jusqu’à atteindre la page **Décider si vous souhaitez tester la stratégie maintenant ou ultérieurement**.
1. Dans la page **Décider si vous souhaitez tester la stratégie maintenant ou ultérieurement**, sélectionnez **Exécuter la stratégie en mode de simulation**, puis **Suivant**.
1. Dans la page **Vérifier et terminer**, sélectionnez **Créer la stratégie**.
1. Dans la page **Votre stratégie d’étiquetage automatique a été créée**, sélectionnez **Terminé**.

Vous avez réussi à créer une étiquette de confidentialité afin de classifier les données financières pour le service Finance.
