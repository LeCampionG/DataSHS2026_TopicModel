# DataSHS2026_TopicModel

Ce dépôt contient le support de la présentation sur les topics models réalisée lors de la semaine data-shs sur Bordeaux le jeudi 11 décembre 2025 à Pessac, ainsi que les support pour le TP.

[Lien vers la présentation](https://lecampiong.github.io/DataSHS2026_TopicModel/#/title-slide)

## Pré-requis

La version de R utilisé pour la présentation est la 4.5.0

Voici la liste des packages nécessaire pour réaliser le TP

```r
# Chargement des données
library(here)
library(readtext)
library(dplyr)

# Création du corpus et manipulation de notre données textuelles
library(quanteda)
library(tidytext)

# Représentation et premières analyses
library(quanteda.textplots)
library(quanteda.textstats)
library(ggplot2)
# Pour faire un réseau de co-occurences plus complexe
library(igraph)
library(ggraph)
library(tidygraph)

# Réalisation du topic model
library(ldatuning)
library(topicmodels)

# Représentation du topic model
library(broom)
library(wesanderson)

# Pour aller un peu plus loin...
library(FactoMineR)
library(ape)
library(dendextend)
library(umap)
library(ggrepel)

```

Pour vérifier leur installation :

```r
# Commande de base pour installer un package
# install.packages("here")


# Process pour vérifier l'installation des packages

#  Packages nécessaires
my_packages <- c("here", 
                 "readtext", 
                 "dplyr", 
                 "quanteda", 
                 "tidytext", 
                 "quanteda.textplots", 
                 "quanteda.textstats", 
                 "ggplot2", 
                 "igraph", 
                 "ggraph", 
                 "tidygraph", 
                 "ldatuning", 
                 "topicmodels", 
                 "broom", 
                 "wesanderson",
                  "LDAvis",
                 "FactoMineR",
                  "ape",
                  "dendextend",
                  "umap",
                  "ggrepel" )


# Vérifier si ces packages sont installés
missing_packages <- my_packages[!(my_packages %in% installed.packages()[,"Package"])]

# Installation des packages manquants depuis le CRAN
if(length(missing_packages)) install.packages(missing_packages, 
                                              repos = "http://cran.us.r-project.org")

# Chargement des packages nécessaires
lapply(my_packages, library, character.only = TRUE)

# Si difficultés possible de passer par les dépôts de github
 # install.packages("devtools")
devtools::install_github("nikita-moor/ldatuning")

```
