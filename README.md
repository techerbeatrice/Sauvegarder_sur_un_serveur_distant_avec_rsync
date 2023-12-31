# Sauvegarder sur un serveur distant avec rsync   

rsync est un protocole client/serveur et un outil de synchronisation entre dossiers source et destination éventuellement à distance.   

___

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/80b04666-158b-4ed5-b012-7c0a092d212a)

___

vm distante ssh  

installer sur la vm distante le service ssh avec **sudo apt install openssh-server -y**   et configurer le ficher conf ssh **sudo nano /etc/ssh/sshd_config**  

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/81527e6f-25a1-401e-8a49-2db6e60f5867)
![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/17689a75-742f-4551-b8f6-97cc6cc499f6)
![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/6966db8b-91d0-4015-b398-819e302a3fbf)

___

générer une paire de clés sur la vm locale   
connection à partir de la vm locale en ssh à la vm distante    

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/8a245534-7e45-46bd-ad4f-b7fda768a84a)

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/3ed63830-3c1c-4e81-8c51-d0e0ffa6ebfe)

___

connection par clé (sans mot de passe)    
copier le certificat public **rsa.pub** dans la vm distante avec la commande **ssh-copy-id beatrice@192.168.1.93**       

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/f923bc60-824f-453f-a35f-ea11c8c8fe7f)

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/cb401f82-7307-4974-bc84-cf0983ddef80)

___

Logout du ssh   

sur les 2vm (la locale + la distante), avoir **rsync** d'installé      
Ubuntu 22.04 contient déjà le package **rsync installé**. Pour vérifier cela et connaître la version, utilisez la commande : **sudo rsync --version** sinon faire un **sudo apt install rsync**   

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/127e3e38-1f1c-4af2-a39b-b1203a71a734)

___
   
et toujours sur les 2vm, démarrer maintenant le service rsync avec la commmande **sudo systemctl restart rsync**  

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/056eb685-a202-44fb-963a-7131b34a5643)

___

Créer un dossier avec des fichiers sur la vm locale  

et  

Transférer des fichiers à la vm distante avec Rsync via SSH avec la commande : **rsync -a ~/Bureau/originedirectory beatrice@192.168.1.93:~/Bureau/destinationdirectory**   

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/ceacb3a0-bb3b-4c85-81bd-3d2f36d0d7df)

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/41495430-1592-4460-8104-844f04a7e5fd)

