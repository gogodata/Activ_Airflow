# Activ_Airflow

Matériel utilisé : MAC M1 Pro 16g

MacOS (à date) : Ventura 13.2

# Prérequis

- Version MacOS à jour
- Homebrew (packages manager)
- Colima (runtimes docker)
- IDE (VS Code pour moi) + Git + XCode

# Démarrage de Colima

Pour démarrer Airflow, il faut déjà démarrer Colima et et lui fournir assez de ressources donc on lance la commande de démarrage de colima avec des paramètres cpu et ram :   
`colima start --cpu 4 --memory 8 --disk 50`. 

Puis on suit la procédure suivante : https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

Dans notre dossier, on aura ceci :  
<img width="256" alt="image" src="https://user-images.githubusercontent.com/45535819/223383697-b8e9319e-928d-4233-ac79-656802fb691a.png">


Une fois les composants Airflow démarrés avec la commande docker compose up.  
On vérifie nos containers airflow avec la commande `docker container ls` ou `docker ps`.  
Tous les containers airflow doivent être démarrés et en "Healthy".  

<img width="1649" alt="image" src="https://user-images.githubusercontent.com/45535819/223462244-38fb2062-d31a-48b4-a271-b3f1cb78fa36.png">. 

Grâce au fichier docker compose, on a une liste des composants Airflow et pas une version all-in-one standalone, ce qui est mieux quand on veut rentrer plus en détails dans nos composants.  

On vérifie notre console Web airflow sur notre navigateur en appelant  http://localhost:8080/home.  

Une fois cette étape validée, on passe sur la création de notre container python sur lequel on va charger notre fichier CSV dans une table (Postgresql) se trouvant dans un autre container.  

# Configuration de la base de données PostgreSQL

Pour configurer une connexion à notre base de données PostgreSQL dans Airflow, on se rend dans l'interface web Airflow, cliquer sur l'onglet "Admin" et sélectionner "Connections" puis cliquer sur "Create" pour créer une nouvelle connexion PostgreSQL en spécifiant les informations de connexion requises, telles que l'hôte, le port, le nom de la base de données, le nom d'utilisateur et le mot de passe.

# Création de la tâche Airflow

Ensuite, on va créer une tâche Airflow pour charger le fichier CSV dans la base de données PostgreSQL. On va utiliser le composant "PostgreSQLOperator" fourni par Airflow pour exécuter des requêtes SQL sur la base de données PostgreSQL. On peut utiliser la commande "COPY" pour charger le fichier CSV dans une table PostgreSQL. Le code Python pour créer une tâche de chargement de fichier CSV dans une table PostgreSQL est dans le fichier loading_task.py.  

# Planification de la tâche Airflow

On peut planifier l'exécution de la tâche de chargement de fichier CSV dans Airflow. On va dans l'interface utilisateur Airflow, cliquer sur l'onglet "DAGs" et sélectionner le DAG "load_csv_to_postgresql" puis cliquer sur le bouton "Trigger DAG" pour exécuter la tâche de chargement de fichier CSV.

