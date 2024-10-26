---
lab:
  task: Create and publish a sensitivity label
  exercise: Exercise 2 - Create and publish a sensitivity label
---

# Tâches d’acquisition de compétences

Votre tâche consiste à créer et à publier des étiquettes de confidentialité au sein de votre organisation qui classifient et protègent les données sensibles en fonction de leur niveau de confidentialité et des contrôles d’accès nécessaires.

**Tâches :**

1. Activer la prise en charge des étiquettes de confidentialité
1. Créer des étiquettes de confidentialité
1. Publier les étiquettes de confidentialité
1. Configurer l’étiquetage automatique

## Tâche 1 - Activer la prise en charge des étiquettes de confidentialité dans SharePoint et OneDrive

Dans cette tâche, vous allez installer les modules nécessaires et activer la prise en charge des étiquettes de confidentialité dans votre locataire. Cela est nécessaire pour la tâche facultative qui consiste à appliquer des étiquettes de confidentialité, plus loin dans cet exercice.

1. Sur le bureau, ouvrez une fenêtre PowerShell à privilèges élevés en cliquant avec le bouton droit sur le bouton Windows dans la barre des tâches, puis sélectionnez **Terminal (admin)**.

1. Dans la fenêtre **Contrôle de compte d’utilisateur**, confirmez en cliquant sur **Oui**.

1. Exécutez le cmdlet **Install-Module** pour installer la dernière version du module PowerShell MS Online :

    ```powershell
    Install-Module -Name MSOnline
    ```

1. Confirmez la boîte de dialogue de sécurité Nuget et la boîte de dialogue de sécurité du référentiel non approuvé en appuyant sur **Y** pour Oui, puis appuyez sur Entrée. Ce processus peut prendre un certain temps.

1. Exécutez le cmdlet **Install-Module** pour installer la dernière version du module PowerShell SharePoint Online :

    ```powershell
    Install-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

1. Confirmez la boîte de dialogue de sécurité du référentiel non approuvé en appuyant sur **Y** pour Oui, puis appuyez sur Entrée.

1. Exécutez **Connect-MsolService** pour vous connecter au service MS Online :

    ```powershell
    Connect-MsolService
    ```

1. Dans le formulaire **Se connecter à votre compte**, connectez-vous en tant que l’utilisateur que vous avez désigné comme **administrateur de conformité** dans un exercice précédent.

1. Une fois connecté, revenez à la fenêtre du terminal.

1. Exécutez le cmdlet **Get-Msoldomain** et enregistrez le domaine en tant que variable :

    ```powershell
    $domain = get-msoldomain
    ```

1. Utilisez la variable _$domain_ créée lors de l’étape précédente pour créer une variable pour _$adminurl_ :

    ```powershell
    $adminurl = "https://" + $domain.Name.split('.')[0] + "-admin.sharepoint.com"
    ```

1. Exécutez le cmdlet **Connect-SPOService** en utilisant la variable _$adminurl_ créée lors de l’étape précédente :

    ```powershell
    Connect-SPOService -url $adminurl
    ```

1. Dans le formulaire **Se connecter à votre compte**, connectez-vous en tant qu’**administrateur général**.

1. Une fois connecté, revenez à la fenêtre du terminal.

1. Exécutez le cmdlet **Set-SPOTenant** pour activer la prise en charge des étiquettes de confidentialité :

    ```powershell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

1. Confirmez les modifications en appuyant sur **Y** pour Oui, puis appuyez sur Entrée.

1. Fermez la fenêtre PowerShell.

Vous avez activé la prise en charge des étiquettes de confidentialité pour les sites Teams et SharePoint.

## Tâche 2 - Créer des étiquettes de confidentialité

Dans cette tâche, votre service RH a demandé qu’une étiquette de confidentialité soit appliquée aux documents des employés RH. Vous allez créer une étiquette de confidentialité pour les documents internes et une sous-étiquette pour le service RH.

