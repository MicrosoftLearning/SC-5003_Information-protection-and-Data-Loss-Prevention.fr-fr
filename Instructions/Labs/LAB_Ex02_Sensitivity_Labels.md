---
lab:
  task: Create and publish a sensitivity label
  exercise: Exercise 2 - Create and publish a sensitivity label
---

# Tâches d’acquisition de compétences

Votre tâche consiste à créer et à publier des étiquettes de sensibilité au sein de votre organisation afin de classer et de protéger les données sensibles en fonction de leur niveau de confidentialité et des contrôles d'accès nécessaires.

**Tâches :**

1. Activer la prise en charge des étiquettes de confidentialité  
1. Créer un groupe d’étiquettes  
1. Créer une étiquette enfant  
1. Publier des étiquettes  
1. Configurer l’étiquetage automatique  

## Tâche 1 - Activer la prise en charge des étiquettes de confidentialité dans SharePoint et OneDrive

Dans cette tâche, vous allez activer la co-création pour les étiquettes de confidentialité, ce qui active également les étiquettes de confidentialité pour les fichiers dans SharePoint et OneDrive.

1. Ouvrez **Microsoft Edge** et accédez à `https://purview.microsoft.com`.

1. Dans le volet de navigation gauche, sélectionnez **Paramètres** > **Protection des données**.

1. Dans les **paramètres Protection des données**, vérifiez que vous êtes sur l’onglet **Co-édition de fichiers avec des étiquettes de confidentialité**.

1. Cochez la case pour **Activer la co-édition des fichiers avec des étiquettes de confidentialité**.

1. Sélectionner **Appliquer** en bas de l’écran.

Vous avez activé la prise en charge des étiquettes de confidentialité pour les fichiers SharePoint et OneDrive.

<!--

## Task 2 – Create sensitivity labels

In this task, your HR department has requested a sensitivity label to apply to HR employee documents. You'll create a sensitivity label for internal documents and a sublabel for the HR department.

1. Open **Microsoft Edge** and navigate to **`https://purview.microsoft.com`**. Log into Microsoft Purview as the user you selected as the **Compliance Administrator**.

1. In the Microsoft Purview portal, select **Solutions** from the left sidebar, then select **Information Protection**.

1. On the **Microsoft Information Protection** page, on the left sidebar, select **Sensitivity labels**.

1. On the **Sensitivity labels** page select **+ Create a label**.

1. The **New sensitivity label** configuration will start. On the **Provide basic details for this label**, enter:

    - **Name**: `Internal`
    - **Display name**: `Internal`
    - **Description for users**: `Internal sensitivity label.`
    - **Description for admins**: `Internal sensitivity label for Contoso.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files** and **Emails**. If the checkbox for **Meetings** is selected, make sure it's deselected.

   > [!NOTE]
   > When **Meetings** is selected, you can't create a sublabel for the sensitivity label.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select **Next**.

1. On the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

1. On the **Sensitivity labels** page, find the newly created **Internal** sensitivity label. Select the vertical ellipsis (**...**) next to it, then select **+ Create sublabel** from the dropdown menu.

    ![Screenshot showing the Action menu to create a sublabel for a sensitivity label.](../Media/create-sublabel-button.png)

1. The **New sensitivity label** wizard will start. On the **Provide basic details for this label** page enter:

   - **Name**: `Employee data (HR)`
   - **Display name**: `Employee data (HR)`
   - **Description for users**: `This HR label is the default label for all specified documents in the HR Department.`
   - **Description for admins**: `This label was created with input from the Head of HR. Contact the HR department for any changes to the label settings.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files**, **Emails**, and **Meetings**.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select the **Control access** option, then select **Next**.

1. On the **Access control** page, select **Configure access control settings**.

