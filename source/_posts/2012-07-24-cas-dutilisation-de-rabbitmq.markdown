---
layout: post
title: "Cas d'utilisation de RabbitMQ"
date: 2012-07-24 01:57
comments: true
categories: rabbitmq
---

RabbitMQ est un *Message Broker*.

Littéralement, un *Broker* signifie un *Courtier*. 
Dans notre cas, ou plus généralement dans l'informatique, la notion de
*Broker* permet d'indiquer un _intermédiaire_.

RabbitMQ est donc un intermédiaire entre deux systèmes ou composants
souhaitant communiquer :
- Le Producer : qui émet un message
- Le Consumer : qui reçoit un message

RabbitMQ est donc un facteur. 
Plus encore, RabbitMQ c'est l'équivalent de La Poste avec les boîtes à 
lettre, les plateformes de distribution, les facteurs, ...

Ci-après, voici les principaux modes de distribution possible.

### Pile FILO : 1/1

Un Producer envoi à un Consumer via 1 file d'attente 

### Dispatch : 1/N 

Un Producer envoi à N Consumers via 1 file d'attente

#### Round-Robbin

Tour à tour (indépendament de la charger)

#### Prefetch

Selon le plus disponible

### Broadcast : 1/N

Un Producer envoi à N Consumers via N file d'attente (1 file par Consumer)
Le message est envoyé à tous les consumers

### Route : 1/N

Un Producer envoi à N Consumers via N file d'attente (1 file par Consumer)
Le message est envoyé à tous les consumers abonnés à la route

#### Routes fixes

Le nom de la route est fixe

#### Routes dynamiques

Le nom de la route est pattern

