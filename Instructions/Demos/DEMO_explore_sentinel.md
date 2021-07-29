---
Demo:
    title: 'Azure Sentinel'
    module: 'Module 3, leçon 3 : Décrire les fonctionnalités des solutions de sécurité Microsoft : Décrire les fonctionnalités de sécurité d’Azure Sentinel'
---


# Démonstration : Azure Sentinel 

### Scénario de la démonstration
Lors de cette démonstration, vous présenterez le processus de création d’une instance Azure Sentinel.  Vous définirez également les autorisations pour assurer l’accès aux ressources qui vont être déployées pour prendre en charge Azure Sentinel.  Une fois cette configuration de base effectuée, vous expliquerez les étapes pour connecter Sentinel à vos sources de données à l’aide d’analyses intégrées pour être informé en cas d’activité suspecte. Enfin, vous découvrirez les possibilités d’automatisation.  

#### Partie 1 de la démonstration :  Créez une instance Azure Sentinel.

1. Ouvrez l’onglet du navigateur intitulé **Accueil-Microsoft Azure**.  Si vous avez fermé l’onglet, ouvrez une page du navigateur et saisissez portal.azure.com dans la barre d’adresse. Ensuite, reconnectez-vous.

1. Dans la barre de recherche, dans la barre bleue en haut de la page à côté de là où il est indiqué Microsoft Azure, saisissez **Sentinel**, puis sélectionnez **Azure Sentinel** à partir des résultats de la recherche.

1. Depuis la page Azure Sentinel, sélectionnez **Créer Azure Sentinel**.

1. Depuis la page Ajouter Azure Sentinel à un espace de travail, sélectionnez **Créer un nouvel espace de travail**.

1. À partir de l’onglet de base de l’espace de travail Créer un journal d’analyses, saisissez les informations suivantes :
    1. Abonnement :  **Pass Azure - Parrainage**
    1. Groupe de ressources : sélectionnez **Créer un nouveau**, puis saisissez le nom **SC900-Sentinel-RG** et sélectionnez **OK**.
    1. Nom : **SC900-LogAnalytics-workspace**.
    1. Région : **USA Est** (conservez le paramètre par défaut)
    1. Sélectionnez **Suivant : Niveau tarifaire >**

1. Pour le niveau tarifaire, conservez les paramètres par défaut : **Paiement à l’utilisation (par Go 2018)**, puis sélectionnez **Suivant : Balises >**.

1. Pour les balises, vous pouvez laissez ce champ vide, puis sélectionnez **Examiner et créer**.

1. Vérifiez les informations que vous avez saisies, puis sélectionnez **Créer**.

1. Cela peut prendre une ou deux minutes avant que l’espace de travail n’apparaisse. Si vous ne le voyez toujours pas, sélectionnez **Actualiser**, puis **Ajouter**.

1. Une fois que le nouvel espace de travail est ajouté, la page | Azure Sentinel News & guides s’affichera.  Notez les trois étapes indiquées sur la page Mise en route.

1. Laissez cette page ouverte, vous en aurez besoin pour la tâche suivante.

#### Partie 2 de la démonstration :  Avec la création de l’instance Azure Sentinel, vous voudrez vous assurer que vous avez les accès nécessaires aux ressources qui sont déployées pour prendre en charge Azure Sentinel.  Pour cette tâche, vous vous rendrez sur la page de contrôle d’accès (IAM) pour le groupe de ressources que vous avez créé avec l’instance d’Azure Sentinel, vous afficherez les rôles disponibles et vous vous attribuerez le rôle nécessaire (administrateur MOD). Assigner le rôle pour le niveau de groupe de ressources garantira que le rôle s’applique à toutes les ressources qui sont déployées pour prendre en charge Azure Sentinel.

1. Dans la barre de recherche, dans la barre bleue en haut de la page à côté de là où il est indiqué Microsoft Azure, saisissez **groupes de ressources**, puis sélectionnez **Groupes de ressources** à partir des résultats de la recherche.

