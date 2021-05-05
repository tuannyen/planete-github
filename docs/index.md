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

`import numpy as np`                                                                                                                                                             
`import random`                                                                                                                                                                 
`from matplotlib import pyplot as plt`

`# Paramètres du modèle Planétaire`                                                                                                                                             
`sysize = 11     # Taille du système`                                                                                                                                           
`plannum= 5     # Nombre de planètes (pour planet number à l'anglaise évidemment)`                                                                                               
`diameter=5    # Diamètre de l'étoile centrale en kms`                                                                                                                           
`mass=10^30 # Masse de l'étoile centrale`                                                                                                                                       
`N=20      #nombre d'itérations`

**Notre système est composé d'une matrice carrée de taille sysize.**

`system=np.zeros((sysize,sysize),dtype=int)`                                                                                                                                     
`print (system)`

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
`def print_system(system):`          
`result = ""`                                                                                                                                                      
`for i in system:`                                                                                                                                                      
`for j in i:`                                                                                                                                                      
`result += " "+str(j)`                                                                                                                                               
`result += " "+'\n'`                                                                                                                                                    
`print(result)`                                                                                                                                                      
`return`                                                                                                                                                          
`print_system(system)`
