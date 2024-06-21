# Exercice 2 : Manipulations pratiques sur VM Linux

## Partie 1 : Gestion des utilisateurs

**Q.2.1.1**

Compte personnel `thomas` créé, avec la commande `adduser` : 

![2024-06-21 10_59_04-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/8745aed3-920a-4ba0-8aff-295aeac8868d)

**Q.2.1.2**

Nous pouvons l'ajouter au groupe `sudo`, avec la commande `usermod -aG sudo <user>` : 

![2024-06-21 11_00_51-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/30bef43e-9b36-4360-8300-8642d8910c46)

## Partie 2 : Configuration de SSH

Pour les 3 questions suivantes, nous allons éditer le fichier `/etc/ssh/sshd_config`

**Q.2.2.1**

Désactivation de l'utilisateur `root` -> `PermitRootLogin no` : 

![2024-06-21 12_32_02-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/61494bc3-e722-4e26-91cd-664b40aa2843)

**Q.2.2.2**

Autorisation du compte personnel uniquement -> `AllowUsers thomas` : 

![2024-06-21 11_31_10-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/c0961e40-7a58-4cd1-8cee-aff2445e424b)

**Q.2.2.3**

Authentification par clés et désactivation de l'authentification par mot de passe : 

`PubkeyAuthentication yes`
`AuthenticationMethods publickey`
`PasswordAuthentication no`

![2024-06-21 11_14_28-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/efaddf98-cf56-4746-8af4-979c6aeb7702)

![2024-06-21 11_31_10-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/0059b22c-39fd-4c37-91e9-da6bfac245a7)

![2024-06-21 11_32_04-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/719b8f89-621f-4fea-a28a-ee820d1621d8)










