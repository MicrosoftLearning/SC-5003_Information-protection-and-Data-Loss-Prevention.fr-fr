---
lab:
  task: Create a data loss prevention (DLP) policy
  exercise: Exercise 3 - Create a data loss prevention (DLP) policy
---

# Tâches d’acquisition de compétences

**Tâches :**

1. Créer une stratégie DLP en mode simulation
1. Modifier une stratégie DLP
1. Créer une stratégie DLP dans PowerShell
1. Activer une stratégie en mode simulation

## Tâche 1 - Créer une stratégie DLP en mode simulation

Dans cet exercice, vous allez créer une stratégie de protection contre la perte de données (DLP) pour protéger les données sensibles contre le partage par les utilisateurs. La stratégie DLP que vous allez créer informera vos utilisateurs s’ils souhaitent partager du contenu qui contient des informations de carte de crédit et leur permettra de fournir une justification pour l’envoi de ces informations. La stratégie sera implémentée en mode simulation, car l’action de blocage ne doit pas affecter vos utilisateurs pour l’instant.

1. Dans **Microsoft Edge**, accédez à **`https://purview.microsoft.com`** et connectez-vous au portail Microsoft Purview en tant que l’utilisateur auquel vous avez accordé des droits d’**Administrateur de conformité**.

1. Sélectionnez **Solutions** dans la barre latérale à gauche, puis **Protection contre la perte de données**.

1. Sélectionnez **Stratégies** dans la barre latérale à gauche.

1. Sur la page **Stratégies**, sélectionnez **+ Créer une stratégie** pour commencer la configuration de la création d’une stratégie de protection contre la perte de données.

1. Sur la page **Démarrer avec un modèle ou créer une stratégie personnalisée**, sélectionnez **Personnalisé** pour la catégorie, puis sélectionnez **Stratégie personnalisée** dans **Réglementations**.

1. Cliquez sur **Suivant**.

1. Dans la page **Nommer votre stratégie DLP**, entrez :

   - **Nom :** `Credit Card DLP Policy`
   - **Description** : `Protect credit card numbers from being shared`

1. Cliquez sur **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Sur la page **Choisir les emplacements où appliquer la stratégie**, activez uniquement l’emplacement **Messages de conversation et de canal Teams**. Si d’autres emplacements sont sélectionnés, désélectionnez-les.

1. Cliquez sur **Suivant**.

1. Dans la page **Définir les paramètres de stratégie**, sélectionnez **Créer ou personnaliser des règles DLP avancées**, puis **Suivant**.

1. Sur la page **Personnaliser les règles DLP avancées**, sélectionnez **+ Créer une règle**.

1. Dans la page volante **Créer une règle**, saisissez `Credit card information` comme nom dans le champ **Nom**.

1. Dans **Conditions**, sélectionnez **+ Ajouter une condition**, puis **Contenu contenant**.

1. Dans la zone **Contenu contenant**, sélectionnez **Ajouter**, puis **Types d’informations sensibles**.

1. Sur la page **Types d’informations sensibles**, sélectionnez **Numéro de carte de crédit**, puis **Ajouter**.

1. Sélectionnez **+ Ajouter une condition**, puis **Contenu partagé à partir de Microsoft 365**.

1. Dans la nouvelle section **Contenu partagé à partir de Microsoft 365**, sélectionnez l’option **Uniquement avec les personnes de mon organisation**.

1. Dans **Actions**, sélectionnez **+ Ajouter une action**, puis **Restreindre l’accès ou chiffrer le contenu dans les emplacements Microsoft 365**.

1. Dans la nouvelle zone **Restreindre l’accès ou chiffrer le contenu dans les emplacements Microsoft 365**, sélectionnez **Bloquer tout le monde.**

1. Dans **Notifications des utilisateurs**, **activez** l’option **Utiliser des notifications pour informer vos utilisateurs et les former sur l’utilisation appropriée des informations sensibles**, puis cochez la case **Notifier les utilisateurs dans le service Office 365 avec un conseil de stratégie**.

1. Dans **Contournements pour les utilisateurs**, cochez la case **Autoriser les utilisateurs à contourner les restrictions de stratégie Fabric (y compris Power BI), Exchange, SharePoint, OneDrive et Teams.**

1. Cochez la case **Exiger une justification professionnelle pour contourner**.

1. Dans **Rapports d’incidents**, dans le menu déroulant **Utiliser ce niveau de gravité dans les alertes et les rapports d’administration**, sélectionnez **Bas**.

1. En bas du panneau volant **Créer une règle**, sélectionnez **Enregistrer**.

1. De retour sur **Personnaliser les règles DLP avancées**, sélectionnez **Suivant**.

1. Sur la page **Mode de stratégie**, sélectionnez **Exécuter la stratégie en mode simulation** et cochez la case **Afficher les conseils de stratégie en mode simulation**.

1. Cliquez sur **Suivant**.

1. Sur la page **Vérifier les paramètres et terminer**, vérifiez vos paramètres, puis sélectionnez **Envoyer**.

1. Dans la page **Nouvelle stratégie créée**, sélectionnez **Terminé**.

Vous avez maintenant créé une stratégie DLP qui vérifie la présence de numéros de carte de crédit dans les conversations et les canaux Microsoft Teams, permettant aux utilisateurs de fournir une justification professionnelle pour contourner la stratégie.

## Tâche 2 - Modifier une stratégie DLP