1. Ouvrez **Microsoft Edge** et accédez à **`https://purview.microsoft.com`**. Connectez-vous à Microsoft Purview en tant que l’utilisateur que vous avez désigné comme **administrateur de conformité**.

1. Dans le portail Microsoft Purview, sélectionnez **Solutions** dans la barre latérale de gauche, puis sélectionnez **Protection des données**.

1. Sur la page **Protection des données Microsoft**, dans la barre latérale de gauche, sélectionnez **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, sélectionnez **+ Créer une étiquette**.

1. La configuration de la **nouvelle étiquette de confidentialité** démarre alors. Dans **Fournir des détails de base pour cette étiquette**, saisissez :

    - **Nom :** `Internal`
    - **Nom d’affichage** : `Internal`
    - **Description pour les utilisateurs** : `Internal sensitivity label.`
    - **Description pour les administrateurs** : `Internal sensitivity label for Contoso.`

1. Cliquez sur **Suivant**.

1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, puis **Fichiers** et **E-mails**. Si la case **Réunions** est cochée, décochez-la.

   > [!NOTE]
   > Si **Réunions** est sélectionné, vous ne pourrez pas créer de sous-étiquette pour l’étiquette de confidentialité.

1. Cliquez sur **Suivant**.

1. Sur la page **Choisir les paramètres de protection pour les éléments étiquetés**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des fichiers et des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Définir les paramètres de protection pour les groupes et les sites**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des ressources de données schématisées (version préliminaire)**, sélectionnez **Suivant**.

1. Dans la page **Vérifier vos paramètres et terminer**, sélectionnez **Créer une étiquette**.

1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

1. Sur la page **Étiquettes de confidentialité**, recherchez l’étiquette de confidentialité **interne** nouvellement créée. Sélectionnez les points de suspension verticaux (**...**) à côté de celle-ci, puis sélectionnez **+ Créer une sous-étiquette** dans le menu déroulant.

    ![Capture d’écran montrant le menu d’actions permettant de créer une sous-étiquette pour une étiquette de confidentialité.](../Media/create-sublabel-button.png)

1. L’assistant **Nouvelle étiquette de confidentialité** démarre alors. Sur la page **Fournir des détails de base pour cette étiquette**, saisissez :

   - **Nom :** `Employee data (HR)`
   - **Nom d’affichage** : `Employee data (HR)`
   - **Description pour les utilisateurs** : `This HR label is the default label for all specified documents in the HR Department.`
   - **Description pour les administrateurs** : `This label was created with input from the Head of HR. Contact the HR department for any changes to the label settings.`

1. Cliquez sur **Suivant**.

1. Sur la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, puis **Fichiers**, **E-mails** et **Réunions**.

1. Cliquez sur **Suivant**.

1. Sur la page **Choisir les paramètres de protection des éléments étiquetés**, sélectionnez l’option **Contrôle d’accès**, puis sélectionnez **Suivant**.

1. Sur la page **Contrôle d’accès**, sélectionnez **Configurer les paramètres de contrôle d’accès**.

1. Configurez les paramètres de chiffrement avec les options suivantes :

   - **Attribuer des autorisations maintenant ou laisser les utilisateurs décider ?**  : attribuer des autorisations maintenant.
   - **L’accès des utilisateurs au contenu expire** : jamais.
   - **Autoriser l’accès hors connexion** : uniquement pendant un certain nombre de jours.
   - **Les utilisateurs disposent d’un accès hors connexion au contenu pendant ce nombre de jours** : 15.
   - Sélectionnez le lien **Attribuer des autorisations**. Dans le panneau volant **Attribuer des autorisations**, sélectionnez **+ Ajouter des utilisateurs authentifiés**, puis sélectionnez **Enregistrer** pour appliquer ce paramètre.

1. Sur la page **Contrôle d’accès**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des fichiers et des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Définir les paramètres de protection pour les groupes et les sites**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des ressources de données schématisées (version préliminaire)**, sélectionnez **Suivant**.