1. Configure the encryption settings with these options:

   - **Assign permissions now or let users decide?**: Assign permissions now
   - **User access to content expires**: Never
   - **Allow offline access**: Only for a number of days
   - **Users have offline access to the content for this many days**: 15
   - Select the **Assign permissions** link. On the **Assign permissions** flyout panel, select the **+ Add any authenticated users**, then select **Save** to apply this setting.

1. On the **Access control** page, select **Next**.

1. On the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

You have successfully created a sensitivity label for your organizations internal policies and a sensitivity sublabel for the Human Resources (HR) department.

## Task 3 – Publish sensitivity labels

You will now publish the Internal and HR sensitivity label so that the published sensitivity labels will be available for the HR users to apply to their HR documents.

1. In **Microsoft Edge**, the Microsoft Purview portal tab should still be open. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. On the **Sensitivity labels** page select **Publish labels**.

1. The publish sensitivity labels configuration will start.

1. On the **Choose sensitivity labels to publish** page, select the **Choose sensitivity labels to publish** link.

1. On the **Sensitivity labels to publish** flyout panel, select the **Internal** and **Internal/Employee Data (HR)** checkboxes, then select **Add** at the bottom of the flyout panel.

1. Back on the **Choose sensitivity labels to publish** page, select **Next**.

1. On the **Assign admin units** page, select **Next**

1. On the **Publish to users and groups** page, select **Next**.

1. On the **Policy settings** page, select **Next**.

1. On the **Default settings for documents** page, select **Next**.

1. On the **Default settings for emails** page, select **Next**.

1. On the **Default settings for meetings and calendar events** page, select **Next**.

1. On the **Default settings for Fabric and Power BI content** page, select **Next**.

1. On the **Name your policy** page, enter:

   - **Name**: `Internal HR employee data`
   - **Enter a description for your sensitivity label policy**: `This HR label is to be applied to internal HR employee data.`

1. Select **Next**.

1. On the **Review and finish** page, select **Submit**.

1. On the **New policy created**, select **Done** to finish publishing your label policy.

You have successfully published the Internal and HR sensitivity labels. Note that it can take up to 24 hours for changes to replicate to all users and services.

## Task 4 – Create a client-side auto labeling policy

In this task, you'll create a client-side auto-labeling policy. Client-side auto-labels apply automatically to files and emails based on their content, ensuring that sensitive information is classified and protected before it leaves the user's device.

1. You should still be on the **Sensitivity labels** page in the Microsoft Purview portal. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. On the **Sensitivity labels** page, find the newly created **Internal** sensitivity label. Select the vertical ellipsis (**...**) next to it, then select **+ Create sublabel** from the dropdown menu.

