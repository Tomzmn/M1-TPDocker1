# TP 1 - Docker

[📖 | Voir la documentation sur cette plateforme.](https://stack.tomz.fr/books/conteneurisation/page/tp-1-docker)

#### 1. Installer Docker et Docker-Compose sur Ubuntu

*(https://docs.docker.com/get-docker/ &amp; [https://docs.docker.com/compose/install/)](https://docs.docker.com/compose/install/))*

#### 2. Quelques commandes à tester

##### Hello-world d’exemple avec Docker

- **`docker run hello-world`**

![image.png](https://stack.tomz.fr/uploads/images/gallery/2022-12/scaled-1680-/RFh9MEth52tqemdf-image.png)

<p class="callout info">`docker run hello-world` est une commande utilisée pour exécuter l'image Docker "hello-world". Cette image est une image très simple qui affiche simplement un message "Hello, World!" lorsqu'elle est exécutée. L'objectif de cette image est d'aider les utilisateurs à vérifier que leur installation de Docker fonctionne correctement. Lorsque vous exécutez cette commande, Docker télécharge l'image "hello-world" à partir du registre Docker Hub, puis l'exécute en créant un conteneur à partir de cette image. Le conteneur affiche ensuite le message "Hello, World!", indiquant que l'exécution s'est déroulée avec succès.</p>

#### Création d’un conteneur et utilisation d’un bash en interactif exit ou Ctrl+D- Pour sortir du conteneur

- **`docker run -it ubuntu bash`**

[![image.png](https://stack.tomz.fr/uploads/images/gallery/2022-12/scaled-1680-/XchOfOcRUUACfC69-image.png)](https://stack.tomz.fr/uploads/images/gallery/2022-12/XchOfOcRUUACfC69-image.png)

<p class="callout info">Le `docker run -it ubuntu bash` commande est utilisée pour exécuter une image Docker Ubuntu en mode interactif en utilisant un shell Bash. Cela signifie que vous pouvez exécuter des commandes dans un environnement Ubuntu à l'intérieur d'un conteneur Docker et interagir avec celui-ci en temps réel.</p>

##### Afficher les images Docker disponibles en local

- *`docker images`*

[![image.png](https://stack.tomz.fr/uploads/images/gallery/2022-12/scaled-1680-/ehBiPqJsClOuBHPS-image.png)](https://stack.tomz.fr/uploads/images/gallery/2022-12/ehBiPqJsClOuBHPS-image.png)

<p class="callout info"> *La commande `docker images` est utilisée pour afficher une liste des images Docker disponibles localement sur votre ordinateur. Cela peut être utile pour voir les images que vous avez téléchargées à partir du dépôt Docker Hub ou que vous avez créées vous-même. La commande affiche des informations telles que le nom de l'image, sa taille et sa référence de l'image.*</p>

##### Affiche tous les conteneurs *(en exécution ou pas, grâce à l’option -a)*

- *`docker ps -a`*

[![image.png](https://stack.tomz.fr/uploads/images/gallery/2022-12/scaled-1680-/1TY6RKtkFRt00eqf-image.png)](https://stack.tomz.fr/uploads/images/gallery/2022-12/1TY6RKtkFRt00eqf-image.png)

<p class="callout info">La commande `docker ps -a` est utilisée pour afficher la liste de tous les conteneurs Docker en cours d'exécution et arrêtés sur votre ordinateur. Cela peut être utile pour voir les conteneurs que vous avez créés et pour gérer ces conteneurs. La commande affiche des informations telles que l'ID du conteneur, son nom, son image de base et son statut.</p>

<p class="callout info">En utilisant l'option `-a`, vous pouvez voir tous les conteneurs, y compris ceux qui sont arrêtés. Si vous exécutez simplement `docker ps`, vous verrez uniquement les conteneurs en cours d'exécution.</p>

##### Démarre un serveur web disponible sur votre navigateur à l’adresse localhost:80

- *`docker run -p 80:80 nginx`* et *`docker run -p -d 80:80 nginx`*

[![image.png](https://stack.tomz.fr/uploads/images/gallery/2022-12/scaled-1680-/dwTr2tz4jyD9Lysl-image.png)](https://stack.tomz.fr/uploads/images/gallery/2022-12/dwTr2tz4jyD9Lysl-image.png)

<p class="callout info">La `docker run -p 80:80 nginx` commande exécute une image Docker nginx en exposant le port 80 du conteneur sur le port 80 de l'hôte. L'application Web nginx dans le conteneur sera donc accessible sur le port 80 de l'hôte, et les requêtes entrantes sur ce port seront acheminées vers le conteneur.</p>

<p class="callout info">La `docker run -p -d 80:80 nginx` commande fonctionne de la même manière, mais elle utilise l'option `-d` pour exécuter le conteneur en arrière-plan, en mode détaché. Cela signifie que le conteneur continuera à s'exécuter en arrière-plan après l'exécution de la commande, et vous pourrez continuer à utiliser votre terminal pour exécuter d'autres commandes.</p>

<p class="callout info">Les deux commandes exécutent une image Docker nginx et exposent le port 80 du conteneur sur le port 80 de l'hôte, mais la seconde commande exécute le conteneur en arrière-plan en mode détaché.</p>

#### 3. Ressources supplémentaires pour découvrir Docker

- [https://docs.docker.com/get-started/02\_our\_app/](https://docs.docker.com/get-started/02_our_app/)
- Et les autres articles du “Getting Started” Docker

---

#### 4. Début du TP

Initialiser un **nouveau repository git** qui vous permettra de sauvegarder les fichiers créés pendant le TP. Vous enverrez un zip du repository à la fin du TP avec vos réponses aux questions / exécutions et résultats sur la console dans des **fichiers texte** (Markdown par exemple) par e-mail.   
<span style="text-decoration: underline;">Utilisez git progressivement ! (Ne pas faire qu’un seul commit à la fin)  
</span>

<p class="callout info">Pour initialiser un nouveau repository Git qui vous permettra de sauvegarder les fichiers créés pendant le TP, vous pouvez utiliser la commande `git init` dans le répertoire où vous souhaitez créer le repository. Cela créera un nouveau repository Git local sur votre ordinateur.</p>

<p class="callout info">Pour ajouter vos fichiers au repository, vous pouvez utiliser les commandes `git add` et `git commit`, qui permettent respectivement d'ajouter des fichiers au répertoire Git et de les sauvegarder en les associant à un message de commit.</p>

<p class="callout info">Une fois que vous avez créé et configuré votre repository Git local, vous pouvez le compresser en un fichier zip et l'envoyer par e-mail avec vos réponses aux questions et vos résultats d'exécution.</p>

#### 5. Exécuter un **serveur web** (apache, nginx, …) **dans un conteneur docker**

- ##### Récupérer l’image sur le Docker Hub

<p class="callout info">Pour récupérer l'image Docker nginx sur le Docker Hub, vous pouvez utiliser la commande `docker pull nginx`.   
Cela téléchargera l'image nginx depuis le Docker Hub et la stockera localement sur votre ordinateur, de sorte que vous pouvez la utiliser pour exécuter des conteneurs nginx.</p>

- ##### Vérifier que cette image est présente en local

<p class="callout info">La commande `docker images` affichera une liste des images Docker disponibles sur votre ordinateur, et vous devriez voir l'image nginx dans la liste. Vous pouvez maintenant utiliser cette image pour exécuter des conteneurs nginx.</p>

- ##### Créer un fichier index.html simple

<p class="callout info">Pour créer un fichier HTML simple, vous pouvez ouvrir un éditeur de texte et ajouter les balises HTML suivantes :</p>

```html

<html>
<head>
  <title>Mon premier fichier HTML</title>
</head>
<body>
  <h1>Bienvenue sur mon site web !</h1>
  <p>Ceci est mon premier fichier HTML.</p>
</body>
</html>

```

<p class="callout info">Enregistrez ce fichier avec un nom, par exemple `index.html`. Vous pouvez maintenant ouvrir ce fichier dans un navigateur web pour voir comment il sera affiché.</p>

<p class="callout info">Notez que les fichiers HTML doivent avoir l'extension `.html` ou `.htm` pour être reconnus comme des fichiers HTML par les navigateurs web. Vous pouvez utiliser n'importe quel nom pour votre fichier, mais veillez à utiliser l'une de ces extensions.</p>

- ##### Démarrer un conteneur et servir la page html créée précédemment à l’aide d’un volume (option -v de docker run)

<p class="callout info">Pour démarrer un conteneur et servir une page HTML à l'aide d'un volume, vous pouvez utiliser la commande `docker run` en spécifiant l'option `-v` pour monter un volume, ainsi que l'option `-p` pour exposer un port sur l'hôte.</p>

<p class="callout info">Voici un exemple de commande `docker run` qui démarre un conteneur nginx en montant un volume contenant un fichier index.html, et en exposant le port 80 du conteneur sur le port 80 de l'hôte :</p>

```bash
# Démarrer un conteneur nginx en montant un volume contenant un fichier index.html
# et en exposant le port 80 du conteneur sur le port 80 de l'hôte
docker run -d -p 80:80 -v chemin/vers/mon/dossier:/usr/share/nginx/html nginx
```

<p class="callout info">Remplacez `chemin/vers/mon/dossier` par le chemin d'accès complet vers le dossier contenant votre fichier index.html. Cela permettra au conteneur d'accéder au fichier index.html à partir du volume monté.</p>

<p class="callout info">Une fois que le conteneur est en cours d'exécution, vous pouvez accéder à la page HTML en ouvrant un navigateur Web et en accédant à l'adresse `http://localhost`. Vous devriez voir la page HTML que vous avez créée précédemment.</p>

- ##### Supprimer le conteneur précédent et arriver au même résultat que précédemment **à l’aide de la commande** `docker cp`

<p class="callout info">Pour supprimer le conteneur précédent et arriver au même résultat que précédemment à l'aide de la commande `docker cp`, vous pouvez utiliser les étapes suivantes :</p>

<p class="callout info">1. Supprimer le conteneur précédent en utilisant la commande `docker rm` en spécifiant l'ID du conteneur. Vous pouvez obtenir l'ID du conteneur en utilisant la commande `docker ps -a`. Par exemple :</p>

```bash
# Afficher la liste des conteneurs, y compris ceux qui sont arrêtés
docker ps -a

# Supprimer le conteneur en utilisant son ID
docker rm mon_conteneur_id
```

<p class="callout info">Remplacez `mon_conteneur_id` par l'ID réel de votre conteneur nginx. Cela supprimera le conteneur et libérera les ressources utilisées par celui-ci.  
2. Démarrer un nouveau conteneur nginx en utilisant la commande `docker run` sans l'option `-v`. Par exemple :</p>

```bash
# Démarrer un conteneur nginx en exposant le port 80 du conteneur sur le port 80 de l'hôte
docker run -d -p 80:80 nginx
```

<p class="callout info">Cela démarrera un conteneur nginx en exposant le port 80 du conteneur sur le port 80 de l'hôte.  
3. Copier le fichier index.html dans le conteneur en utilisant la commande `docker cp`. Par exemple :</p>

```bash
# Copier le fichier index.html dans le conteneur nginx
docker cp chemin/vers/mon/fichier/index.html mon_conteneur_id:/usr/share/nginx/html/index.html
```

<p class="callout info">Remplacez `chemin/vers/mon/fichier/index.html` par le chemin d'accès complet vers votre fichier index.html, et remplacez `mon_conteneur_id` par l'ID réel de votre conteneur nginx. Cela copiera le fichier index.html dans le conteneur nginx, où il sera accessible par l'application Web nginx.</p>

#### 6. **Builder une image**

- ##### A l’aide d’un Dockerfile, créer une image (commande docker build)

<p class="callout info">Pour créer une image avec un fichier HTML à l'intérieur, vous pouvez utiliser un fichier Dockerfile comme celui-ci :</p>

```yaml
FROM nginx:latest

COPY mon_fichier.html /usr/share/nginx/html
```

<p class="callout info">Ce fichier Dockerfile utilise l'image `nginx:latest` comme base, puis copie le fichier HTML (`mon_fichier.html` dans l'exemple ci-dessus) dans le répertoire `/usr/share/nginx/html` de l'image, qui est le répertoire par défaut où Nginx sert les fichiers statiques.  
Pour créer l'image, utilisez la commande `docker build` comme indiqué dans la réponse précédente :</p>

```bash
docker build -t <nom_de_l'image>
```

- ##### Exécuter cette nouvelle image de manière à servir la page html (commande docker run)

<p class="callout info">Une fois que l'image a été créée, vous pouvez l'exécuter en utilisant la commande `docker run` pour servir le fichier HTML </p>

```bash
docker run -p <port>:<port> -d <nom_de_l'image>
```

<p class="callout info">Vous pouvez ensuite accéder au fichier HTML en accédant à l'URL suivante dans votre navigateur web : `http://localhost:<port>/mon_fichier.html`, où `<port>` est le port spécifié dans la commande `docker run`.</p>

- ##### Quelles différences observez-vous entre les procédures 5. et 6. ? Avantages et inconvénients de l’une et de l’autre méthode ? (Mettre en relation ce qui est observé avec ce qui a été présenté pendant le cours)

<p class="callout info">Un dockerfile est un fichier de configuration utilisé pour automatiser la construction d'une image Docker. Il contient des instructions qui spécifient les étapes nécessaires pour créer une image Docker, telles que les dépendances à installer, les fichiers à copier, les ports à exposer, etc.</p>

<p class="callout info">Docker cp, en revanche, est une commande utilisée pour copier des fichiers ou des répertoires entre un conteneur Docker et l'hôte ou un autre conteneur. Cette commande permet de transférer des fichiers entre le système de fichiers du conteneur et celui de l'hôte, ou entre deux conteneurs.</p>

<p class="callout info">En résumé, un dockerfile est un fichier de configuration utilisé pour créer une image Docker, tandis que docker cp est une commande utilisée pour copier des fichiers entre un conteneur et l'hôte ou un autre conteneur.</p>

#### 7. Utiliser une base de données dans un conteneur docker

- ##### Récupérer les images mysql:5.7 et phpmyadmin/phpmyadmin depuis le Docker Hub

<p class="callout info">Pour récupérer les images Docker mysql:5.7 et phpmyadmin/phpmyadmin depuis le Docker Hub, vous pouvez utiliser la commande `docker pull`. La syntaxe générale de cette commande est la suivante :</p>

```bash
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

<p class="callout info">Pour récupérer l'image mysql:5.7, vous pouvez utiliser la commande suivante :</p>

```bash
docker pull mysql:5.7
```

<p class="callout info">Pour récupérer l'image phpmyadmin/phpmyadmin, vous pouvez utiliser la commande suivante :</p>

```bash
docker pull phpmyadmin/phpmyadmin
```

<p class="callout info">Ces commandes téléchargeront les images depuis le Docker Hub et les enregistreront sur votre système. Vous pourrez ensuite utiliser ces images pour créer des conteneurs et exécuter les applications correspondantes.</p>

<div class="bg-black mb-4 rounded-md" id="bkmrk-ex%C3%A9cuter-deux-conten"><div class="p-4"><div class="p-4">- ##### Exécuter deux conteneurs à partir des images et ajouter une table ainsi que quelques enregistrements dans la base de données à l’aide de phpmyadmin

</div></div></div><p class="callout info">Pour exécuter un conteneur à partir de l'image mysql:5.7, vous pouvez utiliser la commande suivante :</p>

```bash
docker run --name mysql -e MYSQL_ROOT_PASSWORD=root -d mysql:5.7
```

<p class="callout info">Pour exécuter un conteneur à partir de l'image phpmyadmin/phpmyadmin, vous pouvez utiliser la commande suivante :</p>

```bash
docker run --name phpmyadmin --link mysql:db -p 8080:80 -d phpmyadmin/phpmyadmin
```

<p class="callout info">Ces commandes créeront des conteneurs à partir des images spécifiées et les exécuteront en utilisant les options spécifiées. Vous pouvez utiliser l'option `-e` pour spécifier des variables d'environnement pour le conteneur, l'option `--name` pour donner un nom au conteneur, l'option `--link` pour créer un lien entre deux conteneurs, l'option `-p` pour publier les ports du conteneur sur l'hôte, et l'option `-d` pour exécuter le conteneur en arrière-plan.</p>

<p class="callout info">Pour ajouter une table et des enregistrements dans la base de données à l'aide de phpmyadmin, vous devez d'abord vous connecter à l'interface de phpmyadmin en vous rendant à l'adresse [http://localhost:8080](http://localhost:8080/) dans votre navigateur web. Vous devrez alors entrer les informations de connexion pour accéder à la base de données mysql.</p>

<p class="callout info">Une fois connecté, vous pouvez utiliser l'interface de phpmyadmin pour créer une nouvelle base de données et une nouvelle table, puis ajouter des enregistrements dans cette table. </p>

#### 8. Faire la même chose que précédemment en utilisant un fichier docker-compose.yml

<p class="callout info">Pour exécuter deux conteneurs à partir des images Docker mysql:5.7 et phpmyadmin/phpmyadmin en utilisant un fichier docker-compose.yml, vous pouvez utiliser la commande `docker-compose up`. La syntaxe générale de cette commande est la suivante :</p>

```bash
docker-compose up [OPTIONS] [SERVICE...]
```

<p class="callout info">Avant de pouvoir exécuter cette commande, vous devez d'abord créer un fichier docker-compose.yml contenant les informations nécessaires pour créer et exécuter les conteneurs. Voici un exemple de fichier docker-compose.yml qui peut être utilisé dans ce cas :</p>

```yaml
version: '3'
services:
  mysql:
    image: mysql:5.7
    environment:
      - MYSQL_ROOT_PASSWORD=root
  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    links:
      - mysql:db
    ports:
      - 8080:80
```

- ##### Qu’apporte le fichier docker-compose par rapport aux commandes docker run ? Pourquoi est-il intéressant ? *(cf. ce qui a été présenté pendant le cours)*

<p class="callout info">Le fichier docker-compose.yml permet de définir et d'exécuter plusieurs conteneurs en utilisant une configuration unique. Cela facilite la gestion des conteneurs et leur exécution en production, car vous pouvez définir toutes les options de configuration dans un seul fichier, puis utiliser une seule commande pour exécuter tous les conteneurs.</p>

<p class="callout info">Cela peut être particulièrement utile lorsque vous avez besoin d'exécuter une application complexe composée de plusieurs conteneurs. Au lieu d'avoir à exécuter plusieurs commandes docker run pour chaque conteneur, vous pouvez définir tous les conteneurs dans un fichier docker-compose.yml et les exécuter en utilisant la commande docker-compose up.</p>

<p class="callout info">Le fichier docker-compose.yml permet également de faciliter la gestion des dépendances entre les conteneurs. Vous pouvez utiliser l'option `links` pour créer des liens entre les conteneurs, de sorte que vous puissiez accéder à un conteneur depuis un autre conteneur en utilisant son nom. Cela peut être utile lorsque vous avez besoin d'exécuter une application qui utilise plusieurs bases de données ou services différents.</p>

<p class="callout info">En résumé, le fichier docker-compose.yml permet de gérer et d'exécuter plusieurs conteneurs de manière centralisée et facilite la gestion des dépendances entre les conteneurs. Cela peut être particulièrement utile lorsque vous avez besoin d'exécuter une application complexe composée de plusieurs conteneurs.</p>

- ##### Quel moyen permet de configurer (premier utilisateur, première base de données, mot de passe root, …) facilement le conteneur mysql au lancement?

<p class="callout info">Pour configurer facilement le conteneur mysql au lancement, vous pouvez utiliser les variables d'environnement. Vous pouvez spécifier les variables d'environnement à utiliser lors du lancement du conteneur en utilisant l'option `-e` avec la commande docker run.</p>

<p class="callout info">Par exemple, pour configurer le mot de passe root de mysql lors du lancement du conteneur, vous pouvez utiliser la commande suivante :</p>

```bash
docker run -e MYSQL_ROOT_PASSWORD=root -d mysql:5.7
```

<p class="callout info">Dans cet exemple, l'option `-e` spécifie la variable d'environnement MYSQL\_ROOT\_PASSWORD avec la valeur "root". Cela configurera le mot de passe root de mysql lors du lancement du conteneur.</p>

<p class="callout info">Vous pouvez également utiliser cette technique avec docker-compose. Dans ce cas, vous pouvez spécifier les variables d'environnement dans le fichier docker-compose.yml en utilisant l'option `environment`. Par exemple, voici comment spécifier la variable d'environnement MYSQL\_ROOT\_PASSWORD dans un fichier docker-compose.yml :</p>

```
version: '3'
services:
  mysql:
    image: mysql:5.7
    environment:
      - MYSQL_ROOT_PASSWORD=root
	  - MYSQL_DATABASE=mydb
      - MYSQL_USER=myuser
      - MYSQL_PASSWORD=mypassword
```

#### 9. Observation de l’isolation réseau entre 3 conteneurs

- ##### A l’aide de docker-compose et de l’image praqma/network-multitool disponible sur le Docker Hub créer 3 services (web, app et db) et 2 réseaux (frontend et backend). Les services web et db ne devront pas pouvoir effectuer de ping de l’un vers l’autre.

<p class="callout info">Pour créer 3 services (web, app et db) et 2 réseaux (frontend et backend) en utilisant docker-compose et l'image praqma/network-multitool disponible sur le Docker Hub, vous pouvez utiliser le fichier `docker-compose.yml` suivant :</p>

```yaml
version: '3'
services:
  web:
    image: praqma/network-multitool
    networks:
      - frontend
  app:
    image: praqma/network-multitool
    networks:
      - frontend
      - backend
  db:
    image: praqma/network-multitool
    networks:
      - backend
networks:
  frontend:
  backend:
```

<p class="callout info">Pour démarrer les services et les réseaux, utilisez la commande `docker-compose up` à partir du répertoire où le fichier `docker-compose.yml` est situé.</p>

<p class="callout info">Les services `web` et `db` seront alors connectés aux réseaux `frontend` et `backend` respectivement, mais ne pourront pas effectuer de ping l'un vers l'autre car ils sont connectés à des réseaux différents. Vous pouvez vérifier cela en exécutant la commande `docker network inspect` pour obtenir des informations sur les réseaux et les services connectés à chacun d'eux.</p>

- ##### Quelles lignes du résultat de la commande docker inspect justifient ce comportement?

<p class="callout info">Pour vérifier que les services `web` et `db` ne peuvent pas effectuer de ping l'un vers l'autre, vous pouvez utiliser la commande `docker network inspect` pour afficher des informations sur les réseaux et les services connectés à chacun d'eux. Le résultat de cette commande inclura des informations sur les adresses IP attribuées aux services et aux réseaux, ainsi que sur les réseaux auxquels chaque service est connecté.  
Par exemple, si vous exécutez la commande suivante :</p>

```bash
docker network inspect frontend
```

<p class="callout info">Le résultat inclura des informations sur les services `web` et `app` connectés au réseau `frontend`, ainsi que sur leurs adresses IP respectives. Si vous exécutez la commande suivante :</p>

```bash
docker network inspect backend
```

<p class="callout info">Le résultat inclura des informations sur le service `db` connecté au réseau `backend`, ainsi que sur son adresse IP.</p>

<p class="callout info">Les lignes du résultat de ces commandes qui justifient le fait que les services `web` et `db` ne peuvent pas effectuer de ping l'un vers l'autre sont les lignes qui indiquent que les services sont connectés à des réseaux différents (`frontend` et `backend` respectivement) et ont donc des adresses IP différentes.</p>

- ##### Dans quelle situation réelles (avec quelles images) pourrait-on avoir cette configuration réseau ? Dans quel but ?

<p class="callout info">Il est possible de créer une configuration réseau similaire en utilisant des images Docker différentes pour les services `web`, `app` et `db`. Cette configuration pourrait être utilisée dans un environnement d'application où l'application est divisée en différents services qui communiquent entre eux via des réseaux.</p>

<p class="callout info">Par exemple, si l'application comporte une interface utilisateur (`web`), une couche d'application (`app`) qui gère les logiques métier et les communications avec la base de données (`db`), on pourrait utiliser cette configuration réseau pour séparer l'interface utilisateur et la couche d'application de la base de données. Cela permet de sécuriser les communications entre ces différents services en limitant les interactions entre eux uniquement aux échanges nécessaires pour l'application.</p>

---

#### **Le compte rendu du TP doit être déposé sur moodle par chacun des membres du groupe au format GIT le 15 décembre 2022 au plus tard.**

</body></html>