1. Depuis la page des groupes de ressources, sélectionnez le groupe de ressources que vous avez créé avec Azure Sentinel, **SC900-Sentinel-RG**.

1. Depuis la page SC900-Sentinel-RG, sélectionnez **Contrôle d’accès (IAM)** dans le volet de navigation à gauche.

1. Depuis la page Contrôle d’accès, sélectionnez **Afficher mon accès**.  Remarquez que le rôle actuel est Administrateur de service.  Fermez la fenêtre des attributions d’administrateur MOD en cliquant sur le **X** en haut à droite de la fenêtre.

1. Depuis la page Contrôle d’accès, sélectionnez **+Ajouter**, puis **Ajouter une attribution de rôle**.

1. La fenêtre d’attribution de rôle s’ouvre.  Sélectionnez la flèche déroulante vers le bas dans le champ Sélectionner un rôle afin d’afficher les rôles disponibles. Dans la barre de recherche Sélectionner un rôle, saisissez **Sentinel** pour afficher les quatre rôles associés à Sentinel. Nous recommandons d’attribuer le privilège minimum nécessaire pour ce rôle.  Pour les besoins de ce labo, saisissez **Propriétaire** dans la barre de recherche et sélectionnez **Propriétaire** à partir des résultats.  Pour référence, passez en revue les autorisations dans Azure Sentinel :  https://docs.microsoft.com/fr-fr/azure/sentinel/roles

1. Depuis la liste des utilisateurs affichés, sélectionnez **Administrateur MOD**.

1. Sélectionnez **Enregistrer** au bas de la page.

1. Depuis la page Contrôle d’accès, sélectionnez **Afficher mon accès** pour confirmer que le rôle a bien été ajouté, puis fermez la fenêtre en sélectionnant le **X** en haut à droite.

#### Partie 3 de la démonstration :  Dans cette partie de la démonstration, vous expliquerez le processus pour connecter Azure Sentinel à votre source de données pour commencer à collecter des données.  Remarque : le statut connecté d’un connecteur peut prendre un moment avant de s’afficher (environ 30 minutes selon le locataire).

1. Dans la barre de recherche, dans la barre bleue en haut de la page à côté de là où il est indiqué Microsoft Azure, saisissez **Sentinel**, puis sélectionnez **Azure Sentinel** à partir des résultats de la recherche.

1. Depuis la page Azure Sentinel, sélectionnez l’espace de travail que vous avez créé avec l’instance d’Azure Sentinel, **SC900-LogAnalytics-workspace**.

1. La première étape avec Azure Sentinel consiste à pouvoir collecter des données. Dans le volet de navigation à gauche, sélectionnez **Connecteurs de données**, qui se trouve sous configuration.

1. Depuis la page Connecteurs de données, sur la page principale, faites défiler vers le bas pour afficher la liste étendue des connecteurs disponibles. Dans la barre de recherche de la page des connecteurs de données, saisissez **Azure**, puis, à partir de la liste, sélectionnez **Azure Active Directory**.

1. La fenêtre de connecteur Azure Active Directory s’ouvre.  Sélectionnez **Ouvrir la page du connecteur**.

1. Depuis la page du connecteur Azure Active Directory, examinez la description et remarquez le contenu associé. Cela comprend les classeurs, les requêtes et les modèles de règles d’analyse.  

1. L’onglet des instructions de la fenêtre principale fournit les conditions requises pour qu’Azure Sentinel s’intègre à Azure Active Directory.   Sous configuration, sélectionnez **Journaux de connexion**, puis Appliquer les modifications (plusieurs connecteurs peuvent être choisis).  Remarque : le statut connecté du connecteur peut prendre un moment avant de s’afficher (environ 30 minutes).  Pour référence :
    1. Passez en revue les autorisations dans Azure Sentinel :  https://docs.microsoft.com/fr-fr/azure/sentinel/roles
    1. Connexion à Azure Active Directory :  https://docs.microsoft.com/fr-fr/azure/sentinel/connect-azure-active-directory

