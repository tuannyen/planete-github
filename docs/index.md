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

`# Paramètres du modèle Planétaire \n
sysize = 11     # Taille du système
plannum= 5     # Nombre de planètes (pour planet number à l'anglaise évidemment)
diameter=5    # Diamètre de l'étoile centrale en kms
mass=10^30 # Masse de l'étoile centrale
N=20      #nombre d'itérations`






You can use the [editor on GitHub](https://github.com/tuannyen/planete-github/edit/gh-pages/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdozefzefzefzfzfzefzfesy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tuannyen/planete-github/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