1. The **New sensitivity label** configuration will start. On the **Provide basic details for this label** page, enter:

   - **Name**: `Confidential Research Data`
   - **Display name**: `Confidential Research Data`
   - **Description for users**: `This document or email contains sensitive research or development data that is proprietary to the organization.`
   - **Description for admins**: `This label is auto-applied to documents and emails containing information related to research, prototypes, or internal projects.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files**, **Emails**, and **Meetings**.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select **Apply content marking**, then select **Next**.

1. Select **Next**.

1. On the **Content marking** page, select the toggle to enable content marking.

1. If the checkbox for **Add a footer** is selected, deselect it, and select the checkbox for **Add a watermark**, then select **Customize text**.

1. In the **Customize watermark text** flyout pane, enter `Confidential - R&D Data` as **Watermark text**. Increase the **Font size** to `40`, then select **Save** at the bottom of the panel.

1. Back on the **Content marking** page, if other content marking options are enabled, disable them to ensure **Add a watermark** is the only option enabled.

1. Select **Next**.

1. On the **Auto-labeling for files and emails** page, set the **Auto-labeling for files and emails** to enabled.

1. In the **Detect content that matches these conditions** section, select **+ Add condition** > **Content contains**.

1. In **Content contains** section select the **Add** > **Trainable classifiers**.

1. In the **Trainable classifiers** flyout panel, add these trainable classifiers:

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

1. Select **Add** at the bottom of the panel to add these trainable classifiers.

1. Back on the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Publish label to users' apps**, then select **Done**.

1. On the **Publish label** flyout panel, select **Create new label policy**.

1. On the **Choose sensitivity labels to publish** page, select the **Choose sensitivity labels to publish** link.

1. Select the parent **Internal** label and the **Confidential Research Data** label that was just created, then select **Add**.

1. Back on the **Choose sensitivity labels to publish** page, select **Next**.

1. On the **Assign admin units** page, select **Next**.

1. On the **Publish to users and groups** page, select **Next**.

1. On the **Policy settings** page, select the checkbox for **Users must provide a justification to remove a label or lower its classification**, then select **Next**.

1. On the **Default settings for documents** page, select **Next** until you reach the **Name your policy** page.

1. On the **Name your policy** page, enter:

   - **Name**: `R&D Confidential Data Policy`
   - **Enter a description for your sensitivity label policy**: `Automatically applies labels to source code, project documents, and development files to protect sensitive R&D data.`

1. Select **Next**.

1. On the **Review and finish** page, select **Submit**.

1. On the **New policy created** page, select **Done**.

You have successfully created a client-side auto-labeling policy that will automatically apply the **Confidential Research Data** label to files and emails containing research and development data. It might take up to 24 hours for the policy to take full effect.

## Task 5 – Create a service-side auto labeling policy

In this task, you'll create a service-side auto-labeling policy. Service-side auto-labels are applied by cloud services like SharePoint, Exchange, and OneDrive after content is uploaded or received, ensuring that sensitive data is protected even if users don't manually classify it.

1. You should still be on the **Sensitivity labels** page in the Microsoft Purview portal. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. Expand the **Internal** label, then select the `Confidential Research Data` sublabel you created in a previous task.

1. In the **Confidential Research Data** flyout panel, you'll see the properties for the auto-label you created in a previous task. In this panel, select **Create auto-labeling policy**.

    ![Screenshot showing the option to create an auto-labeling policy.](../Media/create-auto-labeling-policy.png)

1. On the **Name your policy** page, enter:

   - **Name**: `R&D Confidential Data Container Policy`
   - **Enter a description for your sensitivity label policy**: `Automatically applies the Confidential Research Data label to content in SharePoint, Exchange, and OneDrive.`

1. Select **Next**.

1. On the **Assign admin units** page, select **Next**.

1. On the **Choose locations where you want to apply the label** page, leave **Exchange email**, **SharePoint sites**, and **OneDrive accounts** selected, then select **Next**.

1. On the **Set up common or advanced rules** page, leave **Common rules** selected, then select **Next**.

1. On the **Define rules for content in all locations** page, edit the **Confidential Research Data rule**.

    ![Screenshot where to edit the rule for a service-side auto-labeling policy.](../Media/auto-apply-labels-edit-rule.png)

1. In the **New rule** flyout panel, under **Conditions** > **Content contains** select the dropdown for **Add**, then select **Trainable classifiers**.

1. In the **Trainable classifiers** flyout panel, add these trainable classifiers:

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

   This ensures consistent protection between client-side and service-side labels.

1. Select **Add** at the bottom of the panel to add these trainable classifiers.

1. Back on the **Define rules for content in all locations** page, select **Next**.

1. On the **Choose a label to auto-apply**, leave the **Internal/Confidential Research Data** chosen, then select **Next**.

1. On the **Decide if you want to test out the policy now or later** page, select **Run policy in simulation mode**, and select the checkbox for **Automatically turn on policy if not modified after 7 days in simulation**, then select **Next**.

1. On the **Review and finish** page, select **Create policy**.

1. On the **Your auto-labeling policy was created** page, select **Done**.

You have successfully created a service-side auto-labeling policy that will automatically apply the **Confidential Research Data** label to content stored or shared in SharePoint, Exchange, and OneDrive. It might take up to 24 hours for the policy to take effect.

-->
## Tâche 2 : créer un groupe d’étiquettes

Dans cette tâche, vous allez créer un groupe d’étiquettes afin d’organiser les étiquettes de confidentialité internes. Les groupes d’étiquettes servent de conteneurs pour les étiquettes liées, telles que les classifications par service ou par unité commerciale.

1. Vous devez toujours être connecté au portail Microsoft Purview en tant qu’administrateur de conformité.

1. Dans **Microsoft Edge**, accédez à `https://purview.microsoft.com`.

