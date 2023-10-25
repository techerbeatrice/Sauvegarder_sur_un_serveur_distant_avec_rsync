# Sauvegarder sur un serveur distant avec rsync   

rsync est un protocole client/serveur et un outil de synchronisation entre dossiers source et destination éventuellement à distance.   

___

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/80b04666-158b-4ed5-b012-7c0a092d212a)

___

vm server ssh  

installer service ssh avec **sudo apt install openssh-server -y**   et configurer le ficher conf ssh **sudo nano /etc/ssh/sshd_config**  

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/81527e6f-25a1-401e-8a49-2db6e60f5867)
![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/17689a75-742f-4551-b8f6-97cc6cc499f6)
![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/6966db8b-91d0-4015-b398-819e302a3fbf)

___

générer une paire de clés sur la vm cliente   
connection à partir de la vm cliente en ssh au vm serveur   

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/8a245534-7e45-46bd-ad4f-b7fda768a84a)

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/3ed63830-3c1c-4e81-8c51-d0e0ffa6ebfe)

___

connection par clé (sans mot de passe)    
copier le certificat public **rsa.pub** dans la vm distante avec la commande **ssh-copy-id beatrice@192.168.1.93**       

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/f923bc60-824f-453f-a35f-ea11c8c8fe7f)

![image](https://github.com/techerbeatrice/Sauvegarder_sur_un_serveur_distant_avec_rsync/assets/138071140/cb401f82-7307-4974-bc84-cf0983ddef80)