1. Dans la page **Vérifier vos paramètres et terminer**, sélectionnez **Créer une étiquette**.

1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

Vous avez créé avec succès une étiquette de confidentialité pour les stratégies internes de votre organisation et une sous-étiquette de confidentialité pour le service des ressources humaines (RH).

## Tâche 3 - Publier des étiquettes de confidentialité

Vous allez maintenant publier l’étiquette de confidentialité interne et RH afin que les étiquettes de confidentialité publiées puissent être appliquées par les utilisateurs RH à leurs documents RH.

1. Dans **Microsoft Edge**, l’onglet du portail Microsoft Purview devrait encore être ouvert. Si ce n’est pas le cas, accédez à **`https://purview.microsoft.com`** > **Solutions** > **Protection des données** > **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, sélectionnez **Publier des étiquettes**.

1. La configuration de la publication des étiquettes de confidentialité démarre alors.

1. Sur la page **Choisir les étiquettes de confidentialité à publier**, sélectionnez le lien **Choisir les étiquettes de confidentialité à publier**.

1. Dans le panneau volant **Étiquettes de confidentialité à publier**, cochez les cases **Interne** et **Données internes/employés (RH),** puis sélectionnez **Ajouter** en bas du panneau volant.

1. De retour sur la page **Choisir des étiquettes de confidentialité à publier**, sélectionnez **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Sur la page **Publier pour les utilisateurs et les groupes**, sélectionnez **Suivant**.

1. Sur la page **Paramètres de stratégie**, sélectionnez **Suivant**.

1. Sur la page **Paramètres par défaut des documents**, sélectionnez **Suivant**.

1. Sur la page **Paramètres par défaut des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Paramètres par défaut des réunions et des événements de calendrier**, sélectionnez **Suivant**.

1. Sur la page **Paramètres par défaut du contenu Fabric et Power BI**, sélectionnez **Suivant**.

1. Sur la page **Nommer votre stratégie**, saisissez :

   - **Nom :** `Internal HR employee data`
   - **Entrez une description pour votre stratégie d’étiquette de confidentialité** : `This HR label is to be applied to internal HR employee data.`

1. Cliquez sur **Suivant**.

1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**.

1. Dans la **Nouvelle stratégie créée**, sélectionnez **Terminé** pour terminer la publication de votre stratégie d’étiquette.

Vous avez publié les étiquettes de confidentialité internes et RH. Notez que cela peut prendre jusqu’à 24 heures pour que les modifications soient répliquées pour tous les utilisateurs et tous les services.

## Tâche 4 - Créer une stratégie d’étiquetage automatique côté client

Dans cette tâche, vous allez créer une stratégie d’étiquetage automatique côté client. Les étiquettes automatiques côté client s’appliquent automatiquement aux fichiers et aux e-mails en fonction de leur contenu, ce qui garantit que les informations sensibles sont classifiées et protégées avant de quitter l’appareil de l’utilisateur.

1. Vous devriez toujours être sur la page **Étiquettes de confidentialité** dans le portail Microsoft Purview. Si ce n’est pas le cas, accédez à **`https://purview.microsoft.com`** > **Solutions** > **Protection des données** > **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, recherchez l’étiquette de confidentialité **interne** nouvellement créée. Sélectionnez les points de suspension verticaux (**...**) à côté de celle-ci, puis sélectionnez **+ Créer une sous-étiquette** dans le menu déroulant.

1. La configuration de la **nouvelle étiquette de confidentialité** démarre alors. Sur la page **Fournir des détails de base pour cette étiquette**, saisissez :

   - **Nom :** `Confidential Research Data`
   - **Nom d’affichage** : `Confidential Research Data`
   - **Description pour les utilisateurs** : `This document or email contains sensitive research or development data that is proprietary to the organization.`
   - **Description pour les administrateurs** : `This label is auto-applied to documents and emails containing information related to research, prototypes, or internal projects.`

1. Cliquez sur **Suivant**.

