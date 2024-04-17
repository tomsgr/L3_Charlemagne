---
title: "TP R 05"
author: "Léo Dumont"
date: "2024-04-15"
output:
  html_document: default
  pdf_document: default
editor_options: 
  chunk_output_type: console
---

La ligne ci-dessous permet d'affcher le code des blocs lors de l'exportation vers un document PDF ou HTML 

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# Préparer son environnement de travail

1. Il faut commencer par définir un répertoire de travail via le menu `Session` > `Set Working Directory` > `Choose Directory`.
2. Dans les options du fichier Rmarkdown (icône en forme d'engrenage) choisir l'option `Chunck Output In Console`.

```{r}
source(file = "fonctions_texto.r")
```

# Chargement des paquets

```{r}
# install.packages("readtext")
# install.packages("quanteda")
# install.packages("quanteda.textmodels")

library(readtext)
library(quanteda)
library(quanteda.textmodels)
```

# Définition des données d'entraînement et des données de test

## Importation des textes et création du corpus

```{r}
csvf <- "genres_étiquetés_1840-1860.csv"

textes <- readtext(csvf, text_field = "text")
numapresse <- corpus(textes)
```