1. Dans le portail Microsoft Purview, sélectionnez **Solutions** dans la barre latérale de gauche, puis sélectionnez **Protection des données**.

1. Sur la page **Protection des données Microsoft**, dans la barre latérale de gauche, sélectionnez **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, sélectionnez **+ Créer** > **Groupe d’étiquettes**.

1. La configuration du **Nouveau groupe d’étiquettes** démarre. Sur la page **Fournir les informations de base pour ce groupe d’étiquettes**, entrez :

    - **Nom :** `Internal`
    - **Nom d’affichage** : `Internal`
    - **Description pour les utilisateurs** : `Internal sensitivity label.`
    - **Description pour les administrateurs** : `Internal sensitivity label group for Contoso.`

1. Cliquez sur **Suivant**.

1. Sur la page **Passez en revue vos paramètres et terminez**, sélectionnez **Créer un groupe d’étiquettes**.

1. Sur la page **Votre groupe d’étiquettes a été créé avec succès**, sélectionnez **Ne pas créer d’étiquette pour le moment**, puis sélectionnez **Terminé**.

Vous avez créé un groupe d’étiquettes à usage interne. Ce groupe vous aide à gérer les étiquettes associées à des services ou à des catégories de données spécifiques.

## Tâche 3 : créer une étiquette enfant

Maintenant que vous avez créé un groupe d’étiquettes, vous allez ajouter une étiquette enfant pour le contenu lié aux ressources humaines. Cette étiquette applique un chiffrement et des marquages de contenu afin de protéger les données RH contre tout accès non autorisé.

1. Sur la page **Étiquettes de confidentialité**, recherchez le groupe d’étiquettes de confidentialité **Interne**. Sélectionnez les points de suspension verticaux (**...**) à côté, puis sélectionnez **+ Créer une étiquette dans le groupe** dans le menu déroulant.

    ![Capture d’écran montrant le menu Action permettant de créer une étiquette dans le groupe pour une étiquette de confidentialité.](../Media/create-label-in-group.png)

1. L’assistant **Nouvelle étiquette de confidentialité** démarre alors. Sur la page **Fournir des détails de base pour cette étiquette**, saisissez :

   - **Nom :** `Employee data (HR)`
   - **Nom d’affichage** : `Employee data (HR)`
   - **Description pour les utilisateurs** : `This HR label is the default label for all specified documents in the HR Department.`
   - **Description pour les administrateurs** : `This label is created in consultation with Ms. Jones (Head of the HR department). Contact her if you need to change the label settings.`

1. Cliquez sur **Suivant**.

1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Fichiers** et **E-mails**. Si la case **Réunions** est cochée, décochez-la.

1. Cliquez sur **Suivant**.

1. Sur la page **Choisir les paramètres de protection des éléments étiquetés**, sélectionnez les options **Contrôle d’accès** et **Appliquer le marquage du contenu**, puis sélectionnez **Suivant**.

1. Sur la page **Contrôle d’accès**, sélectionnez **Configurer les paramètres de contrôle d’accès**.