1. Sur la page **Définir l’étendue de cette étiquette**, sélectionnez **Éléments**, puis **Fichiers**, **E-mails** et **Réunions**.

1. Cliquez sur **Suivant**.

1. Sur la page **Choisir les paramètres de protection pour les éléments étiquetés**, sélectionnez **Appliquer le marquage de contenu**, puis **Suivant**.

1. Cliquez sur **Suivant**.

1. Sur la page **Marquage du contenu**, sélectionnez le bouton pour activer le marquage du contenu.

1. Si la case **Ajouter un pied de page** est cochée, décochez-la et cochez la case **Ajouter un filigrane**, puis sélectionnez **Personnaliser le texte**.

1. Dans le panneau volant **Personnaliser le texte de filigrane**, saisissez `Confidential - R&D Data` comme **texte de filigrane**. Augmentez la **taille de police** jusqu’à `40`, puis sélectionnez **Enregistrer** en bas du panneau.

1. De retour sur la page **Marquage de contenu**, si d’autres options de marquage de contenu sont activées, désactivez-les pour vous assurer que l’option **Ajouter un filigrane** est la seule option activée.

1. Cliquez sur **Suivant**.

1. Sur la page **Étiquetage automatique des fichiers et des e-mails**, activez l’option **Étiquetage automatique des fichiers et des e-mails**.

1. Dans la section **Détecter le contenu qui correspond à ces conditions**, sélectionnez **+ Ajouter une condition** > **Contenu contenant**.

1. Dans la section **Contenu contenant**, sélectionnez **Ajouter** > **Classificateurs entraînables**.

1. Dans le panneau volant **Classificateurs entraînables**, ajoutez les classificateurs entraînables suivants :

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

1. Sélectionnez **Ajouter** au bas du panneau pour ajouter ces classificateurs entraînables.

1. De retour sur la page **Étiquetage automatique des fichiers et des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Définir les paramètres de protection pour les groupes et les sites**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des ressources de données schématisées (version préliminaire)**, sélectionnez **Suivant**.

1. Dans la page **Vérifier vos paramètres et terminer**, sélectionnez **Créer une étiquette**.

1. Sur la page **Votre étiquette de confidentialité a été créée** , sélectionnez **Publier une étiquette sur les applications des utilisateurs**, puis sélectionnez **Terminé**.

1. Dans le panneau volant **Publier une étiquette**, sélectionnez **Créer une stratégie d’étiquette**.

1. Sur la page **Choisir les étiquettes de confidentialité à publier**, sélectionnez le lien **Choisir les étiquettes de confidentialité à publier**.

1. Sélectionnez l’étiquette **Interne** parente et l’étiquette **Données de recherche confidentielles** qui vient d’être créée, puis sélectionnez **Ajouter**.

1. De retour sur la page **Choisir des étiquettes de confidentialité à publier**, sélectionnez **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Sur la page **Publier pour les utilisateurs et les groupes**, sélectionnez **Suivant**.

1. Sur la page **Paramètres de stratégie**, cochez la case **Les utilisateurs doivent fournir une justification pour supprimer une étiquette ou réduire son niveau de classification**, puis sélectionnez **Suivant**.

1. Sur la page **Paramètres par défaut des documents**, sélectionnez **Suivant** jusqu’à atteindre la page **Nommer votre stratégie**.

1. Sur la page **Nommer votre stratégie**, saisissez :

   - **Nom :** `R&D Confidential Data Policy`
   - **Entrez une description pour votre stratégie d’étiquette de confidentialité** : `Automatically applies labels to source code, project documents, and development files to protect sensitive R&D data.`

1. Cliquez sur **Suivant**.

1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**.

1. Dans la page **Nouvelle stratégie créée**, sélectionnez **Terminé**.

Vous avez créé une stratégie d’étiquetage automatique côté client qui applique automatiquement l’étiquette **Données de recherche confidentielles** aux fichiers et aux e-mails contenant des données de recherche et de développement. L’application complète de la stratégie peut prendre jusqu’à 24 heures.

