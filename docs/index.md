## Etude d'un système planétaire
**Lehanneur Iona - Blasco Anaïs - Daumont Jean-Baptiste ARE DYNAMIC - 2021**


## Préambule

Un système planétaire tout comme celui dans lequel nous évoluons, se compose de corps célestes (astéroïdes, comètes…). Tous gravitent autour d’une étoile centrale. Ce projet de recherche documentaire a pour objectif de déterminer de quelle manière des facteurs tels que la taille d’un système complet, la masse et le diamètre de l’étoile centrale et le nombre de planètes influent sur les différentes trajectoires des corps célestes. Pour ce faire, nous utiliserons différentes métriques via le langage de programmation Python dans le but de comparer différents systèmes modélisés par nos soins. Nous en déduirons à partir de quelle masse, l’astre central est trop « léger » pour attirer les corps et inversement, à partir de quelle masse et taille se trouve-t-il trop « gros » pour que les planètes n’entrent pas en collision avec ce dernier.

 La taille et le nombre de planètes ont aussi un rôle essentiel à jouer, nos hypothèses soutiennent qu’un système trop grand comparé à la taille de l’étoile, empêchera les planètes lointaines d’engendrer une orbite stable, ainsi, les plus éloignées ne feront plus partie du système étudié. En somme, nous conclurons avec des courbes significatives, montrant le comportement des astres quant à la modification des paramètres cités précédemment, ce qui constituera la réponse à notre problématique.

## Objectifs


Dans ce notebook nous allons essayer de modéliser les trajectoires des planètes avec l'aide de formules mathématiques concrètes, afin que notre modèle mette en lumière les différences d'un système à l'autre. Nous allons essayer de comprendre les différentes façons d'implémenter un modèle significatif, et d'obtenir des résultats commentés qui permettront de comprendre dans quelles mesures un système va-t-il émerger, et sous quelle(s) condition(s) va-t-il pouvoir accueillir un nombre de planètes plus élevé que le notre.


### Etude du modèle en deux dimensions


**Objectifs : implémenter le modèle planétaire en python, le tester sur un exemple simple puis étudier l'impact que peuvent avoir les paramètres du modèle sur le système.**

Nous allons étudier l’impact des paramètres du modèle :

 • la taille du système                                                                                                                                                      
 • le nombre de planètes                                                                                                                                                         
 • le diamètre de l'étoile                                                                                                                                                       
 • la masse de l'étoile                                                                                                                                                         

**Pour quantifier l'impact de ces paramètres, en plus de l'observation visuelle de l'évolution de notre système, nous utiliserons les métriques suivantes :**
```
import numpy as np

import random

from matplotlib import pyplot as plt

# Paramètres du modèle Planétaire
sysize = 11     # Taille du système
plannum= 5     # Nombre de planètes (pour planet number à l'anglaise évidemment)
diameter=5    # Diamètre de l'étoile centrale en kms
mass=10^30 # Masse de l'étoile centrale
N=20      #nombre d'itérations
```

**Notre système est composé d'une matrice carrée de taille sysize.**

```
system=np.zeros((sysize,sysize),dtype=int)
print (system)
```

[[0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                         
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]                                                                                                                                                       
  [0 0 0 0 0 0 0 0 0 0 0]]                                                                                                                                                      

**La fonction print_system permet d'afficher le système.**                                                                                                                   
```
def print_system(system):
    result = ""
    for i in system:
        for j in i:
            result += " "+str(j)
        result += " "+'\n'
    print(result)
    return
print_system(system)
```

0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0    
 
**Notre étoile centrale est donc située au entre du système (ici matrice), elle est représentée grâce à ses coordonnées.**
```
coord_star = sysize//
```
**La fonction `create_etoileplace` l'étoile au centre du système selon ses coordonnées. Le coté du carré sensé représenter l'étoile fera le diamètre de l'étoile (exemple diamètre=3: carré=3x3 dans le système).**

```
def create_etoile(system):
    
    system[coord_star-diameter//2:coord_star+diameter//2+1, coord_star-diameter//2:coord_star+diameter//2+1] = 1
```
`create_etoile(system)`    
`print_system(system)`

