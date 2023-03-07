# Activ_Airflow

Matériel utilisé : MAC M1 Pro 16g

MacOS : Ventura 13.2

Prérequis :

Version MacOS à jour

Homebrew (packages manager)

Colima (runtimes docker)


Pour démarrer Airflow via colima, il faut lui donner assez de ressources donc on lance la commande de démarrage de colima avec des paramètres cpu et ram :

colima start --cpu 4 --memory 8 --disk 50


Puis on suit la procédure suivante : https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

Dans notre dossier, on aura ceci :

<img width="256" alt="image" src="https://user-images.githubusercontent.com/45535819/223383697-b8e9319e-928d-4233-ac79-656802fb691a.png">


On démarre les composants Airflow avec la commande docker compose up


On vérifie nos containers airflow avec la commande docker container ls

Tous les containers doivent être démarrés et en "Healthy"

On vérifie notre console Web airflow sur notre navigateur en appelant  http://localhost:8080/home