1. Configurez les paramètres de chiffrement avec les options suivantes :

   - **Attribuer des autorisations maintenant ou laisser les utilisateurs décider ?**  : attribuer des autorisations maintenant.
   - **L’accès des utilisateurs au contenu expire** : jamais.
   - **Autoriser l’accès hors connexion** : uniquement pendant un certain nombre de jours.
   - **Les utilisateurs disposent d’un accès hors connexion au contenu pendant ce nombre de jours** : 15.
   - Sélectionnez le lien **Attribuer des autorisations**. Dans le panneau volant **Attribuer des autorisations**, sélectionnez **+ Ajouter des utilisateurs authentifiés**, puis sélectionnez **Enregistrer** pour appliquer ce paramètre.

1. Sur la page **Contrôle d’accès**, sélectionnez **Suivant**.

1. Sur la page **Marquage du contenu**, sélectionnez le bouton pour activer le **Marquage du contenu**.

1. Pour chacun des types de marquage suivants, cochez la case, puis sélectionnez l’icône d’édition pour entrer le texte :

   |Type de marquage|Détails|
   |:---|:---|
   |Ajouter un filigrane|`INTERNAL USE ONLY`|
   |Ajouter un en-tête|`Internal Document`|
   |Ajouter un pied de page|`Contoso Confidential`|

1. Cliquez sur **Suivant**.

1. Sur la page **Étiquetage automatique des fichiers et des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Définir les paramètres de protection pour les groupes et les sites**, sélectionnez **Suivant**.

1. Dans la page **Vérifier vos paramètres et terminer**, sélectionnez **Créer une étiquette**.

1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Ne pas créer de stratégie pour le moment**, puis **Terminé**.

Vous avez créé une étiquette enfant dans le groupe d’étiquettes Interne. L’étiquette applique un chiffrement et des marquages de contenu aux documents RH, ce qui permet d’identifier plus facilement les données confidentielles et de les protéger via la stratégie.

## Tâche 4 : publier des étiquettes

Ensuite, vous allez publier l’étiquette RH du groupe d’étiquettes Interne afin que les utilisateurs du service RH puissent l’appliquer à leurs documents.

1. Vous devez toujours être connecté au portail Microsoft Purview en tant qu’administrateur de conformité.

1. Dans **Microsoft Edge**, l’onglet du portail Microsoft Purview devrait encore être ouvert. Si ce n’est pas le cas, accédez à **`https://purview.microsoft.com`** > **Solutions** > **Protection des données** > **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, sélectionnez **Publier des étiquettes**.

1. La configuration de la publication des étiquettes de confidentialité démarre alors.

1. Sur la page **Choisir les étiquettes de confidentialité à publier**, sélectionnez le lien **Choisir les étiquettes de confidentialité à publier**.

1. Dans le panneau volant **Étiquettes de confidentialité à publier**, cochez la case  **Données internes/employés (RH)**, puis sélectionnez **Ajouter** en bas de la page volante.

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

1. Dans la page **Nouvelle stratégie créée**, sélectionnez **Terminé** pour terminer la publication de votre stratégie d’étiquette.

Vous avez publié le groupe d’étiquettes Interne et son étiquette RH afin que les utilisateurs puissent les appliquer aux documents RH. La propagation de la stratégie dans les services peut prendre jusqu’à 24 heures.

## Tâche 5 : configurer l’étiquetage automatique

Vous allez maintenant créer une étiquette enfant pour les données financières et la configurer pour qu’elle s’applique automatiquement au contenu contenant des identifiants financiers tels que les numéros de carte de crédit ou les numéros d’acheminement bancaire.

1. Vous devez toujours être connecté au portail Microsoft Purview en tant qu’administrateur de conformité.

1. Dans **Microsoft Edge**, accédez à `https://purview.microsoft.com` et connectez-vous au portail Microsoft Purview en tant qu'administrateur de la conformité.

1. Dans le portail Microsoft Purview, sélectionnez **Solutions** > **Protection des informations** > **Étiquettes de confidentialité**.

1. Sur la page **Étiquettes de confidentialité**, recherchez l’étiquette de confidentialité **Interne**. Sélectionnez les points de suspension verticaux (**...**), puis sélectionnez **+ Créer une étiquette dans le groupe** dans le menu déroulant.

