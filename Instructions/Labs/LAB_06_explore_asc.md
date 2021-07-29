---
lab:
    title: 'Découvrir Azure Security Center'
    module: 'Module 3, leçon 2 : Décrire les fonctionnalités des solutions de sécurité Microsoft : Décrire les fonctionnalités de gestion de la sécurité d’Azure'
---


# Labo : Découvrir Azure Security Center 

## Scénario du labo
Dans ce labo, vous allez découvrir Azure Security Center et apprendre à utiliser le Niveau de sécurité Azure pour améliorer la posture de sécurité de votre organisation.

  

**Durée estimée** : 10-15 minutes

#### Tâche 1 : Dans cette tâche, vous découvrirez brièvement Azure Security Center.
1.	Ouvrez Microsoft Edge. Dans la barre d’adresse, saisissez **portal.azure.com**.

1. Connectez-vous avec vos informations d’identification d’administrateur.
    1. Dans la fenêtre de connexion, saisissez **admin@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ représente votre ID de locataire unique fourni par votre fournisseur d’hébergement de labo), puis sélectionnez **Suivant**.
    
    1. Saisissez le mot de passe d’administrateur qui doit vous être fourni par votre fournisseur d’hébergement de labo. Sélectionnez **Se connecter**.
    1. Lorsque vous êtes invité à rester connecté, sélectionnez **Oui**.

1. Dans le coin supérieur gauche de l’écran, à côté de la mention Microsoft Azure, sélectionnez l’icône de menu Afficher le portail (les trois lignes horizontales également appelées icône Hamburger), puis sélectionnez **Tous les services**.  
1. Dans la zone Filtrer les services, saisissez **Centre de sécurité**, puis dans la liste des résultats, sélectionnez **Centre de sécurité**.
1. Prenez note des informations disponibles sur la page de présentation de Security Center.  
1. Il est possible qu’une zone d’informations bleue s’affiche en haut de la page. Cela signifie que vous consultez des informations limitées.  Sélectionnez **Cliquer ici**.
    1. Attribuez-vous le rôle nécessaire pour assurer la visibilité au niveau du locataire.  Sélectionnez **Administrateur de sécurité**, puis **Obtenir l’accès** au bas de la page.
   
     1. Le message suivant s’affichera probablement : Le groupe d’administration racine n’existe pas.  Conformément à la description, le système créera le groupe pour vous.  Cette opération peut prendre jusqu’à 15 minutes (mais elle est généralement plus rapide). Vous pouvez ensuite répéter le processus pour obtenir l’accès.  Une fois l’accès accordé, sélectionnez **Centre de sécurité** dans le coin supérieur gauche de la page, au-dessus de la mention Obtenir des autorisations, puis actualisez la page de présentation du Centre de sécurité.
1. Les informations en haut de la page incluent le nombre d’abonnements Azure, le nombre de ressources évaluées, le nombre de recommandations actives et les éventuelles alertes de sécurité.  Sur le corps de la page s’affichent des cartes qui représentent le niveau de sécurité, la conformité réglementaire, Insights, Azure Defender, etc.  
1. Sélectionnez **Ressources évaluées** en haut de la page.  Vous accédez ainsi à la page d’inventaire qui présente votre abonnement au Pass Azure.  Sélectionnez **Pass Azure - Parrainage**.
1. La page Resource Health vous fournit une liste de recommandations.  Dans cette liste, sélectionnez **Plusieurs propriétaires doivent être attribués à votre abonnement**. 
1. Cliquez sur la flèche de déroulement près des étapes de correction. Prenez note de la présence d’étapes de correction détaillées ainsi que de la possibilité de prendre des mesures.  
1. Sélectionnez **Security Center** en haut à gauche de l’écran pour revenir à la page de présentation de Security Center.
1. Sélectionnez **Recommandations actives** en haut de la page.  
1. La page des recommandations présente les actions spécifiques à entreprendre pour augmenter le niveau de sécurité potentiel.  Quittez la page des recommandations en sélectionnant le **X** dans le coin supérieur droit de l’écran.
1. Sur la page principale, sélectionnez **Conformité réglementaire**.
1. La page de conformité réglementaire fournit une liste de contrôles de conformité.  Sous chaque contrôle apparaît une liste d’évaluations fondées sur l’Azure Security Benchmark qui fournit des recommandations quant à la manière de sécuriser vos solutions cloud dans Azure.
1. Cliquez sur **IM. Gestion des identités**, puis cliquez sur **IM.4 : utiliser des contrôles d’authentification renforcés pour tous les accès basés sur Azure Active Directory**.  La liste indique les mesures concernant la responsabilité assumée par le client pouvant être prises pour améliorer la situation de conformité.
1. Sélectionnez le **X** dans le coin supérieur droit pour fermer la page et revenir à la page de présentation du Centre de sécurité. 
1. Gardez la page de présentation du Centre de sécurité ouverte. Vous l’utiliserez pour la tâche suivante.


