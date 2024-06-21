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

## Partie 3 : Analyse du stockage

**Q.2.3.1**

Types de fichiers montés : `ext2`, `lvm`, `ext4`, `swap`

![2024-06-21 11_35_25-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/ee4503d6-0522-47ac-8703-56e7328b81c9)

**Q.2.3.2**

Type de stockage : RAID et LVM

![2024-06-21 11_35_25-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/9d7bc308-ef47-4c08-b122-7583be4b9cfd)


**Q.2.3.3**

Ajout d'un disque de 8GO sur la VM

Etat du raid dégradé : 

![2024-06-21 11_39_37-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/0d8d2c16-2c67-4cca-a36c-ff6940cc2c14)

Formatage du nouveau disque : 

![2024-06-21 11_45_24-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/6b4dc985-863a-47a2-80b5-76a2b7b0e136)

Ajourt du disque au RAID

![2024-06-21 11_47_28-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/89092480-028d-45c2-ba1d-41b8f2ef2223)

RAID re-synchronisé : 

![2024-06-21 11_47_28-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/9f3fe4f4-6406-40ce-8552-f25e00ad4986)

![2024-06-21 11_48_02-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/e7c4fd75-37fd-4718-b45f-596e9df9d802)

**Q.2.3.4**

Création d'un volume de 2G appellé `sauvegarde` : 

![2024-06-21 12_05_44-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/c7e80c7c-3671-4e07-9146-15c901ed12e5)

![2024-06-21 12_06_18-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/f394c7fb-2c6a-4d7e-a84c-29765b18b114)

Formatage du nouveau vcolume en `ext4` : 

![2024-06-21 12_13_13-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/2c234aa7-ccc0-4774-94ff-634a995788d7)

Montage du LV dans le dossier `/var/lib/bareos/storage` : 

![2024-06-21 12_13_42-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/70e9c5fe-036a-45be-bba4-b5545f9002a9)

![2024-06-21 12_14_00-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/fd07f7e2-bfb8-4812-a66c-29e32ab4b877)

Edition du ficier `/etc/fstab` pour le montage automatique au démarrage : 

![2024-06-21 12_17_04-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/22b1ab96-7e14-4b1a-9f50-e1c6472f16aa)

**Q.2.3.5**

Taille disponible : 1.79 GO

![2024-06-21 12_19_00-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/ThoXinou/Checkpoint_3/assets/159007018/c9716cc8-4990-4f08-95d1-bda1be8c7a15)


## Partie 4 : Sauvegardes

**Q.2.4.1**

bareos-dir = Bareos Director, reponsable de tous les modules de Bareos
bareos-sd = Bareos Storage Daemon, service dédié aux sauvegardes
bareos-fd = Bareos File Daemon, collecte d'informations