1. Depuis l’onglet Étapes suivantes, notez la liste de classeurs recommandés.   Sous classeurs recommandés, sélectionnez **Journaux de connexion Azure** (des classeurs supplémentaires peuvent être choisis).

1. Depuis la page des classeurs et avec l’onglet modèles sélectionné (souligné), sélectionnez **Journaux de connexion Azure**.

1. Depuis la fenêtre Journaux de connexion Azure AD qui s’ouvre, examinez la description et sélectionnez **Afficher le modèle**.  Fermez le modèle en sélectionnant le **X** en haut à droite de l’écran.  Sélectionnez **Enregistrer** en bas de la page, puis sélectionnez **OK** pour enregistrer le classeur à l’emplacement par défaut.

1. En haut à gauche de la page Classeurs, au-dessus de Classeurs, sélectionnez **Azure Sentinel**. Cela vous fait revenir à la page des connecteurs de données Azure Sentinel.

1. Le haut de la page Connecteurs de données doit afficher 1 connecté, afin de refléter le fait que vous êtes connecté à Azure Active Directory.

1. Dans le volet de navigation à gauche, sélectionnez **Classeurs**.

1. Depuis la page Classeurs, sélectionnez l’onglet **Mes classeurs** qui se trouve au-dessus de la barre de recherche.  Le classeur que vous venez d’enregistrer est répertorié et disponible pour que vous puissiez visualiser et contrôler vos données.  Les connexions suivantes apparaîtront dans le classeur. Vous pouvez donc choisir de les afficher.

1. Laissez cette page ouverte, vous en aurez besoin pour la tâche suivante.

#### Partie 4 de la démonstration (facultative) :  Dans cette partie de la démonstration, vous expliquerez le processus d’utilisation d’un modèle de règle d’analyse intégré afin de créer une règle pour être informé en cas d’activité suspecte.

1. Dans le volet de navigation à gauche, sélectionnez **Analyse**.

1. La page Analyse affiche les règles actives (la détection avancée des attaques multiphases est activée par défaut) et permet d’accéder aux modèles de règle.  Sélectionnez l’onglet **Modèles de règle**.  Notez la liste des modèles disponibles et les différentes façons de filtrer la liste.  Les alertes d’analyse intégrées au sein de l’espace de travail Azure Sentinel vous informent en cas d’activité suspecte.

1. Dans la barre de recherche, saisissez **Portail Azure**.  Sélectionnez **Échec des tentatives de connexions au portail Azure**.  

1. Depuis la fenêtre qui s’ouvre, lisez la description et examinez les informations associées au modèle.  Sélectionnez **Créer une règle** au bas de la page.
    1. Depuis l’assistant Règle d’analyse, examinez les informations, puis sélectionnez **Suivant : Définir la logique de la règle >**.
    1. C’est sur la page Définir la logique de la règle que vous définissez la logique pour votre nouvelle règle d’analyse. Le modèle fournit déjà une certaine logique et des paramètres prédéfinis.  Faites défiler la page pour voir les paramètres disponibles.  Conservez les paramètres par défaut. Sélectionnez **Suivant : Paramètres d’incident (préversion) >**.
    1. Avec les paramètres d’incident, les alertes Azure Sentinel peuvent être regroupées en un incident qui doit être examiné. Vous pouvez définir si les alertes qui sont déclenchées par cette règle d’analyse doivent générer des incidents ou non.  Conservez les paramètres par défaut et sélectionnez **Suivant : Réponse automatisée >**.
    1. Dans l’onglet Réponse automatisée, remarquez comment vous pouvez ajouter un playbook pour automatiser la réponse.  De la même façon, vous pouvez créer une règle d’automatisation d’incident.  Sélectionnez **+ Ajouter** une nouvelle sous l’automatisation d’incident.  Une fenêtre pour créer une nouvelle règle d’automatisation s’ouvre.  Toutes les règles d’automatisation que vous créez sur cette page sont déclenchées par la règle d’analyse que vous   Remarquez que vous pouvez ajouter des conditions et définir des actions pour la règle.   Cliquez sur **Annuler** pour quitter la fenêtre.
    1. Sélectionnez **Suivant : Révision>** pour revoir tous les détails associés à la règle et basés sur le modèle choisi. Vous pouvez maintenant choisir de créer la règle en sélectionnant **Créer** ou quitter sans créer de règle en sélectionnant le **X** en haut à droite de la page.

