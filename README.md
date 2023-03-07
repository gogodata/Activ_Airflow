# Activ_Airflow

Matériel utilisé : MAC M1 Pro 16g

MacOS : Ventura 13.2

Prérequis : 
Version MacOS à jour

Homebrew (packages manager)

Colima (runtimes docker)


Pour démarrer Airflow via colima, il faut lui donner assez de ressources.
Pour cela, on lance la commande de démarrage de colima avec des paramètres cpu et ram :
colima start --cpu 4 --memory 8 --disk 50

Suivre la procédure suivante : https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

Dans votre dossier, vous aurez ceci :

<img width="256" alt="image" src="https://user-images.githubusercontent.com/45535819/223383697-b8e9319e-928d-4233-ac79-656802fb691a.png">
