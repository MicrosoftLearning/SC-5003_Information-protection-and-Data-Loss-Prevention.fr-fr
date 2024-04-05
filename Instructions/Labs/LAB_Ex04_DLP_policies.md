---
lab:
  task: Create a data loss prevention (DLP) policy
  exercise: Exercise 4 - Create a data loss prevention (DLP) policy
---

# Tâches d’acquisition de compétences

Votre tâche consiste à développer et à appliquer une stratégie personnalisée de protection contre la perte de données (DLP) pour sécuriser les données client sensibles de votre organisation, tout en garantissant la conformité aux réglementations en matière de protection des données.

- **Créer une stratégie DLP personnalisée** en mode test pour monitorer les données sans mise en œuvre.
- **Définir une règle DLP avancée** ciblant des informations sensibles spécifiques.
- **Activer la stratégie DLP** pour mettre en œuvre activement les protections et la conformité.

**Objectif** : développer et implémenter une stratégie personnalisée de protection contre la perte de données (DLP) pour protéger les données client sensibles et garantir la conformité réglementaire. Vous commencerez par créer une stratégie DLP en mode test pour le monitoring initial, passerez à la conception d’une règle avancée ciblant des types spécifiques d’informations sensibles, puis activerez la stratégie pour appliquer la protection des données dans les communications par e-mail, SharePoint, OneDrive et Teams.

## Tâche 1 – Créer une stratégie personnalisée de protection contre la perte de données (DLP)

1. Accédez au portail de conformité Microsoft Purview.
1. Développez **Protection contre la perte de données**, puis sélectionnez **Stratégies**.
1. Dans la page **Stratégies**, sélectionnez **+ Créer une stratégie**.
1. Dans l’Assistant Stratégie DLP, dans **Démarrer avec un modèle ou créer une stratégie personnalisée**, sélectionnez :
   - Catégories : **Custom** (Personnalisé)
   - Réglementations : **Stratégie personnalisée**
1. Cliquez sur **Suivant**.
1. Dans la page **Nommer votre stratégie DLP**, entrez :
   - **Nom :** `Customer interaction protection policy`
   - **Description** : `This DLP policy protects customer data integrity and confidentiality in the Customer Service department by preventing unauthorized access and disclosure.`
1. Sélectionnez **Suivant** jusqu’à ce que vous arriviez à la page **Choisir où appliquer la stratégie**.
1. Dans la page **Choisir où appliquer la stratégie**, sélectionnez uniquement :
   - **Messagerie Exchange**
   - **Sites SharePoint**
   - **Comptes OneDrive**
   - **Messages de conversation et de canal Teams**
1. Cliquez sur **Suivant**.
1. Dans la page **Définir les paramètres de stratégie**, sélectionnez **Créer ou personnaliser des règles DLP avancées**, puis **Suivant**.
1. Dans **Personnaliser les règles DLP avancées**, sélectionnez **+ Créer une règle**.
1. Dans la page **Créer une règle** :
   - Dans le champ **Nom**, entrez `Customer data`.
   - Sous **Conditions**, sélectionnez **+ Ajouter une condition** > **Le contenu contient**.
   - Sous **Le contenu contient**, sélectionnez **Ajouter** > **Types d’informations sensibles**.
   - Dans la page **Classificateurs pouvant être formés** à droite, sélectionnez les classificateurs pour `Customer Complaints` et `Customer Files`, puis sélectionnez **Ajouter** en bas de la page pour ajouter ces classificateurs préformés.
   > [!tip] Utilisez la barre de recherche pour trouver facilement des classificateurs pouvant être formés.
   - De retour dans la page **Créer une règle**, sous **Le contenu contient**, sélectionnez **+ Ajouter une condition** > **Le contenu est partagé à partir de Microsoft365**.
   - Sous **Le contenu est partagé à partir de Microsoft365**, sélectionnez **avec des personnes extérieures à mon organisation** dans la liste déroulante.
   - Sous **Actions**, sélectionnez **+ Ajouter une action** > **Restreindre ou chiffrer le contenu dans les emplacements Microsoft 365**.
   - Sous **Restreindre ou chiffrer le contenu dans les emplacements Microsoft 365** vérifiez que la case d’option **Bloquer uniquement les personnes extérieures à votre organisation** est sélectionnée.
   - Sous **Notifications à l’utilisateur** positionnez le bouton bascule des notifications sur **Activé**, puis cochez la case **Notifier les utilisateurs du service Office 365 avec un conseil de stratégie**.
   - Sous **Remplacements utilisateur**, cochez la case **Autoriser les remplacements à partir des services Microsoft 365**.
   - Sous **Rapports d’incidents**, définissez **Utiliser ce niveau de gravité dans les alertes et les rapports d’administrateur** sur **Moyen**.
   - En bas de **Créer une règle**, sélectionnez **Enregistrer**.
1. De retour dans la page **Personnaliser les règles DLP avancées**, sélectionnez **Suivant**.
1. Dans la page **Mode stratégie**, sélectionnez **Exécuter la stratégie en mode test** et vérifiez que l’option **Afficher les conseils de stratégie en mode simulation** est activée, puis sélectionnez **Suivant**.
1. Dans la page **Vérifier et terminer**, sélectionnez **Envoyer**.
1. Dans la page **Nouvelle stratégie créée**, sélectionnez **Terminé**.

## Tâche 2 – Modifier une stratégie DLP

1. Dans la page **Stratégies**, cochez la case à gauche de la stratégie **Customer interaction protection policy** que vous venez de créer, puis sélectionnez **Modifier la règle** en haut de la page.
1. Une fois dans l’Assistant Création de stratégie DLP, sélectionnez **Suivant** jusqu’à ce que vous arriviez à la page **Mode de stratégie**, puis sélectionnez **Activer la stratégie immédiatement** pour appliquer la stratégie DLP.
1. Sélectionnez **Suivant** pour passer en revue la stratégie DLP, puis sélectionnez **Envoyer** après avoir examiné vos modifications.
1. Dans la page **Stratégie mise à jour**, sélectionnez **Terminé**.

Vous venez de créer une stratégie DLP pour protéger les données client sensibles.
