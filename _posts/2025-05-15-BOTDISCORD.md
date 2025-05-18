---
title: Création d'un bot pour discord
date: 2025-05-15 17:20:00 +/-0100
categories: [Projet Personnel, dev]
tags: [Python]
author: <author_id>
description: Comment créer et mettre en place un bot discord pour son serveur discord
comments: true
media_subpath: /assets/ 
---


## Introduction :

Discord est aujourd’hui une des plateformes de les plus utilisées par les communautés de joueurs, développeurs, étudiants ou passionnés de tous horizons. Grâce à sa flexibilité, il est possible d’y ajouter des **bots personnalisés** capables de répondre à des messages, modérer des salons, animer des jeux ou automatiser des tâches.

Mais alors… comment crée-t-on son propre bot Discord ?


## Créer son bot discord :
Pour commencer on créer mon bot via le site [discord developper](https://discord.com/developers/application), puis une fois qu'on lui a donné un nom, j'arrive sur cette interface :
![TestImage](imgBlog/application.png)

Celle-ci est très importante, car tous les paramètres du bot, l'invitation et aussi le token du bot se trouve ici.

### Maintenant, invitons notre bot discord sur notre serveur !
Avant de pouvoir l'inviter, il faut posséder au moins 1 serveur où l'on est administrateur ou plus. Ensuite pour l'inviter, on va dans ```OAuth2``` et on coche l'onglet ```bot```, puis on choisit de lui donner les perms admin. Tout en bas de la page, on retrouve le lien à coller pour faire venir le bot sur notre serveur.

![TestImage](imgBlog/application.png)

Le bot est bel est bien sur notre serveur, mais pas connecté, pour ça, il va falloir un peu de code !

Avant de passer au code, il faut récupérer le token dans l'onglet ```bot```
![token](imgBlog/token.png)

> Ne jamais partager son token !
{: .prompt-warning }

Une fois le token récupéré, on va créer nos premières lignes de code pour mettre en ligne le bot

```python
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix=".")

@bot.event
async def on_ready():
    print(f"Connecté en tant que {bot.user}")

bot.run("TOKEN")
```

On exécute ce fichier et notre bot est connecté.


## La suite arrive patience...
