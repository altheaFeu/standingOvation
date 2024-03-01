# Standing Ovation 

[![Julia Version](https://img.shields.io/badge/Julia-dev-blue.svg)](https://julialang.org/)
[![Docteur Watson](https://img.shields.io/badge/Docteur%20Watson-Live-green)](https://lien_vers_votre_page)
[![Agents.jl](https://img.shields.io/badge/Agents.jl-v5.4.0-blue.svg)](https://github.com/JuliaDynamics/Agents.jl)
[![Pluto.jl](https://img.shields.io/badge/Pluto.jl-v0.15.0-blue.svg)](https://github.com/fonsp/Pluto.jl)
[![Folium](https://img.shields.io/badge/Folium-v0.13.0-green.svg)](https://github.com/python-visualization/folium)
[![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen.svg)](LICENSE.md)
[![Build By](https://img.shields.io/badge/Build%20By-Althéa_Feuillet-orange.svg)](https://yourportfolio.com)

<h1 align="center">
  <strong>Un modèle agent produit avec <a href="https://julialang.org/" style="color:#8e7cc3;">Julia</a> et <a href="https://juliadynamics.github.io/DrWatson.jl/stable/" style="color:#8e7cc3;">DrWatson</a>
  </strong>
</h1>

## Introduction

Ce projet propose un modèle agent développé en utilisant le langage de programmation [Julia](https://julialang.org/) et le framework [DrWatson](https://juliadynamics.github.io/DrWatson.jl/stable/).

Le modèle est conçu pour simuler un phénomène de "Standing Ovation" en utilisant le framework [Agents.jl](https://juliadynamics.github.io/Agents.jl/stable/).

Pour comprendre le concept de "Standing Ovation", vous pouvez consulter l'article de H. Miller et Scott E. [ici](https://onlinelibrary.wiley.com/doi/10.1002/cplx.20033).

Le modèle offre une flexibilité considérable avec la possibilité de modifier plusieurs paramètres, tels que :

- L'espace X et Y où se déplace les agents ;
- Le nombre d'étapes du modèle ;
- Le nombre minimum d'agent qui doit être dans son champs de vision pour qu'il choisisse d'applaudir ;
- Le champs de vision en °C de l'agent. ;
- La probabilité que l'agent se retourne (son champs de vision est alors de 360°) ;
- Si les agents se lèvent de façon synchrone ou asynchrone ;
- La probabilité que l'agent applaudisse ;
- Le pourcentage d'activation, qui permet d'initialiser le `scheduler` ;
- Le pourcentage de bruit, où la probabilité qu'un agent qui devrait applaudir décide de ne pas applaudir.

Le script complet est sauvegardé dans `notebooks/standing-ovation.jl`.

## Installation

Pour reproduire localement ce projet, suivez les étapes suivantes :

0. Téléchargez le code source.
1. Ouvrez une console Julia et exécutez les commandes suivantes :

   ```julia
   using Pkg
   Pkg.add("DrWatson")
   Pkg.activate("path/to/this/project")
   Pkg.instantiate()
   ```

   Ces commandes installeront tous les packages nécessaires.

2. Activez les scripts avec la commande :

   ```julia
   using DrWatson
   @quickactivate "StandingOvation"
   ```

3. Installez Pluto :

   ```julia
   using Pkg
   Pkg.add("Pluto")
   ```

## Utilisation

Le script principal est `notebooks/standing-ovation.jl`. Vous pouvez l'exécuter avec Pluto.jl.

## Résultats

Le modèle produit plusieurs sorties, dont :
- Une vidéo du mouvement des agents (`videos/standing_ovation.mp4`).
- Un graphique montrant l'évolution du nombre d'agents debout et assis (`plots/evolution_standing_ovation.png`).
- Des pages HTML représentant les agents sous la forme de polygones sur une carte (`results_html/carte_1.png`, `results_html/carte_2.png`, etc.).
- Un tableau de statistiques (`data/exp_pro/statistiques.csv`) contenant des informations telles que :
    1. Le Nombre d'itération (NI) pour atteindre un état stable ;
    2. Le "Stick in the mud" (SM), qui correspond au pourcentage de gens qui font l'opposé de la majorité dans un état stable ;
    3. L'efficacité informationnelle (IE), qui correspond au pourcentage du temps pendant lequel la majorité des agents en état d'équilibre effectuent la même action que la majorité.