1. Sur la page **Fournir des détails de base pour cette étiquette**, saisissez :

   |Détails|Détails|
   |---|---|
   |**Nom**|`Financial Data`|
   |**Nom complet**|`Financial Data`|
   |**Description pour les utilisateurs**|`This content contains financial data that must be labeled and protected.`|
   |**Description pour les administrateurs**|`This label is used for content that includes sensitive financial identifiers.`|

1. Cliquez sur **Suivant**.

1. Dans la page **Définir l’étendue de cette étiquette**, sélectionnez **Fichiers** et **E-mails**. Si la case **Réunions** est cochée, décochez-la.

1. Cliquez sur **Suivant**.

1. Sur la page **Choisir les paramètres de protection pour les éléments étiquetés**, sélectionnez **Suivant**.

1. Sur la page **Étiquetage automatique des fichiers et des e-mails**, activez l’option **Étiquetage automatique des fichiers et des e-mails**.

1. Dans la section **Détecter le contenu qui correspond à ces conditions**, sélectionnez **+ Ajouter une condition** > **Contenu contenant**.

1. Dans la section **Le contenu contient**, sélectionnez **Ajouter** > **Types d’informations confidentielles**.

1. Dans la page volante **Types d’informations sensibles**, recherchez et sélectionnez ces types d’informations sensibles :

   - `Credit Card Number`
   - `ABA Routing Number`
   - `SWIFT Code`

1. Sélectionnez **Ajouter**.

1. De retour sur la page **Étiquetage automatique des fichiers et des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Définir les paramètres de protection pour les groupes et les sites**, sélectionnez **Suivant**.

1. Dans la page **Vérifier vos paramètres et terminer**, sélectionnez **Créer une étiquette**.

1. Dans la page **Votre étiquette de confidentialité a été créée**, sélectionnez **Appliquer automatiquement l’étiquette au contenu sensible**, puis sélectionnez **Terminé**.

1. Dans la page volante **Créer une stratégie d’étiquetage automatique**, sélectionnez **Vérifier la stratégie**.

1. Dans la page **Nommer votre stratégie d’étiquetage automatique**, conservez la valeur par défaut, puis sélectionnez **Suivant**.

1. Dans la page **Choisir une étiquette à appliquer automatiquement**, vérifiez que l’étiquette _Données internes/financières_ est sélectionnée, puis sélectionnez **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Dans la page **Choisir les emplacements où vous souhaitez appliquer l’étiquette**, sélectionnez les options pour :

   - Messagerie Exchange
   - Sites SharePoint
   - Comptes OneDrive

1. Cliquez sur **Suivant**.

1. Sur la page **Configurer des règles courantes ou avancées**, laissez l’option par défaut **Règles courantes** sélectionnée, puis sélectionnez **Suivant**.

1. Dans la page **Définir des règles pour le contenu de tous les emplacements**, développez les règles pour la _Règle de données financières_ pour vous assurer que les règles attendues sont définies, puis sélectionnez **Suivant**.

1. Sur la page **Paramètres supplémentaires des e-mails**, sélectionnez **Suivant**.

1. Sur la page **Décider si vous souhaitez tester la stratégie maintenant ou ultérieurement**, sélectionnez **Exécuter la stratégie en mode simulation** et cochez la case **Activer automatiquement la stratégie si elle n’est pas modifiée après 7 jours de simulation**.

1. Cliquez sur **Suivant**.

1. Sur la page **Vérifier et terminer**, sélectionnez **Créer la stratégie**.

1. Dans la page **Votre stratégie d’étiquetage automatique a été créée**, sélectionnez **Terminé**.

Vous avez organisé des étiquettes dans un groupe, les a publiées pour les utilisateurs et activé l’étiquetage automatique afin que le contenu sensible soit protégé sans compter sur les utilisateurs.