Dans cette tâche, vous allez modifier la stratégie DLP existante créée lors de la tâche précédente pour qu’elle analyse également les e-mails pour détecter la présence d’informations de cartes de crédit. Cette modification garantit que les données sensibles sont protégées dans un plus grand nombre de canaux de communication.

1. Vous devriez toujours être connecté à Microsoft 365 en tant que l’utilisateur que vous avez choisi pour être votre **Administrateur de conformité**.

1. Vous devriez toujours vous trouver sur la page **Stratégies** de Microsoft Purview. Si ce n’est pas le cas, ouvrez **Microsoft Edge** et accédez à `https://purview.microsoft.com`. Sélectionnez **Solutions** > **Protection contre la perte de données** > **Stratégies**.

1. Sur la page **Stratégies**, cochez la case de la **stratégie DLP de carte de crédit** récemment créée, puis sélectionnez **Modifier la stratégie** pour ouvrir la configuration de la stratégie.

1. Sur la page **Nommer votre stratégie DLP**, sélectionnez **Suivant**.

1. Sur la page **Affecter des unités d’administration**, sélectionnez **Suivant**.

1. Sur la page **Choisir les emplacements où appliquer la stratégie**, cochez la case **E-mail Exchange** pour ajouter cet emplacement à votre stratégie DLP.

1. Sélectionnez **Suivant** jusqu’à atteindre la page **Vérifier et terminer**.

1. Sélectionnez **Envoyer** sur la page **Vérifier et terminer** pour appliquer la modification que vous avez apportée à la stratégie.

1. Une fois la stratégie mise à jour, sélectionnez **Terminé** sur la page **Stratégie mise à jour**.

Vous avez correctement modifié la stratégie DLP pour inclure l’analyse des e-mails, améliorant ainsi la protection des informations sensibles.

## Tâche 3 - Créer une stratégie DLP dans PowerShell

Dans cette tâche, vous allez utiliser PowerShell pour créer une stratégie DLP afin de protéger les ID des employés de Contoso et empêcher leur partage via Exchange. Cette stratégie va notifier les utilisateurs qui tentent de partager ces données sensibles et bloquer l’e-mail s’il contient des ID d’employés.

1. Sur votre bureau, ouvrez une fenêtre PowerShell à privilèges élevés en cliquant avec le bouton droit sur le bouton Windows dans la barre des tâches, puis en sélectionnant **Terminal (admin)**.

1. Exécutez le cmdlet **Install Module** pour installer la dernière version du module **Exchange Online PowerShell** :

    ```powershell
    Install-Module ExchangeOnlineManagement
    ```

1. Confirmez la boîte de dialogue de sécurité du référentiel non approuvé en appuyant sur **Y** pour Oui, puis appuyez sur **Entrée**.  Ce processus peut prendre un certain temps.

1. Exécutez le cmdlet **Connect-IPPSSession** pour vous connecter au PowerShell de Sécurité et conformité :

   ```powershell
   Connect-IPPSSession
   ```

1. Connectez-vous en tant que l’utilisateur que vous avez désigné comme **Administrateur de conformité** dans la fenêtre contextuelle **Se connecter à votre compte**.

1. Exécutez le cmdlet **New-DlpCompliancePolicy** pour créer une stratégie DLP qui analyse toutes les boîtes aux lettres Exchange :

   ```powershell
   New-DlpCompliancePolicy -Name "EmployeeID DLP Policy" -Comment "This policy blocks sharing of Employee IDs" -ExchangeLocation All
   ```

1. Exécutez le cmdlet **New-DlpComplianceRule** pour ajouter une règle DLP à la stratégie DLP que vous avez créée lors de l’étape précédente :

   ```powershell
   New-DlpComplianceRule -Name "EmployeeID DLP rule" -Policy "EmployeeID DLP Policy" -BlockAccess $true -ContentContainsSensitiveInformation @{Name="Contoso Employee IDs"}
   ```

1. Exécutez le cmdlet **Get-DLPComplianceRule** pour vérifier la **règle DLP EmployeeID** :

   ```powershell
   Get-DLPComplianceRule -Identity "EmployeeID DLP rule"
   ```

Vous avez créé une stratégie DLP à l’aide de PowerShell qui analyse les ID des employés de Contoso dans Exchange.

## Tâche 4 - Activer une stratégie en mode simulation

Dans cette tâche, vous allez activer la **stratégie DLP de carte de crédit** que vous avez créée en mode simulation afin qu’elle applique ses actions de protection.

1. Vous devriez toujours être connecté à Microsoft 365 en tant que l’utilisateur que vous avez choisi pour être votre **Administrateur de conformité**.

1. Dans **Microsoft Edge**, accédez aux stratégies DLP via `https://purview.microsoft.com` > **Solutions** > **Protection contre la perte de données**, puis sélectionnez **Stratégies** dans la barre latérale de gauche.

1. Sur la page **Stratégies** , cochez la case de la **Stratégie DLP de carte de crédit** et sélectionnez **Modifier la stratégie** pour ouvrir la configuration de la stratégie.

1. Sélectionnez **Suivant** jusqu’à atteindre la page **Mode de stratégie**, puis sélectionnez **Activer immédiatement la stratégie**.

1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**.

1. Dans la page **Stratégie mise à jour**, sélectionnez **Terminé**.

Vous avez activé la stratégie DLP, ce qui permet de garantir que toutes les tentatives de partage d’informations de carte de crédit sont bloquées et nécessitent une justification professionnelle.
