# Exercice 1 : Manipulations pratiques sur VM Windows

## Partie 1 : Gestion des utilisateurs

**Q.1.1.1**

`Kelly Rhameur` se situe dans la sous-OU **DirectionDesRessourcesHumaines**, de l'OU principale **LabUsers**

![2024-06-21 09_29_01-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/9e560562-6cca-45b5-986c-e1000a291fbe)

Nous allons donc créer l'utilisateur `Lionel Lemarchand` avec les même attributs de société que `Kelly Rhameur`

![2024-06-21 09_34_28-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/6445b76d-085b-42d6-ab46-c7c26d2304b2)

`Lionel Lemarchand` et `Kelly Rhameur` ont les mêmes attributs : 

![2024-06-21 09_35_37-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/5364e8b4-500f-41d3-b9be-16ff2434cc3d)


**Q.1.1.2**

Création de l'OU **DeactivatedUsers** : 

![2024-06-21 09_41_13-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/1fb89763-333b-4228-9aa5-26c14baa6807)

Déplacement de `Kelly Rhameur` dans l'OU créée : 

![2024-06-21 09_41_56-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/1d768d30-646b-4f31-a17c-ada25ee86f75)

Désactivation du compte de `Kelly Rhameur` -> Clic droit sur le compte, puis `Disable Account` : 

![2024-06-21 10_24_46-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/4c92e638-3894-4d00-8721-73b85421000a)

![2024-06-21 10_24_58-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/79937329-022f-4b0b-a6d9-a6c095b3dc3c)



**Q.1.1.3**

Retrait de `Kelly Rhameur` du groupe **Direction des Ressources Humaines** : 

![2024-06-21 09_43_23-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/4ec37072-784b-4635-8082-6acceea5042d)

**Q.1.1.4**

Se rendre dans le disque `F:`, puis créér un dossier `lionel.lemarchand` et renommer le dossier de `Kelly Rhameur` en `kelly.rhameur-ARCHIVE`

![2024-06-21 09_48_13-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/efc75f2e-a751-4e3e-af21-c65e8ad2e5f3)


## Partie 2 : Restriction utilisateurs

**Q.1.2.1**

Recherche de l'utilisateur `Gabriel Guhl` -> Clic droit sur son compte -> `Properties` -> Onglet `Account` -> Clic sur `Logon Hours` -> Editer les heures pour n'autoriser la connexion que de 7h à 17h, du lundi au vendredi : 

![2024-06-21 09_54_31-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/6a7c3f20-bac1-4018-a2dd-588c45b6f678)


**Q.1.2.2**

Toujours dans l'onglet `Account` -> Cliquer sur `Log On To` -> Cocher la case `The following computers` -> Inscrire `CLIENT01` -> Cliquer sur `Add` -> Cliquer sur `OK`

![2024-06-21 09_55_17-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/8d2714df-a341-4728-ac6a-36a2ba2bab6f)


**Q.1.2.3**

Se rendre sur le `Server Manager` -> Cliquer sur `Tools` -> Cliquer sur `Group Policy Management` -> Faire un clic droit sur l'OU **LabUsers** -> Cliquer sur `Create a GPO in this domain, and Link it here ...` -> Donner un nom à la GPO : 

![2024-06-21 09_57_55-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/15c042be-538a-4c21-88ce-3469a75d7ff1)

Clic droit sur la GPO -> Cliquer sur `Edit` -> Se rendre dans `Computer Configuration / Policies / Windows Settings / Security Settings / Account Policies / Password Policy` -> Double-cliquer sur `Password must meet complexity requirements` -> Cocher la case `Enabled` -> Cliquer sur `OK`

![2024-06-21 10_02_08-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/0ce15524-0e16-4a3f-8a5c-2c6ee6f4ec00)

Pour aller plus loin, nous pouvons également définir une taille minimum de mot de passe, içi 10 caractères : 

![2024-06-21 10_48_06-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/b380b593-cc4f-43c4-a901-834af044e2f1)


## Partie 3 : Lecteurs réseaux

**Q.1.3.1

Avant de monter les lecteurs `E` et `F`, nous devons mettre en place le partage de ces deux disques, (Ci-dessous, ce qui a été fait pour `E`) : 

![2024-06-21 10_08_11-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/f48c888a-0e80-4aaf-a3a1-288cb11c264b)

Création de la GPO Drive-Mount : 

![2024-06-21 10_03_37-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/6043aee2-de5c-4e34-b31b-0e00d69a9538)

Mappage des lecteur `E` et `F` (Ci-dessous, ce qui a été fait pour `E`) :

![2024-06-21 10_04_17-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/32b59c06-5af4-4898-9c19-bd93df3d3c22)

![2024-06-21 10_13_21-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/f51ca9b7-4b7c-46d7-a77a-2f9b36a2ddb3)

Une fois les deux lecteurs mappés, nous devrions avoir ça : 

![2024-06-21 10_17_32-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/5dcd17fc-9711-4232-a95a-be3acb6b1ba8)

ATTENTION : Bien penser à appliquer les GPO précédemment créées avant la commande `gpupdate /force` : 

![2024-06-21 10_19_56-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/96d5d854-0504-45b5-ac5e-e5aceb718ced)












