# Activ_Airflow

Matériel utilisé : MAC M1 Pro 16g

MacOS : Ventura 13.2

# Prérequis

- Version MacOS à jour
- Homebrew (packages manager)
- Colima (runtimes docker)
- IDE (VS Code pour moi)

# Démarrrage

Pour démarrer Airflow via colima, il faut lui donner assez de ressources donc on lance la commande de démarrage de colima avec des paramètres cpu et ram :   
`colima start --cpu 4 --memory 8 --disk 50`. 

Puis on suit la procédure suivante : https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

Dans notre dossier, on aura ceci :  
<img width="256" alt="image" src="https://user-images.githubusercontent.com/45535819/223383697-b8e9319e-928d-4233-ac79-656802fb691a.png">


Une fois les composants Airflow démarrés avec la commande docker compose up.  
On vérifie nos containers airflow avec la commande `docker container ls` ou `docker ps`.  
Tous les containers doivent être démarrés et en "Healthy".  
On vérifie notre console Web airflow sur notre navigateur en appelant  http://localhost:8080/home.  

<img width="1649" alt="image" src="https://user-images.githubusercontent.com/45535819/223462244-38fb2062-d31a-48b4-a271-b3f1cb78fa36.png">