0 0 0 0 0 0 0 0 0 0 0      
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 1 1 1 1 1 0 0 0      
 0 0 0 1 1 1 1 1 0 0 0     
 0 0 0 1 1 1 1 1 0 0 0     
 0 0 0 1 1 1 1 1 0 0 0     
 0 0 0 1 1 1 1 1 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0
 
 **Pour créer une planète, nous nous servons d'une classe planète.**
 ```
 class planetetype():

    def __init__(self):
        # self fait référence à l'objet lui-même
        self.sizeplan = random.randint(1,7)*0.01
        self.coordonnees = [random.randint(0,sysize-1),random.randint(0,sysize-1)]
        self.massplan = random.randint(10**20,10**28)
 ```
 **La fonction `rand_plan` permet de créer une planète de notre système en fonction de plannum, et de lui prodiguer une masse random dans un intervalle réliste (la planète ne peut être plus lourde que l'étoile centrale), ainsi qu'un diamètre plausible (même raisonnement).**
 
```
def randplan(plannum):
    L=[]
    while (plannum!=0):
        planete=planetetype()
        if system[planete.coordonnees[0],planete.coordonnees[1]]==0:
            plannum-=1
            L.append(planete)
    return (L)
    ```
`randplan(plannum)`
```
[<__main__.planetetype at 0x231761f44f0>,    
 <__main__.planetetype at 0x231761f4ca0>,    
 <__main__.planetetype at 0x231761f4520>,    
 <__main__.planetetype at 0x231761f4e20>,    
 <__main__.planetetype at 0x231761cdcd0>] 
 
 ```
def create_p(plannum):
    L=randplan(plannum)
    for i in range (plannum):
        p=L[i].coordonnees
        system[p[0],p[1]]=2
    return system 
 ```
  ```
  create_p(plannum)
   ```
 array([[0, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0],    
       [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],    
       [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],    
       [0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],    
       [0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],     
       [0, 0, 0, 1, 1, 1, 1, 1, 2, 0, 0],     
       [2, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0],     
       [0, 0, 0, 1, 1, 1, 1, 1, 0, 2, 0],     
       [0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0],     
       [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],     
       [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]])   
```
 print_system(system)
```
 0 0 0 0 0 0 0 2 0 0 0      
 0 0 0 0 0 0 0 0 0 0 0     
 0 0 0 0 0 0 0 0 0 0 0      
 0 0 0 1 1 1 1 1 0 0 0     
 0 0 0 1 1 1 1 1 0 0 0      
 0 0 0 1 1 1 1 1 2 0 0     
 2 0 0 1 1 1 1 1 0 0 0      
 0 0 0 1 1 1 1 1 0 2 0       
 0 0 0 0 2 0 0 0 0 0 0      
 0 0 0 0 0 0 0 0 0 0 0       
 0 0 0 0 0 0 0 0 0 0 0
 
 **Dans le but de modéliser les trajectoires de nos planètes, des fonctions de déplacement sont nécessaires. La fonction moveuppermet de déplacer la planète vers le haut du système en utilisant ses coordonnées.**
```
def moveup(p):
    system[p.coordonnees[0],p.coordonnees[1]]=0
    system[p.coordonnees[0],p.coordonnees[1]+1]=1
    p.coordonnees[0]+=1
```
**De même pour les autres directions avec les fonctions moveleft,moveright,movedown et movediagpour les déplacements en diagonale**
```
def moveleft(p):
    system[p.coordonnees[0],p.coordonnees[1]]=0
    system[p.coordonnees[0]-1,p.coordonnees[1]]=1
    p.coordonnees[0]-=1

```
```
def moveright(p):
    system[p.coordonnees[0],p.coordonnees[1]]=0
    system[p.coordonnees[0]+1,p.coordonnees[1]]=1
    p.coordonnees[0]+=1
```
```
def movedown(p):
    system[p.coordonnees[0],p.coordonnees[1]]=0
    system[p.coordonnees[0],p.coordonnees[1]-1]=1
    p.coordonnees[0]-=1
```
```
def movediag_up_left(p):
    moveleft(p)
    moveup(p)
```
```
def movediag_up_right(p):
    moveright(p)
    moveup(p)
```
```
def movediag_down_left(p):
    moveleft(p)
    movedown(p)
```
```
def movediag_down_right(p):
    moveright(p)
    movedown(p)
```
**Avec ces fonctions de mouvement, nous sommes maintenant capables de déterminer la trajectoire qu'aura une planète de notre système, on attribut une vitesse à chaque planète en fonction de sa masse et sa distance à l'étoile.Puis nous regarderons où se trouve la planète à T+1 (sachant que le système de base est représenté à T=0)**
```
def vitesse(p):
    G = 6.6742*10**-11
    d = sqrt((p.coordonnees[0]-coord_star)**2+(p.coordonnees[1]-coord_star)**2)
    vitesse = sqrt((G*p.massplan)/d)
```
**On obtient ici la vitesse à l'aide de la formule pour les vitesses orbitales où G est la constante de gravitation universelle , et d la distance entre les noyaux de la planète et l'étoile**

**A T=0, la planète est donc à sa position random initiale, et à T+1, la planète bougera de 1 en diagonale, la position dépendra de si la planète rentre, sors, ou perdure dans l'orbite de son étoile**

**La fontion `trajectoire` nous aide à tracer la trajetoire de la planète**
```
def trajectoire(p):
    for i in range (N):
        
```
**A T+N : on obtient un modèle stable, les tentatives montreront à partir de quel N, notre modèle ne bouge plus selon les métriques fixées au départ. N est fixé avant chaque essai, c'est le "nombre de tours" que notre fonction `final_system` fera.**

**La fonction `final_system` nous permet d'avoir une vision globale du système après N itérations**



 
 
