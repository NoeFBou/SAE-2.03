# SAE-2.03 Equipe 4

**dockerfile** pour lancer un serveur d'hébergement de vidéo basé sur l'image ```debian``` et utilisant ```nginx```


## Instructions pour lancer l'application

- Vérifiez si docker est installé :
```shell
docker --version
```

- Cloner le référentiel :
 ```shell
git clone git@github.com:NoeFBou/SAE-2.03.git
```

- Aller au référentiel :
```shell
cd SAE-2.03
```

- Construisez l'image décrite dans dockerfile avec docker build : 
```shell
docker build -t <choisir-un-nom-pour-l'image> .
```

- Lancer le serveur web :
```shell
docker run -d -p 54351:80 <nom-de-l'image-choisie>
```

- Vérifier que l'application est en cours d'exécution. Pour ce faire, ouvrez un navigateur et tapez ```localhost:8080```

- Vérifier que le conteneur associé est actif :
```shell
docker ps
```

- La sortie de ```docker ps``` doit être similaire à :
```shell
CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS          PORTS                                               NAMES
bd2cbf1456f6   sae203_eq4   "nginx -g 'daemon of…"   34 seconds ago   Up 2 seconds    8096/tcp, 0.0.0.0:54351->80/tcp, :::54351->80/tcp   sae203_eq4
```

- Finalement, arrêtez le conteneur avec la commande suivante (les dernières chiffres sont le code de hachage affiché par docker ps):
```shell
docker stop bd2cbf1456f6
```

- Encore, si on souhaite supprimer le conteneur, on peut taper :
```shell
docker rm bd2cbf1456f6
```

**NOTE :** Au lieu du code de hachage, on peut toujours taper le nom du conteneur. Dans le cas d'exemple ce nom est ```sae203_eq4```