## Tâche 5 - Créer une stratégie d’étiquetage automatique côté service

Dans cette tâche, vous allez créer une stratégie d’étiquetage automatique côté service. Les étiquettes automatiques côté service sont appliquées par des services cloud tels que SharePoint, Exchange et OneDrive après que du contenu est chargé ou reçu, ce qui garantit que les données sensibles sont protégées même si les utilisateurs ne les classifient pas manuellement.

1. Vous devriez toujours être sur la page **Étiquettes de confidentialité** dans le portail Microsoft Purview. Si ce n’est pas le cas, accédez à **`https://purview.microsoft.com`** > **Solutions** > **Protection des données** > **Étiquettes de confidentialité**.

1. Développez l’étiquette **Interne**, puis sélectionnez la sous-étiquette `Confidential Research Data` que vous avez créée lors d’une tâche précédente.

1. Dans le panneau volant **Données de recherche confidentielles**, vous pouvez voir les propriétés de l’étiquette automatique que vous avez créée lors d’une tâche précédente. Dans ce panneau, sélectionnez **Créer une stratégie d’étiquetage automatique**.

    ![Capture d’écran montrant l’option permettant de créer une stratégie d’étiquetage automatique.](../Media/create-auto-labeling-policy.png)

1. Sur la page **Nommer votre stratégie**, saisissez :

   - **Nom :** `R&D Confidential Data Container Policy`
   - **Entrez une description pour votre stratégie d’étiquette de confidentialité** : `Automatically applies the Confidential Research Data label to content in SharePoint, Exchange, and OneDrive.`

1. Cliquez sur **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Sur la page **Choisir les emplacements où vous souhaitez appliquer l’étiquette**, laissez **E-mail Exchange**, **Sites SharePoint** et **Comptes OneDrive** sélectionnés, puis sélectionnez **Suivant**.

1. Sur la page **Configurer des règles courantes ou avancées**, laissez **Règles courantes** sélectionné, puis sélectionnez **Suivant**.

1. Sur la page **Définir des règles de contenu pour tous les emplacements**, modifiez la règle **Données de recherche confidentielles**.

    ![Capture d’écran montrant où modifier la règle pour une stratégie d’étiquetage automatique côté service.](../Media/auto-apply-labels-edit-rule.png)

1. Dans le panneau volant **Nouvelle règle**, dans **Conditions** > **Contenu contenant**, sélectionnez la liste déroulante **Ajouter**, puis sélectionnez **Classificateurs entraînables**.

1. Dans le panneau volant **Classificateurs entraînables**, ajoutez les classificateurs entraînables suivants :

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

   Cela garantit une protection cohérente entre les étiquettes côté client et côté service.

1. Sélectionnez **Ajouter** au bas du panneau pour ajouter ces classificateurs entraînables.

1. De retour sur la page **Définir des règles de contenu pour tous les emplacements**, sélectionnez **Suivant**.

1. Dans **Choisir une étiquette à appliquer automatiquement**, laissez **Données de recherche confidentielles/Internes** sélectionné, puis sélectionnez **Suivant**.

1. Sur la page **Décider si vous souhaitez tester la stratégie maintenant ou ultérieurement**, sélectionnez **Exécuter la stratégie en mode simulation**, cochez la case **Activer automatiquement la stratégie si elle n’est pas modifiée après 7 jours de simulation**, puis sélectionnez **Suivant**.

1. Sur la page **Vérifier et terminer**, sélectionnez **Créer la stratégie**.

1. Dans la page **Votre stratégie d’étiquetage automatique a été créée**, sélectionnez **Terminé**.

Vous avez créé une stratégie d’étiquetage automatique côté service qui applique automatiquement l’étiquette **Données de recherche confidentielles** au contenu stocké ou partagé dans SharePoint, Exchange et OneDrive. L’application de la stratégie peut prendre jusqu’à 24 heures.