#### Tâche 2 : Dans cette tâche, vous accéderez au Niveau de sécurité Azure et découvrirez les recommandations permettant d’améliorer votre niveau de sécurité. 

1. Sur la page de présentation du Centre de sécurité, sélectionnez la carte **Niveau de sécurité**.

2. Sélectionnez **Pass Azure - Parrainage**.  Notez votre niveau de sécurité.
3. Sur la page des recommandations, sélectionnez **Gérer les accès et les autorisations**. Notez qu’un élément de ce groupe est rouge.
4. Sélectionnez l’élément **Plusieurs propriétaires doivent être affectés à votre abonnement**, dont l’état d’intégrité des ressources est rouge. Si vous ne parvenez pas à sélectionner cet élément.
    1. Dans le coin supérieur gauche de la page, sélectionnez **Centre de sécurité** au-dessus de la mention Recommandations.
    
    1. Dans le volet de navigation de gauche, sélectionnez **Recommandations**.
    1. Sur la page des recommandations, sélectionnez **Gérer les accès et les autorisations**. Notez qu’un élément de ce groupe est rouge.
    1. Sélectionnez l’élément **Plusieurs propriétaires doivent être affectés à votre abonnement**, dont l’état d’intégrité des ressources est rouge. 
5. Sélectionnez l’**abonnement Azure**.
6. En haut de la page Contrôle d’accès (IAM), sélectionnez **+ Ajouter**. Ensuite, dans la liste déroulante, sélectionnez **Ajouter une attribution de rôle**.
7. Dans le champ Rôle, saisissez **Propriétaire**, puis sélectionnez **Propriétaire** dans la liste ci-dessous.
8. Dans la liste des utilisateurs, sélectionnez **Alexandre Lacroix**, puis sélectionnez **Enregistrer** au bas de la page.
9. La mise à jour du statut peut prendre jusqu’à 24 heures. Ensuite, votre niveau de sécurité sera également mis à jour dans la mesure où tous les éléments du groupe Gérer les accès et les autorisations sont respectés.
10. Dans le coin supérieur gauche de la page, au-dessus de la mention Pass Azure, sélectionnez **Centre de sécurité** puis **Présentation** pour revenir à la page de présentation du Centre de sécurité.
11. Gardez cette page ouverte pour la prochaine tâche.


#### Tâche 3 :  Rappelez-vous que le Centre de sécurité est proposé en deux modes : Azure Defender DÉSACTIVÉ (gratuit) et Azure Defender ACTIVÉ. Dans cette tâche, vous découvrez comment activer et désactiver Azure Defender.

1.	Sur la page de présentation du Centre de sécurité, sélectionnez l’option **Activer Azure Defender** depuis la carte Azure Defender.

2.	Cochez la case **Azure Defender activé**.  Notez le changement de statut de tous les plans Defender, qui deviennent actifs, ainsi que le prix de chaque élément, puis sélectionnez **Enregistrer** dans le coin supérieur gauche de la page.
3.	Revenez à la page du Centre de sécurité, en sélectionnant **Centre de sécurité** dans le coin supérieur gauche de la page.   Il se peut que la carte Azure Defender mette plusieurs minutes à refléter le changement.  Actualisez la page, si nécessaire.
4.	Pour désactiver Azure Defender, sélectionnez **Tarif et paramètres** dans le volet de navigation gauche de la page du Centre de sécurité, puis sélectionnez **Abonnement Pass Azure - Parrainage**.
5.	Sur la page des plans Azure Defender, cochez la case **Azure Defender désactivé**, puis sélectionnez **Enregistrer** dans le coin supérieur gauche de la page.
6.	Une fenêtre contextuelle apparaît et demande la confirmation du passage à une version antérieure.  Décochez la case permettant à Microsoft de vous contacter et sélectionnez **Confirmer**.
7.	Vous pouvez maintenant fermer l’onglet du navigateur pour quitter le portail Azure.


#### Révision
Dans ce labo, vous avez découvert Azure Security Center et appris à utiliser le Niveau de sécurité Azure pour améliorer la posture de sécurité de votre organisation.
