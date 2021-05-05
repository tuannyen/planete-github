# Etude d'un système planétaire
**Lehanneur Iona - Blasco Anaïs - Daumont Jean-Baptiste ARE DYNAMIC - 2021**


### Préambule

Un système planétaire tout comme celui dans lequel nous évoluons, se compose de corps célestes (astéroïdes, comètes…). Tous gravitent autour d’une étoile centrale. Ce projet de recherche documentaire a pour objectif de déterminer de quelle manière des facteurs tels que la taille d’un système complet, la masse et le diamètre de l’étoile centrale et le nombre de planètes influent sur les différentes trajectoires des corps célestes. Pour ce faire, nous utiliserons différentes métriques via le langage de programmation Python dans le but de comparer différents systèmes modélisés par nos soins. Nous en déduirons à partir de quelle masse, l’astre central est trop « léger » pour attirer les corps et inversement, à partir de quelle masse et taille se trouve-t-il trop « gros » pour que les planètes n’entrent pas en collision avec ce dernier.

 La taille et le nombre de planètes ont aussi un rôle essentiel à jouer, nos hypothèses soutiennent qu’un système trop grand comparé à la taille de l’étoile, empêchera les planètes lointaines d’engendrer une orbite stable, ainsi, les plus éloignées ne feront plus partie du système étudié. En somme, nous conclurons avec des courbes significatives, montrant le comportement des astres quant à la modification des paramètres cités précédemment, ce qui constituera la réponse à notre problématique.
 
### Résumé

L'objectif du projet est de modéliser la création d'un système planétaire avec son astre central et les planètes qui gravitent autour. Pour comprendre comment fonctionne un système planétaire, l'élément le plus important est la trajectoire des planètes gravitant dans le système. 
Pour construire notre système, on a suivi les étapes suivantes:
 - création de la matrice
 - création de l'astre central dans la matrice
 - création des planètes
 - mouvoir les planètes 
 - appliquer les fonctions de mouvement en fonction de la formule pour la trajectoire des planètes

### In English please

### Description synthétique du projet

#### Problématique : De quelle manière des facteurs tels que la taille d’un système complet, la masse et le diamètre de l’étoile centrale et le nombre de planètes influent sur les différentes trajectoires des corps célestes ?

###### Hypothèse principale :
Ces facteurs influent directement sur la mise en orbite et donc la trajectoire des planètes.

###### Objectifs :
Modèliser la trajectoire des planètes, déterminer si la planètes peut être mise en orbite.

###### Critère(s) d'évaluation :

### Présentation des résultats
Nous avons décidé de modéliser le système grâce à une matrice, voici un exemple ci-dessous.

[[0, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0],    
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],    
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],    
[0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],    
[0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],    
[0, 0, 0, 1, 1, 1, 1, 1, 2, 0, 0],    
[2, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],    
[0, 0, 0, 1, 1, 1, 1, 1, 0, 2, 0],    
[0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0],    
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],    
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]]

Les "1" représentent l'astre central, les "2" les planètes.

Ensuite pour ce qui est de la trajectoire voici un autre exemple.


Le point fort de notre modélisation est que de nombreux facteurs peuvent être changé pour voir l'impact sur les trajectoires, elle est donc polyvalente.
Un point faible peut-être l'aproximation des trajectoires du au fait que nous modélisons par une matrice.

## Carnet de bord

#### Semaine 1    
Le groupe se découvre, un brainstorming a lieu pour mettre en commun des idées quant au sujet du projet. Modélisation d'une population d'abeille dans une ruche, vitesse d'apprentissage, ce sera finalement la modélisation des planètes qui sera retenue.

#### Semaine 2
Mise en forme de l'organisation du projet, que doit-on créer, faire varier, dans quel ordre doit-on organiser les étapes. Il est retenu qu'on doit créer le système, l'astre central, les planètes.

#### Semaine 3
Début des étapes, les différents membres du groupe cherchent sur internet des pistes. L'idée de matrice pour modéliser vient alors. On essaie tout d'abord de créer une matrice vide, puis une matrice comportant des "0".

#### Semaine 4
Après avoir crée la matrice représentant notre système, nous avons essayé de créer l'astre central, représenté par des "1". Nous avons eu l'idée de faire varier le nombre de "1" au sein de notre matrice pour pouvoir faire varier la taille de l'astre central. 

#### Semaine 5
Création des planètes gravitant autour de l'astre central, représentées par des "2" grâce à une fonction random. On décide de faire choisir à l'utilisateur le nombre de planète qu'il souhaite, si une planète n'est pas dans la matrice, la boucle se répete.

#### Semaine 6
On veut maintenant pouvoir faire bouger les planètes dans notre matrice, on crée donc des fonctions de mouvement (par exemple move_up) qui nous permettent de faire varier la position des planètes si besoin.

#### Semaine 7
On ajoute la fonction nous permettant de calculer la trajectoire d'une planète. On appliquera nos fonctions de mouvement en fonction des coordonnées données en fonction du temps, on crée le site web pour notre projet et on se prépare pour la soutenance orale.

## Bibliographie
1. FUTURA. Futura, Explorer le monde. Futura [en ligne]. [Consulté le 5 mai 2021]. Disponible à l’adresse : https://www.futura-sciences.comMédia de décryptage, Futura vous emmène à la rencontre des découvertes et innovations qui changent le monde. Autour de 5 rubriques (Sciences, Santé, Tech, Maison et Planète), nos journalistes vous proposent un contenu exclusif : actualités, vidéos, dossiers, photos...
2. QUELOZ, Didier et CARIEL, Francisca. Il y a trop d’étoiles, de planètes et de galaxies pour que nous soyons seuls. Courrier international. 11 mars 2021. Vol. 1584, n° 1584, pp. 49,50,51. 
3. BLAY, Michel. Les Principia de Newton [en ligne]. Dunod, 2017. [Consulté le 29 mars 2021]. Disponible à l’adresse : https://halldulivre.com/livre/9782100769162-les-principia-de-newton-michel-blay/
4. DEPARIS, Vincent. Pourquoi les corps tombent-ils ? Une histoire de la gravité d’Aristote à Einstein (2/3). — Planet-Terre. [en ligne]. 2011. [Consulté le 29 mars 2021]. Disponible à l’adresse : https://planet-terre.ens-lyon.fr/article/histoire-gravite-2-Hooke-Newton.xml
5. ANDRADE, Jules. Sur le mouvement d’un corps soumis à l’attraction newtonienne de deux corps fixes et sur l’extension d’une propriété des mouvements keplériens. 2009. Paris ; 1806-1896, France : Bibliothèque universitaire Pierre et Marie Curie (BUPMC).







 
 