1. Laissez cette page ouverte, vous en aurez besoin pour la tâche suivante.

#### Partie 5 de la démonstration (facultative) :  À l’étape précédente, vous avez créé une règle d’analyse pour être informé en cas d’activité suspecte.  L’option permettant d’automatiser la réponse à un incident basé sur une règle spécifique est incluse dans cet assistant.  Mais vous pouvez aussi créer des règles d’automatisation en accédant directement à l’option de configuration d’automatisation.

1. Dans le volet de navigation à gauche, sélectionnez **Automatisation**.  

1. Sélectionnez **+ Créer**. À partir du menu déroulant, remarquez comment vous pouvez choisir d’ajouter un nouveau playbook ou une nouvelle règle.  Sélectionnez **Ajouter une nouvelle règle**.  
    1. Une fenêtre pour créer une nouvelle règle d’automatisation s’ouvre.  Remarquez que vous pouvez ajouter des conditions et définir des actions pour la règle.  La seule distinction est que la première condition est d’associer les règles d’analyse auxquelles vous voulez appliquer cette règle d’automatisation.  Cette option était grisée lors de la tâche précédente, car l’automatisation était configurée pour la règle spécifique.  Sélectionnez **Annuler** pour quitter la fenêtre Créer une nouvelle règle d’automatisation.

1. Laissez cette page ouverte, vous en aurez besoin pour la tâche suivante.

#### Étape 6 : DESTRUCTION - Instructeur, effectuez cette étape après la classe. Supprimez un groupe de ressources Azure Sentinel.  Azure Sentinel est facturé en fonction du volume de données ingérées pour l’analyse dans Azure Sentinel. Bien que la quantité de données ingérées dans le cadre de ce labo soit minime, nous vous recommandons de supprimer le groupe de ressources Azure Sentinel quand vous avez fini de découvrir les fonctionnalités et les possibilités d’Azure Sentinel.

1. Depuis la page Azure Sentinel, en haut à gauche, où il est indiqué Azure Sentinel, sélectionnez **Tous les services**.

1. Dans la barre de services de filtrage, saisissez groupes de ressources, puis à partir de la liste, sélectionnez **Groupes de ressources**.

1. Depuis la page des groupes de ressources, sélectionnez le groupe de ressources que vous avez créé avec Azure Sentinel, **SC900-Sentinel-RG**.

1. En haut au centre de la page, sélectionnez **Supprimer le groupe de ressources**.  Passez en revue l’avertissement.  Saisissez le nom du groupe de ressources, **SC900-Sentinel-RG**, puis sélectionnez **Supprimer** en bas de la page.  La suppression du groupe de ressources prend plusieurs minutes.

1. Une fois que vous avez vérifié que le groupe de ressources est bien supprimé, fermez la page de navigation. 

#### Révision

Lors de cette démonstration, vous avez présenté le processus de création d’une instance Azure Sentinel.  Vous avez également présenté comment définir les autorisations pour assurer l’accès aux ressources associées à votre instance Azure Sentinel.  Une fois l’instance Azure Sentinel créée, vous avez expliqué les étapes pour connecter Sentinel à vos sources de données, vous avez montré comment utiliser des règles d’analyse intégrées pour être informé en cas d’activité suspecte. Enfin, vous avez découvert les possibilités d’automatisation. Vous avez terminé cette démonstration en supprimant le groupe de ressources associé à l’instance Azure Sentinel que vous aviez créée.
